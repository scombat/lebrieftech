---
title: "Optimisation des performances de Kyverno CLI : récit de mon mentorat LFX"
seoTitle: "Optimisation des performances de Kyverno CLI : parcours de mentorat LFX"
seoDescription: "Découvrez comment un mentorat LFX a permis d'améliorer Kyverno CLI, réduisant les temps d'exécution de 15 minutes à 1 à 2 secondes seulement."
datePublished: Wed Dec 10 2025 12:07:17 GMT+0000 (Coordinated Universal Time)
cuid: cmizysclg000902l84zhg70jd
slug: optimisation-kyverno-cli-performance-mentorat-lfx
canonical: https://www.cncf.io/blog/2025/12/10/optimizing-kyverno-cli-performance-my-lfx-mentorship-journey/

---

# Optimisation des performances de Kyverno CLI : récit de mon mentorat LFX

## TL;DR

- Kyverno est un moteur de gestion de politiques cloud-native pour Kubernetes garantissant sécurité et conformité.
- Le mentorat LFX a permis de résoudre des problèmes de performance critiques dans Kyverno CLI, réduisant les temps d'exécution de 15 minutes à seulement 1-2 secondes.
- Trois approches ont été mises en œuvre : chargement parallèle des ressources, mise en cache des namespaces et traitement différé des mappers REST.
- Le projet met en lumière l'importance de la collaboration dans l'open source.

## Qu'est-ce que Kyverno ?

Kyverno est un moteur de gestion de politiques cloud-native spécifiquement conçu pour Kubernetes. En tant que contrôleur d'admission dynamique, il applique automatiquement des politiques codifiées aux ressources Kubernetes. Ces politiques permettent de valider, muter ou générer des configurations, garantissant ainsi la sécurité et la conformité des environnements.

Cet outil est essentiel aux équipes utilisant Kubernetes à grande échelle et cherchant à automatiser les meilleures pratiques tout en renforçant la sécurité opérationnelle.

## Introduction au mentorat LFX

Le programme de mentorat LFX est une initiative dédiée à la collaboration en open source, offrant aux participants l'opportunité de travailler sur des projets techniques. Pendant 12 semaines, étudiants et professionnels contribuent directement à des projets reconnus, développant leurs compétences techniques tout en s'immergeant dans l'écosystème collaboratif.

C'est dans ce cadre qu'Abhishek Dhiman a rejoint Kyverno pour résoudre un problème de performance majeur au sein du projet. Sa mission a consisté à repenser les structures existantes pour rendre la CLI de Kyverno plus efficace sur des clusters volumineux.

## Détection du problème

Kyverno CLI propose la commande `kyverno apply`, utilisée pour appliquer et valider les politiques sur un ensemble de ressources Kubernetes. Si cette fonctionnalité s'avère rapide pour des groupes restreints de ressources (1-2 secondes), son exécution devient extrêmement lente sur des clusters contenant des milliers de ressources. Sur des environnements complexes, les temps d'exécution pouvaient atteindre jusqu'à 15 minutes.

Trois goulets d'étranglement principaux ont été identifiés :

1. **Chargement séquentiel des ressources** : Chaque ressource était chargée individuellement, créant des délais importants.
2. **Requêtes répétitives des namespaces** : Les informations des namespaces étaient récupérées plusieurs fois inutilement.
3. **Découverte anticipée des mappers REST** : Les remappings étaient effectués pour chaque ressource sans discernement, ajoutant une surcharge inutile.

## Solutions technologiques mises en œuvre

### Chargement parallèle des ressources

Pour accélérer le processus, une approche de chargement par lots concurrentiels a été adoptée. Un pool de travailleurs a été introduit, accompagné de nouvelles options configurables :

- `--concurrent` : Permet de définir le nombre de travailleurs simultanés.
- `--batch-size` : Configure la taille des lots de ressources à traiter.

En complément, un flag `--show-performance` a été ajouté pour aider les utilisateurs à visualiser les performances lors de l'exécution.

### Mise en cache des namespaces

Pour éliminer les requêtes redondantes aux namespaces, une solution de mise en cache a été mise en œuvre. Les données sont désormais stockées localement, réduisant les appels répétés à l'API Kubernetes et accélérant le traitement global.

### Chargement différé des mappers REST

Les opérations de découverte des mappers REST ont été adaptées pour fonctionner de manière paresseuse. Ces remappings ne sont désormais effectués que lorsque nécessaire, limitant la surcharge liée à cette fonctionnalité sur les environnements complexes.

## Résultats et impact

Les solutions apportées ont significativement amélioré l'expérience utilisateur de Kyverno CLI :

- **Réduction massive des temps d'exécution** : Le temps pour appliquer des politiques sur des clusters volumineux est passé de 15 minutes à seulement 1-2 secondes, soit une réduction de 99 %.
- **Performances optimisées sur les grands clusters** : Le chargement parallèle des ressources a permis une accélération phénoménale d'environ 80 %.
- **Paramètres configurables** : Les nouvelles options permettent une personnalisation fine, idéale pour les déploiements en production.

## Réflexions et apprentissages

L'expérience d'Abhishek Dhiman dans le cadre du programme LFX met en évidence l'importance des contributions open source et du mentorat dans l'évolution des projets techniques. La collaboration constante avec la communauté Kyverno a été clé pour surmonter les défis techniques et proposer des solutions pérennes.

Même après la fin du programme, Abhishek continue de contribuer activement au projet, renforçant le lien entre apprentissage et impact réel dans l'open source.

## Key takeaways

Grâce aux améliorations apportées, Kyverno CLI est désormais mieux armé pour répondre aux besoins des environnements Kubernetes complexes. Les changements, en plus d'améliorer les performances, soulignent la force du mentorat pour résoudre des problématiques techniques.

## À surveiller / Risques

Malgré ces avancées, il reste essentiel de continuer les tests sur des environnements variés. Les nouvelles fonctionnalités nécessitent une intégration robuste ainsi qu'une maintenance régulière, surtout dans le cadre de déploiements critiques ou à très grande échelle.



[source](https://www.cncf.io/blog/2025/12/10/optimizing-kyverno-cli-performance-my-lfx-mentorship-journey/)