---
title: "React2Shell : Exploitation et propagation massive de mineurs cryptographiques et malwares"
seoTitle: "React2Shell : Propagation de mineurs cryptographiques et malwares - Que savoir et comment protéger vos systèmes"
seoDescription: "Découvrez comment la faille de sécurité React2Shell dans RSC est exploitée pour diffuser mineurs cryptographiques et malwares. Mettez à jour vos composants !"
datePublished: Thu Dec 11 2025 13:32:14 GMT+0000 (Coordinated Universal Time)
cuid: cmj1h9fql000002ju4ryrhlcw
slug: react2shell-securite-malwares
canonical: https://thehackernews.com/2025/12/react2shell-exploitation-delivers.html

---

# React2Shell : Exploitation et propagation massive de mineurs cryptographiques et malwares

## TL;DR
- Le CVE-2025-55182 dans les React Server Components (RSC) est une vulnérabilité critique permettant l'exécution de code à distance.
- Elle est exploitée pour diffuser des mineurs cryptographiques et des malwares tels que PeerBlight, CowTunnel et ZinFoq.
- Environ 165 000 IPs et 644 000 domaines sont exposés dans le monde, principalement dans les secteurs de la construction, du divertissement et de la finance.
- Une mise à jour immédiate des composants React Server est essentielle pour contrer ces attaques.

## Qu'est-ce que React2Shell ?

React2Shell fait référence à une vulnérabilité critique (CVE-2025-55182) identifiée dans React Server Components (RSC), une technologie largement utilisée pour construire des applications web modernes. Cette faille permet une exécution de code à distance non authentifiée, ouvrant la porte à diverses activités malveillantes, notamment la distribution de malwares peu documentés et de mineurs cryptographiques.

Les attaquants exploitent cette faille en ciblant des organisations à l'aide de scripts automatisés capables de repérer les environnements vulnérables. Cela inclut les serveurs utilisant les technologies Node.js associées, telles que `react-server-dom-webpack`. En conséquence, les secteurs tels que la construction, le divertissement et la finance sont particulièrement touchés.

## Principaux malwares observés

### PeerBlight : Backdoor Linux
PeerBlight est un implant malware conçu pour fonctionner sur Linux. Il utilise un shell inversé pour contrôler les systèmes ciblés, permet la gestion des fichiers distants et l'exécution de fichiers exécutables. Sa communication avec un serveur de commande et contrôle (C2) repose sur une architecture sophistiquée utilisant des Domain Generation Algorithms (DGA) et le protocole DHT BitTorrent.

Il se distingue par ses techniques avancées de dissimulation, notamment en se camouflant sous le processus légitime `ksoftirqd`, rendant sa détection difficile.

### ZinFoq : Implant post-exploitation Go
Développé en Go, ZinFoq est une menace post-exploitation polyvalente. Il offre un accès shell et permet aux attaquants de télécharger des payloads supplémentaires ou de pivoter dans un réseau.

Parmi ses fonctionnalités remarquables, on trouve la mise en place de proxys SOCKS5, la redirection de ports TCP et la dissimulation sous forme de services légitimes. Ces capacités en font un outil précieux pour les acteurs malveillants cherchant à étendre leur contrôle sur les systèmes compromis.

### Scripts malveillants
Parmi les scripts observés dans les attaques de React2Shell, plusieurs se démarquent :
- **sex.sh** : Automatisation de l’extraction et déploiement de mineurs XMRig, ciblant des ressources système pour miner des cryptomonnaies.
- **d5.sh** et ses variantes : Installent et maintiennent le framework Sliver C2 pour le contrôle des systèmes infectés.
- **wocaosinm.sh** : Déploie le malware Kaiji (DDOS) avec des fonctionnalités avancées d’administration distante et de persistance.

Ces scripts montrent à quel point les attaques liées à React2Shell sont variées et efficaces, combinant outils de persistance, exploitation et exfiltration.

## Impact global de la faille

La propagation de cette vulnérabilité est inquiétante par son ampleur. Les données collectées par Shadowserver indiquent qu'au moins 165 000 adresses IP et 644 000 domaines sont actuellement exposés. La majorité des adresses touchées sont localisées aux États-Unis, en Allemagne et en France.

Les attaquants s’appuient sur des tactiques proactives, notamment en analysant des dépôts GitHub pour trouver des implémentations vulnérables de Next.js. Cela intensifie considérablement leur capacité à cibler des systèmes non corrigés.

Cette propagation massive démontre à quel point React2Shell représente une menace mondiale, dépassant les frontières et affectant des entreprises de toutes tailles.

## Recommandations pour protéger vos systèmes

Face à cette vulnérabilité critique, plusieurs mesures s'imposent :

1. **Mettre à jour les composants React Server** : Remplacez immédiatement les versions vulnérables de `react-server-dom-webpack` par leurs équivalents corrigés.
2. **Renforcer la surveillance des systèmes** : Implémentez des outils de détection des malwares et surveillez les communications réseau pour repérer toute activité anormale vers des serveurs C2.
3. **Audits de sécurité réguliers** : Vérifiez les configurations et les dépendances des environnements Node.js pour identifier et corriger les vulnérabilités.
4. **Collaboration avec des experts** : Consultez les rapports détaillés publiés par des groupes tels que Unit 42 de Palo Alto Networks et Rapid7. Ces derniers fournissent des analyses approfondies sur les clusters d'attaquants exploitant cette faille.

## Les secteurs les plus vulnérables

Les attaques liées à React2Shell ne ciblent pas exclusivement les organisations technologiques. Les secteurs suivants sont parmi les plus touchés :

- **Construction** : Infrastructure logicielle souvent moins mise à jour.
- **Divertissement** : Dépendance accrue à des sites et services accessibles en ligne.
- **Finance** : Risque accru en raison de la nature sensible des données traitées.
- **Éducation** : Utilisation massive de technologies web, souvent sans mise à jour régulière.

Ces secteurs doivent redoubler de vigilance et prioriser une mise à jour de leurs environnements React Server Components.

## Conclusion

La vulnérabilité React2Shell met en lumière les risques croissants posés par des attaques sophistiquées exploitant des composants web critiques. La mise à jour de vos systèmes reste l'approche la plus efficace pour prévenir une exploitation de cette faille. En agissant vite, les entreprises peuvent limiter les impacts potentiels et protéger leurs infrastructures contre les malwares et les mineurs cryptographiques.

[source](https://thehackernews.com/2025/12/react2shell-exploitation-delivers.html)