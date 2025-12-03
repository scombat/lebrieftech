---
title: "Un aperçu de SeaORM 2.0 : la nouvelle génération de l’ORM Rust"
seoTitle: "Découvrez les nouveautés de SeaORM 2.0 et ses avancées impressionnantes"
seoDescription: "SeaORM 2.0 propose des améliorations essentielles pour renforcer l’expérience utilisateur et offrir des fonctionnalités avancées, révolutionnant l’écosystème Rust."
datePublished: Wed Dec 03 2025 11:07:41 GMT+0000 (Coordinated Universal Time)
cuid: cmipwkqnl000202l7cg09741z
slug: un-apercu-de-seaorm-20
canonical: https://dev.to/seaql/a-sneak-peek-at-seaorm-20-3473

---

# Un aperçu de SeaORM 2.0 : la nouvelle génération de l’ORM Rust

## TL;DR
- SeaORM 2.0 introduit des améliorations majeures pour une meilleure ergonomie et convivialité.
- Support des sélections imbriquées, y compris sur tous les modèles ordinaires.
- Nouvelle gestion des clés uniques multipartites, facilitant la manipulation des bases de données complexes.
- Fonctionnalités avancées telles que le macro `raw_sql!` pour du SQL sécurisé et flexible.
- Intégration d’un moteur de contrôle d’accès basé sur les rôles (RBAC) et un panneau d’administration professionnel avec SeaORM Pro.

## Contexte et pertinence

SeaORM, le framework ORM basé sur Rust, a pris son essor depuis la sortie de la version 1.0. Grâce à de nombreuses fonctionnalités ajoutées au cours de son évolution, il a su répondre aux besoins des développeurs tout en maintenant une grande stabilité. Toutefois, cette croissance rapide engendrait quelques incohérences et complexités dans son utilisation. La version 2.0 se positionne comme une étape nécessaire pour consolider sa base et améliorer l’expérience utilisateur en profondeur.

## Améliorations dans SeaORM 1.0

### Sélection imbriquée
Un des ajouts les plus demandés dans SeaORM est la sélection imbriquée, permettant de travailler avec des modèles imbriqués, des alias et des `ActiveEnum`. Cette fonctionnalité simplifie la manipulation des données complexes tout en offrant une souplesse accrue.

### Transformation des modèles partiels
Les modèles partiels peuvent désormais être directement convertis en modèles actifs, facilitant les processus d’insertion ou de mise à jour des données. Cette amélioration réduit les étapes nécessaires dans les workflows de manipulation des données.

### Insertion de colonnes non uniformes
SeaORM permet une meilleure flexibilité dans l’insertion des modèles actifs. Les colonnes absentes dans un ensemble sont automatiquement remplies avec des valeurs `NULL`, simplifiant la gestion des schémas de données variés.

### Prise en charge des types PostgreSQL avancés
SeaORM a ajouté un support pour PgVector et IpNetwork dans PostgreSQL. Ces options sont activées via les flags de fonctionnalités `postgres-vector` et `with-ipnetwork`, permettant d’exploiter des types avancés pour des cas d’utilisation spécifiques.

## Nouvelles fonctionnalités dans SeaORM 2.0

### Sélection imbriquée sur tous les modèles ordinaires
La capacité de sélection imbriquée s’étend désormais à tous les modèles standards grâce à la dérive du trait `PartialModelTrait`. Cela permet aux développeurs de manipuler plus facilement les relations complexes sans ajustements supplémentaires.

### Type wrapper comme clé primaire
Les types dérivés utilisant `DeriveValueType` peuvent désormais servir de clés primaires. Ce changement renforce la robustesse des bases de données et la flexibilité des modèles pour des applications fortement typées.

### Clés uniques multipartites
SeaORM 2.0 introduit la déclaration de contraintes uniques sur plusieurs colonnes, une fonctionnalité essentielle pour modéliser les bases de données avec des relations complexes tout en respectant les règles d’intégrité.

### Champs JSON manquants
Avec la fonction `ActiveModel::from_json`, les champs absents dans les données JSON sont automatiquement pris en charge. Cela simplifie grandement l’intégration avec les API REST et la manipulation des données utilisateur.

## Fonctionnalités avancées excitantes

### Macro `raw_sql!` pour SQL ergonomique
La macro `raw_sql!` permet l’exécution de requêtes SQL tout en garantissant une sécurité et une flexibilité accrues. Par exemple, elle prend en charge :
- L’interpolation imbriquée dans les requêtes complexes.
- La pagination des requêtes SQL pour des résultats organisés en lots.

Grâce à cette fonctionnalité, SeaORM facilite les requêtes personnalisées tout en minimisant le risque d’erreurs liées au SQL brut.

### Contrôle d’accès basé sur les rôles (RBAC)
La version 2.0 introduit un moteur RBAC hiérarchique, permettant aux développeurs d’établir des permissions personnalisées pour les utilisateurs. Ce moteur audite les requêtes avant leur exécution et utilise une connexion restreinte pour protéger les données sensibles.

## SeaORM Pro : Panneau d’administration professionnel

SeaORM Pro simplifie la création d’outils d’administration pour les développeurs. Ce panneau offre :
- Des fonctionnalités CRUD complètes basées sur les interactions de bases de données.
- Une infrastructure frontend construite avec React et une intégration GraphQL.
- Un système de personnalisation accessible via des fichiers TOML.

SeaORM Pro vise à accélérer le développement en éliminant la nécessité de maîtriser l’ensemble de l’écosystème frontend.

## À surveiller

La transition vers SeaORM 2.0 implique des ajustements importants en raison des changements de compatibilité. Par exemple :
- Certains comportements par défaut peuvent ne plus être pris en charge et nécessiter des modifications de code.
- Cette mise à jour s’accompagne de la sortie de SeaQuery 1.0, offrant une intégration améliorée pour des requêtes SQL complexes.

## À retenir

SeaORM 2.0 représente une étape clé dans l’évolution des ORM basés sur Rust. En améliorant la robustesse, la flexibilité, et en introduisant des outils comme le macro `raw_sql!` et le moteur RBAC, cette nouvelle version offre une expérience utilisateur nettement supérieure. Pour les développeurs travaillant avec Rust et SQL, SeaORM 2.0 devient un choix incontournable pour gérer des bases de données modernes et performantes.

[source](https://dev.to/seaql/a-sneak-peek-at-seaorm-20-3473)