---
title: "Rust et Docker : Automatisation de Chromium avec WebSockets"
seoTitle: "Rust et Docker : Automatisation de Chromium avec WebSockets et Docker"
seoDescription: "Découvrez comment automatiser Chromium avec Rust via WebSockets dans Docker, avec des options pour arm64, VNC, noVNC et une gestion avancée des containers."
datePublished: Wed Nov 19 2025 23:46:54 GMT+0000 (Coordinated Universal Time)
cuid: cmi6nj5rv000102i8dxjp0xh8
slug: rust-automatisation-chromium-websockets-docker
canonical: https://dev.to/adaschevici/rusty-puppets-websockets-and-voyeurism-part-ii-driving-chromium-in-docker-with-a-window-30li

---

# Rust et Docker : Automatisation de Chromium avec WebSockets

## Pourquoi choisir Chromium avec Docker ?

Chromium, le projet open-source derrière le navigateur Google Chrome, est un outil puissant pour automatiser des tâches liées au web, comme le crawling, les tests end-to-end ou la génération de contenus dynamiques. Cependant, travailler avec Chromium dans un environnement non isolé peut poser des problèmes, notamment en matière de compatibilité des versions, de gestion des dépendances, ou encore de sécurité.

Pour répondre à ces défis, l'utilisation de Docker offre plusieurs avantages majeurs :

- **Isolation** : Les dépendances de Chromium et des outils nécessaires sont encapsulées dans un conteneur. Cela réduit les problèmes liés aux conflits de versions sur votre système.
- **Portabilité** : Les images Docker permettent une exécution uniforme sur différentes machines et environnements. C'est particulièrement utile pour les développeurs travaillant sur des architectures arm64, comme les Mac M1.
- **Scalabilité** : Docker facilite la gestion des instances Chromium déployées sur plusieurs conteneurs, idéal pour des scénarios de haute disponibilité ou d'exécutions parallèles.
- **Sécurité renforcée** : Grâce à la sandbox intégrée et aux bonnes pratiques de conteneurisation, vous minimisez les risques d'exposer Chromium à des attaques extérieures.

En associant Docker avec Rust et des WebSockets, il devient possible de piloter Chromium de manière fluide et performante, tout en conservant un niveau important de modularité et de contrôle.

---

## Les composants nécessaires

Pour mettre en place un environnement fonctionnel permettant l'automatisation de Chromium dans Docker, voici les éléments requis : 

1. **Chromium** : Le noyau du projet, qui sera configuré pour fonctionner à l'intérieur du conteneur.
2. **Xvfb (X Virtual Framebuffer)** : Simule un environnement graphique pour Chromium, essentiel lorsque vous exécutez le navigateur dans un conteneur.
3. **VNC/noVNC** : Permet la visualisation de l'interface graphique du navigateur en temps réel. Cette fonctionnalité est pratique pour le débogage.
4. **Socat** : Utilisé comme proxy pour router le trafic vers et depuis le conteneur.
5. **Supervisor** : Gère les différents processus au sein du conteneur, garantissant qu'ils restent actifs et redémarrent en cas de défaillance.
6. **Client Rust utilisant WebSockets** : Permet de communiquer avec Chromium de façon efficace et flexible. Rust offre à la fois des performances impressionnantes et une gestion fine de la mémoire, essentielle pour un service de contrôle en temps réel.

---

## Stratégies d'image Docker

La création de votre image Docker joue un rôle crucial dans la performance et la fiabilité de votre environnement. Voici quelques stratégies optimales pour bâtir votre Dockerfile :

### Optimiser pour arm64

L'architecture arm64 devient de plus en plus populaire, notamment avec l'adoption des processeurs Apple Silicon. Lors de la construction de l'image Docker, assurez-vous que Chromium est compilé avec des flags adaptés à arm64 pour garantir la compatibilité et la performance optimale.

```Dockerfile
FROM ubuntu:20.04

# Mise à jour des packages
RUN apt-get update && apt-get install -y \
    chromium-browser \
    xvfb \
    x11vnc \
    noVNC \
    socat \
    supervisor

# Quelques configurations spécifiques
ENV DISPLAY=:99
EXPOSE 5900 6080
CMD ["supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]
```

### Découplage des services avec supervisord

Le fichier `supervisord.conf` permet de définir les services à exécuter dans le conteneur, comme suit :

```ini
[supervisord]
nodaemon=true

[program:xvfb]
command=Xvfb :99 -screen 0 1280x1024x24
autostart=true
autorestart=true

[program:chromium]
command=chromium-browser --no-sandbox --disable-gpu --remote-debugging-port=9222
autostart=true
autorestart=true
```

### Ajout de noVNC pour la visualisation

noVNC permet de se connecter au conteneur via un client VNC web. Cela est particulièrement utile pour déboguer et visualiser l'état du navigateur en cas de problème.

---

## Configuration et débogage du conteneur

Une fois l'image Docker prête, il est temps de configurer et de déboguer votre conteneur. Voici quelques étapes cruciales :

### Tester la connectivité WebSocket

Après avoir démarré le conteneur, il est essentiel de vérifier que le serveur WebSocket fonctionne correctement et que votre client Rust peut s'y connecter :

```rust
use tungstenite::connect;
use url::Url;

fn main() {
    let (mut socket, _response) =
        connect(Url::parse("ws://localhost:9222/devtools/browser/<browser-id>").unwrap())
        .expect("Échec de la connexion au serveur WebSocket");

    socket.write_message(tungstenite::Message::Text("{\"id\":1,\"method\":\"Network.enable\"}".to_string())).unwrap();
    println!("Réponse: {:?}", socket.read_message().unwrap());
}
```

### Journalisation et surveillance des processus

Utilisez les logs générés par `supervisor` pour identifier les erreurs et anomalies. En cas de problème d'affichage ou de connexion, vérifiez les services `xvfb` et `chromium`.

### Configuration réseau et proxy

Configurez `socat` pour router efficacement les connexions en cas de besoin :

```bash
socat TCP-LISTEN:9222,reuseaddr,fork TCP:127.0.0.1:9222
```

---

## Recommandations de sécurité pour la production

Lorsque vous déployez un environnement Docker sur des serveurs de production, il est crucial d'assurer une sécurité maximale. Voici quelques bonnes pratiques :

1. **Protection de noVNC** : Ajoutez une authentification ou servez noVNC derrière un proxy HTTPS avec mot de passe.
2. **Utilisateurs non-root** : Configurez l'image pour qu'elle utilise un utilisateur non-root. Cela réduit les risques d'escalade de privilèges.
3. **VPN et pare-feu** : Utilisez un VPN pour sécuriser l'accès au conteneur. Configurez également les règles de pare-feu pour autoriser uniquement les connexions nécessaires.
4. **Version des packages figée** : Lorsque vous générez votre image, spécifiez des versions fixes pour les dépendances. Cela garantit la stabilité entre les déploiements.
5. **Surveillance active** : Intégrez des outils comme `Prometheus` ou `Grafana` pour surveiller les ressources et détecter des anomalies dans votre infrastructure.

---

En conclusion, l'automatisation de Chromium dans un conteneur Docker, combinée à l'utilisation des WebSockets pour le piloter à l'aide de Rust, ouvre la voie à des solutions robustes et flexibles. Que ce soit pour le débogage, les tests ou des déploiements à grande échelle, cette approche offre des performances et une modularité adaptées aux besoins des développeurs modernes. 

[source](https://dev.to/adaschevici/rusty-puppets-websockets-and-voyeurism-part-ii-driving-chromium-in-docker-with-a-window-30li)