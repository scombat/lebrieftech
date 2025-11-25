---
title: "Cadre de collaboration entre AUTOSAR AP et ROS 2"
seoTitle: "Cadre de collaboration innovant entre AUTOSAR AP et ROS 2 pour les véhicules autonomes"
seoDescription: "Découvrez comment un nouveau cadre facilite la collaboration entre AUTOSAR AP et ROS 2, deux outils clés pour les véhicules autonomes."
datePublished: Tue Nov 25 2025 06:30:34 GMT+0000 (Coordinated Universal Time)
cuid: cmie75jmc000002js0ckhb29k
slug: cadre-de-collaboration-autosar-ap-et-ros-2
canonical: https://arxiv.org/abs/2511.17540

---

# Cadre de collaboration entre AUTOSAR AP et ROS 2

## TL;DR

- La collaboration entre AUTOSAR Adaptive Platform (AUTOSAR AP) et Robot Operating System 2 (ROS 2) vise à rapprocher les outils industriels et de recherche pour les véhicules autonomes.
- Le cadre repose sur l'utilisation de DDS pour surmonter les divergences de protocoles de communication avec AUTOSAR AP, qui utilise SOME/IP.
- Des tests empiriques ont validé l'efficacité de la solution, notamment en termes de performance et d'intégration.
- Des outils automatisés, comme le générateur de fichiers de configuration, simplifient l'utilisation du framework.
- Ce cadre facilite la recherche et le développement de technologies de conduite autonome.

## Présentation du cadre de collaboration

La communication entre les plateformes utilisées dans l'industrie et celles favorisées par le monde académique représente un réel défi pour les chercheurs et fabricants de véhicules autonomes. AUTOSAR Adaptive Platform (AUTOSAR AP) et Robot Operating System 2 (ROS 2) sont deux exemples de telles plateformes, chacune répondant à des besoins spécifiques :  

- **AUTOSAR AP** est largement déployée industriellement grâce à son accent sur la sécurité et la fiabilité dans les environnements de production. Cependant, son adoption en recherche reste limitée en raison de contraintes liées à sa licence et son implantation.
  
- **ROS 2**, en revanche, est très populaire dans le domaine de la recherche pour sa flexibilité et son adaptabilité. Ses caractéristiques favorisent les expérimentations rapides, ce qui est essentiel dans la recherche avancée. Cependant, il est moins adapté aux besoins industriels tels que la sécurité stricte et la conformité aux standards.

Le fossé entre ces technologies freine leur intégration et limite la collaboration entre les laboratoires de recherche et l'industrie automobile. Le cadre de collaboration présenté ici propose une solution visant à combiner les forces de ces deux outils pour accélérer l'innovation et l'implémentation des technologies de conduite autonome.

## Défis des plateformes de véhicules autonomes

La recherche et le développement de véhicules autonomes nécessitent des outils robustes, capables de répondre à des exigences strictes en termes de temps réel, de performances et de sécurité. Cependant, ROS 2 et AUTOSAR AP utilisent des protocoles de communication incompatibles entre eux :

- **ROS 2** s'appuie sur le protocole **DDS** (Data Distribution Service), conçu pour les systèmes distribués en temps réel. DDS garantit des échanges fiables et rapides de données entre les différents composants du système.
  
- **AUTOSAR AP**, quant à lui, utilise le protocole **SOME/IP** (Scalable service-Oriented Middleware over IP), orienté vers les besoins industriels et la mise en réseau sécurisée.

La divergence de ces protocoles constitue un obstacle majeur à l'interopérabilité et limite le potentiel des technologies développées dans les deux univers.

## Les solutions proposées par l'article

### Un framework basé sur DDS

Pour surmonter ces problèmes, les chercheurs ont conçu un cadre de collaboration permettant une interaction transparente entre AUTOSAR AP et ROS 2. Le pilier central de cette solution est l’utilisation de **DDS**, déjà intégré dans ROS 2, combiné avec un système de conversion vers le protocole SOME/IP, utilisé par AUTOSAR AP.  

Ce système de **bridge converter** garantit une communication fluide entre les deux protocoles. Il permet la traduction des messages échangés entre AUTOSAR AP et ROS 2 sans compromission des performances ni de la fiabilité.

### Automatisation via un générateur de fichiers de configuration

Pour simplifier l'intégration et l'implémentation, les chercheurs ont également développé un **générateur automatique de fichiers de configuration**. Cet outil réduit considérablement la charge de travail des développeurs en automatisant le processus de configuration nécessaire au fonctionnement du bridge converter.

Ce point est particulièrement avantageux, car il accélère le déploiement de la solution dans différents types de projets industriels et académiques.

## Validation et tests empiriques

L'efficacité du cadre proposé a été validée à travers plusieurs tests expérimentaux. Voici les résultats clés :  

- **Performance** : Le bridge converter a démontré des **temps de conversion rapides** entre DDS et SOME/IP, confirmant sa pertinence pour des systèmes critiques nécessitant une faible latence.  
- **Intégration fluide** : Le framework s'est montré hautement compatible avec les outils actuels basés sur ROS 2. Grâce à l'automatisation de la configuration, les développeurs disposent d’une solution pratique et directement opérationnelle.

Ces résultats ont été publiés et présentés lors de la *27th Euromicro Conference on Digital System Design (DSD) de 2024*, validant la faisabilité du concept dans un contexte académique et professionnel.

## Avantages du cadre proposé

En connectant efficacement deux des plateformes les plus utilisées pour les véhicules autonomes, ce cadre apporte plusieurs bénéfices tangibles :  
- **Interopérabilité accrue** : Les chercheurs et industriels pourront utiliser conjointement ROS 2 et AUTOSAR AP sans obstacles majeurs liés aux protocoles.  
- **Simplicité** : L'outil de configuration automatisé réduit la complexité de mise en œuvre et le temps nécessaire à l’intégration.  
- **Flexibilité** : Les capacités d’interaction entre AUTOSAR AP et ROS 2 permettent de tirer parti des avantages uniques des deux plateformes.  

Ces éléments font de ce système une solution efficace pour accélérer le rapprochement entre recherche et industrie dans le développement des technologies de véhicules autonomes.

## Considérations et défis futurs

Malgré ses promesses, le cadre proposé n’est pas exempt de limitations. Les défis suivants devront être pris en compte pour garantir son adoption et son évolution dans le temps :  

- **Support limité** : Le cadre repose sur des protocoles spécifiques (DDS et SOME/IP). Cela peut poser des problèmes de compatibilité avec des architectures plus complexes ou des standards industriels divergents.  
- **Évolutivité** : À mesure que ROS 2 et AUTOSAR AP sont mis à jour, des efforts supplémentaires seront nécessaires pour adapter le système et garantir sa pérennité.
- **Complexité d’intégration** : Même avec un générateur automatisé, certains projets industriels spécifiques pourraient exiger des ajustements personnalisés.  

Ces contraintes rappellent qu'une attention particulière devra être portée aux évolutions de ces technologies pour assurer une adoption durable et efficace.

## À retenir

Ce cadre de collaboration représente une avancée significative pour surmonter les barrières entre les plateformes industrie et recherche dans le domaine des véhicules autonomes. En assurant une communication fluide entre AUTOSAR AP et ROS 2 via le bridge converter et en simplifiant l'intégration grâce à des outils automatisés, cette solution favorise l’accélération de l’innovation et le passage rapide des prototypes de recherche à la production industrielle.  

Pour les chercheurs et les professionnels du secteur automobile, ce type d’initiative pourrait déboucher sur des opportunités concrètes pour un déploiement plus rapide et harmonieux des technologies dédiées à la conduite autonome.

[source](https://arxiv.org/abs/2511.17540)