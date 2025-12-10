---
title: "Google introduit des protections avancées contre les injections de requêtes dans Chrome"
seoTitle: "Google introduit des défenses inédites contre les attaques dans Chrome"
seoDescription: "Google renforce la sécurité de Chrome avec le User Alignment Critic et les Agent Origin Sets, empêchant toute manipulation via des agents IA."
datePublished: Wed Dec 10 2025 20:23:13 GMT+0000 (Coordinated Universal Time)
cuid: cmj0gi42s000202jmcw6g2flu
slug: google-defenses-pour-injections-dans-chrome
canonical: https://www.techradar.com/pro/security/google-adds-prompt-injection-defenses-to-chrome

---

# Google introduit des protections avancées contre les injections de requêtes dans Chrome

## TL;DR
- Google renforce la sécurité de Chrome contre les attaques par injection de requêtes indirectes.
- Deux nouvelles fonctionnalités clés : le User Alignment Critic et les Agent Origin Sets.
- Accès et actions des agents IA désormais soumis à des approbations explicites et des restrictions sur les sites sensibles.
- Transparence accrue grâce aux journaux de travail des agents accessibles aux utilisateurs.

## Qu'est-ce que l'injection de requêtes ?

L'injection de requêtes indirectes est une méthode d'attaque exploitant les agents intelligents pour manipuler leurs comportements. Ces agents, souvent utilisés pour automatiser des tâches ou fournir des réponses basées sur des instructions, peuvent être abusés en insérant des commandes dissimulées dans des contenus tiers. Cela permet de forcer l'agent à exécuter des actions malveillantes, souvent à l'insu de l'utilisateur.

Ce type d'attaque représente un réel danger dans un environnement où les outils alimentés par l'intelligence artificielle sont de plus en plus présents. Les agents IA, tels qu'intégrés à des navigateurs comme Chrome, doivent donc être mieux sécurisés pour protéger les données et les interactions des utilisateurs.

## Les nouvelles mesures de sécurité dans Chrome

### User Alignment Critic

Le User Alignment Critic est une fonctionnalité de validation conçue pour contrôler les actions proposées par les agents IA. Elle repose exclusivement sur les métadonnées associées aux actions et joue le rôle de filtre final. Son objectif est double : garantir que chaque action correspond aux intentions initiales de l'utilisateur et éviter toute manipulation entraînée par des contenus malveillants.

Concrètement, le processus se déroule ainsi :
- Après qu'un agent IA génère une réponse ou un plan d'action, celui-ci est soumis à l'analyse du User Alignment Critic.
- Si l'action ne correspond pas aux objectifs définis par l'utilisateur, elle est automatiquement rejetée.

Bien que cette approche soit limitée par le fait que le critère d'analyse est uniquement basé sur les métadonnées, elle représente une avancée notable dans la lutte contre les injections de requêtes.

### Agent Origin Sets

Les Agent Origin Sets permettent de restreindre les accès des agents IA aux origines considérées comme fiables et pertinentes pour leur tâche actuelle. Cette fonctionnalité limite les possibilités d'intervention malveillante en établissant des garde-fous clairs sur les données pouvant être exploitées.

Principaux axes de fonctionnement :
- Seules les origines explicitement autorisées par l'utilisateur sont accessibles.
- Un processus de gestion des « origines fiables » est implémenté, assurant à l'utilisateur un contrôle accru sur ces paramètres.

En réduisant les interactions des agents avec des environnements potentiellement risqués, ces restrictions diminuent les risques d'abus et renforcent la confidentialité des activités en ligne.

### Transparence accrue et contrôle utilisateur

En plus de ces fonctionnalités, Google a mis en place des mécanismes complémentaires pour garantir une meilleure transparence et un contrôle accru des agents IA :
- **Journal de travail des agents** : les utilisateurs peuvent consulter les décisions prises et les actions exécutées par leurs agents en temps réel.
- **Approbation explicite** : avant d'accéder à des sites sensibles tels que des plateformes bancaires ou médicales, les agents IA doivent obtenir une autorisation préalable de l'utilisateur.

Ces mesures permettent aux utilisateurs de garder la main sur les interactions de leurs outils et d'identifier rapidement d'éventuelles actions non désirées.

## Impact pour les utilisateurs

Avec ces nouvelles fonctionnalités, les utilisateurs de Chrome bénéficient d'un niveau de sécurité renforcé lors de leur navigation. Les actions des agents IA sont mieux encadrées, réduisant considérablement les risques de manipulation malveillante. De plus, la transparence offerte par les journaux d'activité contribue à instaurer un climat de confiance entre l'utilisateur et les outils qu'il utilise.

Toutefois, la mise en œuvre de ces protections peut nécessiter un effort supplémentaire pour comprendre et configurer les paramètres. Les développeurs devront également s'assurer que leurs intégrations respectent ces nouvelles contraintes, notamment en ce qui concerne les validations et les origines approuvées.

## Avantages et limites des défenses actuelles

### Avantages
- Les attaques par injection de requêtes sont significativement réduites grâce à des mécanismes de validation et de restriction.
- Le contrôle explicite des interactions avec des sites sensibles offre une protection supplémentaire pour les données critiques.
- La transparence et la traçabilité des actions des agents IA renforcent la confiance et permettent un suivi complet.

### Limitations
- Le User Alignment Critic repose sur un contexte limité (par exemple les métadonnées), ce qui pourrait mener à des rejets d'actions pourtant valides.
- Les nouvelles mesures de validation pourraient ne pas être adaptées à toutes les formes d'attaques de type injection de requêtes.
- La configuration initiale des Agent Origin Sets et des autres mécanismes de sécurité peut ajouter une couche de complexité pour les utilisateurs comme pour les développeurs.

## À retenir

En intégrant des défenses comme le User Alignment Critic et les Agent Origin Sets, Google marque une étape importante dans la sécurisation des interactions des agents alimentés par l'intelligence artificielle. Ces fonctionnalités renforcent la protection des utilisateurs contre les risques d'injections de requêtes tout en favorisant une transparence accrue. 

Bien que des défis subsistent autour de leur mise en œuvre, ces avancées montrent la direction que prennent les navigateurs modernes pour garantir une utilisation plus sûre des technologies basées sur l’IA.

[source](https://www.techradar.com/pro/security/google-adds-prompt-injection-defenses-to-chrome)