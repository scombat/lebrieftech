---
title: "Sécurité renforcée de Chrome grâce à l'intelligence artificielle et aux capacités agentiques"
seoTitle: "Sécurité renforcée de Chrome : IA et capacités agentiques"
seoDescription: "Découvrez comment Google Chrome améliore la sécurité grâce à l'intelligence artificielle pour prévenir les menaces comme l'injection de prompts et protéger vos données."
datePublished: Mon Dec 08 2025 19:07:11 GMT+0000 (Coordinated Universal Time)
cuid: cmixiwml0000202iecuer1sin
slug: securite-renforcee-chrome-ia-capacites-agentiques
canonical: http://security.googleblog.com/2025/12/architecting-security-for-agentic.html

---

# Sécurité renforcée de Chrome grâce à l'intelligence artificielle et aux capacités agentiques

## TL;DR

- Des attaques d'injection de prompts ciblent les capacités d'IA en exploitant des contenus malveillants.
- Chrome introduit une critique d'alignement utilisateur pour vérifier et approuver chaque action d'IA sensible.
- Les origines des actions agentiques sont isolées et limitées pour une meilleure protection des données.
- Confirmation utilisateur obligatoire pour des interactions sensibles, comme des transactions ou l'accès à des données critiques.
- Audits continus et simulations d'attaques garantissent une défense proactive et améliorent les sécurités.

## Alignement utilisateur et vérifications critiques

L'une des innovations majeures introduites dans Chrome est la mise en place d'un modèle d'IA secondaire dédié, nommé Critique d'Alignement Utilisateur (CAU). Ce système autonome a pour rôle de valider chaque action planifiée par l'agent principal. En analysant uniquement les métadonnées associées à une action, le CAU demeure isolé des contenus potentiellement non sécurisés, réduisant ainsi la surface d'attaque.

Le principe est simple : lorsqu'une action mal alignée est détectée, elle est rejetée immédiatement. L'agent est alors informé pour ajuster son plan et proposer une alternative conforme aux exigences et aux objectifs de l'utilisateur. Ce processus trouve ses racines dans la recherche avancée de DeepMind et le paradigme du modèle dual IA, conçu pour réduire les risques et garantir une cohérence maximale entre intentions et résultats.

## Isolation stricte des origines et protection des données

Chrome applique des principes éprouvés de sécurité, notamment le Site Isolation et la politique de Same-Origin afin de catégoriser les interactions agentiques en deux types distincts :

- **Lecture seule** : lorsqu'un agent consulte uniquement des informations sur un site.
- **Lecture-écriture** : lors d'interactions actives comme des clics ou des soumissions de formulaires.

Chaque tâche est soumise à des fonctions de vérification, permettant de bloquer les accès potentiels à des origines non autorisées. Cela limite les risques de fuite de données entre sites et renforce ainsi la sécurité des utilisateurs. Ces fonctions ("gating functions") agissent comme des barrières supplémentaires pour contrôler et valider l'accès des agents aux données sensibles.

## Détection des menaces et audits continus

Face à l'évolution rapide des cybermenaces, Chrome intègre une surveillance en temps réel pour détecter et prévenir les attaques d'injection de prompts. Ces injections exploitent notamment des contenus malveillants ciblant les capacités analytiques et décisionnelles des agents IA. En surveillant activement ces menaces, Chrome s'appuie sur :

- Une combinaison d'analyse des prompts et des contenus via **Safe Browsing**, le système de protection de Google contre les sites dangereux et les logiciels malveillants.
- L'interruption automatique des actions initiées par des contenus suspects avant qu'elles ne puissent affecter l'utilisateur.

En complément, Chrome adopte une approche proactive avec des audits réguliers utilisant des simulations d'attaques ("Red-Teaming"). Ces tests reposent sur la génération automatisée de sites malveillants et l'utilisation de modèles de langage avancés pour reproduire des scénarios d'attaque réalistes. Grâce à son système auto-update, Chrome est capable de diffuser rapidement des correctifs pour renforcer ses défenses en permanence.

## Collaboration et récompenses pour la recherche

Google met également en avant la coopération avec la communauté de chercheurs en cybersécurité afin de perfectionner les mécanismes de sécurité liés à ces capacités agentiques. Le programme de récompenses de vulnérabilité (Vulnerability Rewards Program, VRP) a été étendu pour inclure les scénarios impliquant l'IA.

Des primes allant jusqu'à 20 000 dollars sont attribuées à ceux qui identifient et documentent des failles critiques mettant en danger la sécurité des agents de Chrome. L'objectif est de capitaliser sur l'intelligence collective pour anticiper les menaces inédites et améliorer les défenses globales du navigateur.

## Vers un futur sécurisé avec Chrome

La sécurisation des capacités agentiques s'inscrit dans une démarche durable, combinant des solutions techniques avancées et des performantes démontrées. Les fondations de Chrome reposent sur une isolation stricte des origines, des modèles IA autonomes pour vérifier les décisions et une collaboration active avec les experts en cybersécurité.

Cependant, les défis restent complexes dans un environnement où les menaces évoluent rapidement. Les attaques indirectes, qui ciblent les interactions critiques ou exploitent des fonctionnalités d'IA mal comprises, nécessiteront une vigilance constante des équipes de développement.

Chrome illustre un équilibre réfléchi entre innovation et sécurité, tout en offrant une navigation fluide et fiable aux utilisateurs. Ces mesures représentent une étape importante vers le déploiement sûr et généralisé des agents web dans les navigateurs modernes.

[source](http://security.googleblog.com/2025/12/architecting-security-for-agentic.html)