---
title: "Alpine Linux 3.23.0 : nouveautés et mise à jour"
seoTitle: "Alpine Linux 3.23.0 : Découvez les nouveautés et améliorations"
seoDescription: "Découvrez les nouveautés incontournables d'Alpine Linux 3.23.0 : mises à jour d'APK, remplacement de linux-edge par linux-stable et report de la fusion des dossiers /usr."
datePublished: Thu Dec 04 2025 19:37:40 GMT+0000 (Coordinated Universal Time)
cuid: cmiru8f42000802jv2dmues04
slug: alpine-linux-3-23-0-nouveautes-et-mises-a-jour
canonical: https://lwn.net/Articles/1049299/

---

# Alpine Linux 3.23.0 : nouveautés et mise à jour

## TL;DR
- La version 3.23.0 introduit des changements importants, notamment une mise à jour significative d'APK vers la version 3.0.
- Le noyau linux-edge est remplacé par linux-stable pour une gestion simplifiée et une meilleure stabilité.
- La fusion planifiée des dossiers `/usr` est reportée à une date ultérieure.

## Mise à jour d'APK vers la version 3.0

Alpine Package Keeper (APK), le gestionnaire de packages natif d'Alpine Linux, bénéficie d’une mise à niveau majeure avec le passage à la version 3.0. Cette mise à jour, qui s’inscrit dans une démarche d’amélioration continue, permet de mieux gérer les dépendances, d’optimiser les performances et de rendre l’installation des logiciels plus rapide et fluide. Les développeurs utilisant Alpine Linux dans leurs environnements de production apprécieront cette avancée, qui renforce la fiabilité des installations automatiques et simplifie la maintenance.

## Remplacement du noyau linux-edge par linux-stable

### Pourquoi ce changement ?
Le remplacement du noyau linux-edge par linux-stable fait partie des changements stratégiques de cette nouvelle version. Historiquement, linux-edge et linux-lts coexistaient, mais leurs configurations et leurs approches techniques étaient divergentes. Cela provoquait parfois des problèmes de compatibilité et une complexité accrue pour les utilisateurs.

### Qu’est-ce qui change avec linux-stable ?
Le nouveau noyau linux-stable hérite d’une configuration identique à celle du noyau linux-lts, tout en suivant les versions stables du noyau publiées sur [kernel.org](https://kernel.org). Cette unification des configurations simplifie considérablement la gestion des noyaux, réduit les risques d’incompatibilités et améliore la stabilité globale du système. Les utilisateurs de linux-edge devront migrer vers linux-stable, ce qui nécessitera une vérification méthodique de leurs configurations existantes.

## Report de la fusion des dossiers /usr

Prévue initialement pour la version 3.23.0, la fusion des répertoires `/usr` a été reportée à une prochaine mise à jour. Ce changement structurel aurait des implications importantes sur la hiérarchie des fichiers du système. Bien que le calendrier spécifique de cette transition n’ait pas encore été déterminé, il est essentiel pour les administrateurs et développeurs de surveiller de près les annonces futures.

Ce report offre du temps supplémentaire pour identifier les impacts techniques possibles et se préparer en conséquence à ce changement majeur. L’équipe derrière Alpine Linux s'engage à fournir plus d’informations et à planifier une mise en œuvre qui minimise les perturbations.

## Principales nouveautés d'Alpine Linux 3.23.0

La version 3.23.0 d'Alpine Linux marque un tournant avec des améliorations pensées pour simplifier la vie des développeurs et des administrateurs système :

- **Mise à jour d'APK :** Gestion des dépendances plus performante et expérience utilisateur améliorée.
- **Linux-stable :** Une consolidation bienvenue des noyaux qui améliore la stabilité et réduit les complication techniques.
- **Dossiers `/usr`:** Bien qu’un report ait été décidé, les implications futures de cette fusion promettent de transformer la structure du système de fichiers.

Cette nouvelle version met l’accent sur la stabilité, les performances et l’harmonisation, des aspects essentiels pour les professionnels dans les environnements exigeants comme les conteneurs et les systèmes embarqués. Les utilisateurs de linux-edge sont encouragés à adapter leurs configurations pour garantir une transition fluide vers linux-stable.



[source](https://lwn.net/Articles/1049299/)