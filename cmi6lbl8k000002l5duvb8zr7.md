---
title: "Des clusters Ray détournés pour miner des cryptomonnaies : une vulnérabilité alarmante"
seoTitle: "Clusters Ray détournés : menace cryptojacking et botnets"
seoDescription: "Les clusters Ray exposés à une faille critique détournés pour miner des cryptomonnaies et mener des attaques DDoS par le groupe IronErn440."
datePublished: Wed Nov 19 2025 22:45:01 GMT+0000 (Coordinated Universal Time)
cuid: cmi6lbl8k000002l5duvb8zr7
slug: clusters-ray-detournes-menace-cryptojacking-botnets
canonical: https://www.techradar.com/pro/security/ray-clusters-hijacked-and-turned-into-crypto-miners-by-shadowy-new-botnet

---

# Des clusters Ray détournés pour miner des cryptomonnaies : une vulnérabilité alarmante

## Qu'est-ce que les clusters Ray ?

Ray est un framework open-source particulièrement prisé dans le domaine de l'informatique distribuée et de l'intelligence artificielle. Il est conçu pour exécuter des programmes Python en distribuant les tâches sur plusieurs machines, offrant ainsi une mise à l'échelle horizontale rapide et efficace. Typiquement, un cluster Ray est composé de nœuds principaux et de nœuds travailleurs, chacun jouant un rôle spécifique dans l'exécution des tâches.

L'une des forces de Ray réside dans son API, qui permet de soumettre des tâches et des jobs de manière transparente. Malheureusement, cette même caractéristique rend Ray vulnérable face à des scénarios de cybersécurité complexes, en particulier lorsque son déploiement n'est pas correctement sécurisé.

## Une faille critique exploitée par des cybercriminels

Une vulnérabilité critique dans les versions 2.6.3 et 2.8.0 de Ray, découverte en 2023, reste encore largement exploitée. Cette faille repose sur l'API Jobs non sécurisée, qui permet à des attaquants de soumettre des tâches malveillantes et d'exécuter du code arbitraire à distance, sans aucune authentification préalable.

Cette situation représente une menace importante pour les infrastructures utilisant Ray, et les conséquences sont amplifiées par le fait que le correctif nécessaire pour résoudre ce problème n’a toujours pas été publié par Anyscale, l'organisation responsable du projet. Résultat : plus de 230,000 clusters Ray sont aujourd'hui exposés en ligne et deviennent des cibles privilégiées pour les groupes malveillants, parmi lesquels le tristement célèbre "IronErn440".

### Le groupe IronErn440 et ses méthodes

IronErn440 est un groupe de cybercriminels qui a exploité cette vulnérabilité en intensifiant ses opérations. Leur stratégie repose sur l'utilisation de payloads générés par des technologies basées sur l'intelligence artificielle, ce qui leur permet de soumettre des tâches malveillantes à l'API de Jobs non sécurisée. Ces tâches initient l'installation de logiciels malveillants, en particulier le mineur de cryptomonnaies XMRig, via des scripts multi-étapes hébergés sur des plateformes comme GitHub et GitLab.

## Le rôle du cryptojacking dans cette attaque

Le cryptojacking, technique bien connue des cybercriminels, est au cœur des activités d'IronErn440. Il consiste à détourner les ressources informatiques des clusters Ray pour miner des cryptomonnaies, principalement le Monero (XMR), souvent choisi pour sa confidentialité et sa facilité d'exploitation.

### Pourquoi XMRig est efficace dans ce contexte ?

Le mineur XMRig est configuré par les attaquants pour exploiter jusqu'à 60 % des capacités du processeur des machines infectées. Ce choix stratégique permet de réduire les chances d’être détectés par des outils classiques de surveillance, tout en maintenant une efficacité opérationnelle suffisante pour générer un gain significatif.

Avec plus de 230,000 serveurs Ray compromis, l’ampleur du cryptojacking prend une dimension alarmante. De simples infrastructures distribuées au service d’applications Python se transforment en véritables mines de cryptomonnaies non autorisées.

## Conséquences pour les utilisateurs de Ray

Les utilisateurs de Ray, qu’ils soient développeurs, chercheurs ou entreprises, doivent prendre conscience des risques liés à cette faille. Parmi les impacts principaux, on peut identifier :

- **Une vulnérabilité accrue** : Les clusters Ray restent particulièrement exposés dans les environnements où les règles de sécurité sont relâchées ou inexistantes.
- **Un impact économique** : La surconsommation des ressources entraîne non seulement une hausse des coûts opérationnels (factures énergétiques, temps machine), mais affecte également la performance des systèmes légitimes.
- **Risques systémiques** : La prolifération des attaques pourrait conduire à la formation de super-botnets capables de perpétrer des attaques orchestrées, comme le vol massif de données ou les attaques par déni de service (DDoS), paralysant des infrastructures critiques.

## Solutions pour atténuer les risques

Bien que la vulnérabilité critique de Ray reste non corrigée, plusieurs mesures peuvent être prises pour réduire les risques de compromission :

1. **Pare-feu strict et isolation réseau**  
   Il est primordial de restreindre l'accès réseau des clusters Ray en les isolant des environnements non contrôlés. L’utilisation de pare-feu bien configurés protège contre les accès non autorisés à l’API Jobs.

2. **Mises à jour et restriction d'accès**  
   En l’absence de mise à jour corrective, les utilisateurs peuvent limiter manuellement l’accès à l’API. L’intégration d’authentifications renforcées et de mécanismes de contrôle peut significativement réduire les possibilités d’intrusion.

3. **Surveillance active des ressources**   
   Mettre en œuvre des outils de monitoring pour détecter les anomalies dans l’utilisation des ressources CPU. Des pics soudains ou des usages constants autour de 60 % peuvent être des indicateurs précoces de cryptojacking.

## À surveiller / risques

Les attaques ciblant les clusters Ray mettent en lumière certains risques émergents liés à la cybersécurité et à l’informatique distribuée, notamment :

- Une augmentation des menaces utilisant des payloads générés par IA, qui améliorent la sophistication des attaques.
- Une exploitation accélérée des infrastructures cloud publiques, rendant les systèmes mal sécurisés particulièrement vulnérables.
- L'absence de correctifs officiels, qui oblige les administrateurs à renforcer manuellement leurs défenses.

Dans ce contexte évolutif, il est essentiel de suivre de près les développements autour de Ray et d'autres frameworks open-source pour réagir rapidement aux nouvelles menaces.

---

Face à une faille critique persistante, les clusters Ray illustrent les dangers que représentent les cyberattaques dans le monde connecté actuel. La sécurité des infrastructures distribuées dépend de mesures proactives, de surveillances constantes et de la collaboration entre développeurs et experts en cybersécurité.

[source](https://www.techradar.com/pro/security/ray-clusters-hijacked-and-turned-into-crypto-miners-by-shadowy-new-botnet)