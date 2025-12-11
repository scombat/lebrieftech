---
title: "Découvrez les nouveautés révolutionnaires de GitHub Actions"
seoTitle: "Les nouveautés clés de GitHub Actions en 2025"
seoDescription: "Découvrez comment GitHub Actions améliore ses performances et sa fiabilité grâce à une refonte complète, répondant aux besoins de la communauté des développeurs."
datePublished: Thu Dec 11 2025 17:51:24 GMT+0000 (Coordinated Universal Time)
cuid: cmj1qiq2x000402l50e6f7czl
slug: les-nouveautes-github-actions-2025
canonical: https://github.blog/news-insights/product-news/lets-talk-about-github-actions/

---

# Découvrez les nouveautés révolutionnaires de GitHub Actions

## TL;DR

- GitHub Actions a bénéficié d’une refonte complète de son architecture en 2025, améliorant considérablement ses performances et sa fiabilité.
- Des fonctionnalités très demandées comme les ancres YAML, un cache étendu et des workflows plus flexibles sont désormais disponibles.
- La plateforme gère plus de **71 millions de tâches par jour** grâce à une capacité de mise à l’échelle accrue.
- Des innovations centrées sur la flexibilité et l’expérience utilisateur sont prévues pour début 2026.

## Pourquoi une refonte était nécessaire

Introduit en 2018, GitHub Actions a rapidement séduit les développeurs en tant qu’outil clé d’automatisation CI/CD. Son adoption massive a cependant engendré des défis significatifs. En 2024, l’équipe Github a constaté plusieurs limitations :

- Fiabilité insuffisante : Throttling et temps d’exécution instables dans les workflows complexes.
- Incapacité à répondre à la forte demande, avec une architecture dépassée.
- Frameworks vieillissants ne permettant pas une évolution dynamique des fonctionnalités.

Face à une augmentation de l’utilisation de 35 % entre 2024 et 2025 (atteignant **11,5 milliards de minutes Actions**), une refonte était devenue impérative pour maintenir la qualité et élargir les capacités.

## Les améliorations majeures apportées en 2025

### Refonte de l’infrastructure backend

La reconstruction de l’architecture de GitHub Actions en 2025 a permis d’atteindre des résultats impressionnants. Parmi les objectifs majeurs de cette refonte :

- **Performance optimisée** : Triplement du nombre de tâches traitées quotidiennement.
- **Résilience accrue** : Réduction des limites de throttling et augmentation de la capacité de mise à l’échelle jusqu’à **10 fois** la configuration initiale.
- Intégration plus fluide pour les entreprises, avec une accélération de la gestion des workflows : certaines entreprises exécutent désormais **7 fois plus de tâches par minute**.

### Fonctionnalités clés ajoutées

#### Ancres YAML

GitHub Actions adopte enfin une fonctionnalité demandée par la communauté : les ancres YAML. Elles permettent de minimiser les répétitions dans les configurations de workflows grâce à une structure réutilisable. Exemples pratiques :

- Définir une valeur commune avec `&anchor` et la réutiliser à l’aide d’un alias `*alias`.
- Appliqué à des variables globales, des étapes répétées, ou des configurations complexes pour des tasks cohérentes et maintenables.

#### Modèles de workflow réutilisables

Un autre ajout clé concerne les modèles de workflow, notamment privés, hébergés au sein des dépôts `.github`. Cela simplifie la maintenance des configurations CI/CD en éliminant les duplications tout en permettant un partage contrôlé entre projets.

#### Workflows imbriqués améliorés

Pour les pipelines modulaires, GitHub Actions permet désormais une imbriquation et un appel réciproque jusqu’à **10 niveaux** avec **50 exécutions par workflow**. Cela offre une flexibilité inégalée pour gérer des process d’intégration plus complexes.

#### Cache étendu

Les limitations de cache précédentes ont été levées : les dépôts peuvent maintenant définir des caches dépassant **10 Go**. Cette évolution est particulièrement pertinente pour les projets volumineux tels que les monorepos, souvent exigeants en ressources.

#### Inputs supplémentaires dans `workflow_dispatch`

La capacité de configuration a été étendue avec la prise en charge de **25 inputs** programmables. Cela enrichit les scénarios d’automatisation et facilite la personnalisation des workflows à grande échelle.

#### Autres avancées

- Support pour les runners arm64 dans les dépôts publics, facilitant les builds sur différentes architectures matérielles.
- Compatibilité avec les nouvelles versions des systèmes d’exploitation (macOS 15 et Windows 2025).
- Développement initial d’un support pour des images personnalisées.

## Perspectives et innovations prévues pour 2026

### Améliorations à venir

GitHub envisage en 2026 une série de nouvelles fonctionnalités destinées à optimiser encore davantage l’expérience développeur :

1. Gestion des **fuseaux horaires** dans les tâches planifiées, pour synchroniser les workflows avec des équipes globales.
2. Utilisation de fonctions conditionnelles avancées telles que `case`, simplifiant les logiques complexes dans les expressions YAML.
3. Amélioration des performances pour les workflows complexes contenant plus de **300 jobs**, évitant les temps de charge prolongés.
4. Développement des **étapes parallèles**, permettant une exécution simultanée d’actions dans les workflows CI/CD.

Chaque amélioration est guidée par les retours de la communauté et les avancées des besoins métiers modernes.

## Comment contribuer au développement de GitHub Actions

GitHub reste attentif aux besoins de sa communauté, et son engagement en matière de collaboration est au cœur de sa stratégie. Plusieurs opportunités s’offrent aux développeurs souhaitant participer :

- **Voter pour les priorités** : Faites entendre votre voix sur les fonctionnalités les plus importantes.
- **Participer aux discussions publiques** disponibles sur [GitHub Discussions](https://github.com/orgs/community/discussions/categories/actions).

Une publication régulière de mises à jour et une transparence accrue dans le cycle de développement visent à maintenir une relation collaborative entre GitHub et ses utilisateurs.

## Importance de la refonte

La refonte de l’architecture de GitHub Actions n’est pas qu’une énième mise à jour technologique : elle marque une transition majeure dans la manière dont les développeurs gèrent leurs workflows CI/CD. Performances accrues, réduction des limites techniques, et une flexibilité inégalée redéfinissent l’expérience utilisateur. GitHub confirme ainsi son rôle moteur dans l’écosystème du développement logiciel. Les chemins tracés pour 2026 promettent encore plus d’innovation.

**Source :** [GitHub Blog](https://github.blog/news-insights/product-news/lets-talk-about-github-actions/)

[source](https://github.blog/news-insights/product-news/lets-talk-about-github-actions/)