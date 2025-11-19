---
title: "Découvrez les nouvelles fonctionnalités de métadonnées dans Amazon SageMaker Catalog"
seoTitle: "Améliorez la découvrabilité avec les nouvelles métadonnées dans Amazon SageMaker Catalog"
seoDescription: "Amazon SageMaker introduit des outils de gestion de métadonnées d'entreprise pour renforcer la classification, la gouvernance et la recherche des données."
datePublished: Wed Nov 19 2025 19:26:34 GMT+0000 (Coordinated Universal Time)
cuid: cmi6e8dh7000002l3eqsd7kly
slug: nouvelles-metadonnees-amazon-sagemaker-catalog
canonical: https://aws.amazon.com/blogs/aws/new-business-metadata-features-in-amazon-sagemaker-catalog-to-improve-discoverability-across-organizations/

---

# Découvrez les nouvelles fonctionnalités de métadonnées dans Amazon SageMaker Catalog

## Améliorez la gestion avec les métadonnées au niveau des colonnes

La gestion des métadonnées est essentielle pour optimiser l'utilisation des données au sein des entreprises. Amazon SageMaker Catalog introduit une nouveauté importante : les **formulaires de métadonnées au niveau des colonnes**, permettant aux organisations de mieux documenter leurs données pour une administration plus efficace et systématique.

### Principales nouveautés des formulaires au niveau des colonnes

- **Formulaires personnalisables** : Amazon SageMaker Catalog offre désormais la possibilité de configurer des formulaires qui s’appliquent directement aux colonnes des jeux de données. Ces formulaires permettent de capturer des détails contextuels et de documenter les informations de manière enrichie à l’aide de Markdown.
  
```markdown
**Exemple d'utilisation des formulaires personnalisés :**
Nom de colonne : `produit_id`  
Description : "Identifiant unique du produit."  
Glossaire associé : "ID produit, utilisé dans les systèmes ERP."
```

- **Indexation en temps réel** : Les métadonnées ajoutées via les formulaires sont immédiatement indexées, offrant une recherche rapide et pertinente dans le catalogue.

- **Modification simplifiée** : Les utilisateurs peuvent accéder à leurs jeux de données, sélectionner des schémas, et éditer les descriptions directement via l’option "Afficher/Modifier" pour chaque colonne.

- **Interopérabilité accrue** : Les informations saisies dans les formulaires peuvent être exploitées pour rechercher efficacement les ressources à partir des noms de colonnes, des descriptions ou des termes associés dans un glossaire métier commun.

Ces évolutions permettent aux équipes d'accéder facilement à des informations bien structurées et enrichies, réduisant les frictions dans la gestion des données.

---

## Adoptez des règles strictes pour les glossaires

La standardisation des métadonnées d'entreprise devient de plus en plus essentielle pour garantir une documentation cohérente et conforme aux exigences métiers. Amazon SageMaker Catalog introduit des règles de glossaire pour assurer une utilisation homogène de la terminologie métier dans les descriptions des ressources.

### Fonctionnalités clés des nouvelles règles de glossaire

1. **Utilisation obligatoire de vocabulaires métiers** : Les nouvelles règles obligent les utilisateurs à associer des termes standardisés provenant d’un glossaire approuvé avant toute publication d’actif. Par exemple, chaque définition ou description doit suivre une terminologie commune et validée.

2. **Validation et contrôle automatisés** : Un système de vérification est intégré pour s’assurer que les actifs publiés respectent les termes exigés. En l’absence de termes obligatoires, le processus de publication est bloqué, préservant ainsi la cohérence des métadonnées.

3. **Configuration adaptée à vos besoins** : La gestion des règles est accessible via l’onglet "Gestion des domaines" du menu dédié à la gouvernance. Les administrateurs peuvent définir jusqu’à cinq termes requis pour chaque règle, garantissant la conformité aux standards métiers.

Avec ces règles en place, les organisations peuvent non seulement contrôler la qualité de leurs métadonnées, mais aussi s’assurer que les informations critiques sont uniformes et compréhensibles pour toutes les parties prenantes.

---

## Les avantages des nouvelles capacités d'Amazon SageMaker Catalog

Les nouvelles fonctionnalités d'Amazon SageMaker Catalog offrent une gamme d'avantages concrets pour les entreprises et les équipes qui cherchent à mieux gérer leurs métadonnées et à maximiser la valeur de leurs données.

### Standardisation des pratiques

Grâce aux formulaires de métadonnées détaillés et aux règles de glossaire, les entreprises peuvent établir des standards clairs pour la documentation des données. Cela favorise une cohésion entre les équipes, quel que soit leur domaine ou expertise.

### Recherche et découvrabilité optimisées

Les améliorations apportées à la gestion des métadonnées permettent d'accéder rapidement à des données pertinentes via des recherches en texte intégral dans le catalogue, même pour des détails au niveau des colonnes. Cela est particulièrement utile dans les environnements comportant de vastes volumes de données.

### Conformité et gouvernance renforcées

En imposant des règles de glossaire et en automatisant la validation des métadonnées, les organisations peuvent garantir que leurs données sont conformes aux réglementations sectorielles. Ces mécanismes contribuent également à éviter les erreurs dans la documentation.

### Réduction des efforts manuels

Les suggestions générées par l'IA pour la documentation des données réduisent considérablement le temps et les efforts nécessaires pour la gestion quotidienne des métadonnées. Cela permet aux équipes de se concentrer sur des activités à forte valeur ajoutée.

---

## Comment intégrer ces nouvelles fonctionnalités

Les nouvelles capacités d'Amazon SageMaker Catalog sont accessibles via les outils AWS CLI et AWS SDKs. Cela facilite leur intégration dans les flux de travail existants des entreprises et leur utilisation dans des solutions scalables d'analyse et de gouvernance des données.

Pour accéder à ces fonctionnalités, les utilisateurs doivent activer les options appropriées dans leur compte AWS et configurer les paramètres spécifiques adaptés à leurs besoins métier. Les guides disponibles sur le site d’AWS offrent une assistance complète pour démarrer avec ces outils et apprendre à les exploiter de manière optimale.

---

Avec l'ajout de ces points forts au catalogue Amazon SageMaker, les entreprises disposent désormais d’une solution innovante et évolutive pour relever les défis liés à la gouvernance des données. Ces améliorations facilitent la mise en œuvre de standards robustes tout en optimisant la découvrabilité et l'utilisation des ressources critiques.

Pour plus de détails, consultez l’annonce originale sur le site officiel d’AWS : [Nouvelles fonctionnalités de métadonnées d'entreprise dans Amazon SageMaker Catalog](https://aws.amazon.com/blogs/aws/new-business-metadata-features-in-amazon-sagemaker-catalog-to-improve-discoverability-across-organizations/).

[source](https://aws.amazon.com/blogs/aws/new-business-metadata-features-in-amazon-sagemaker-catalog-to-improve-discoverability-across-organizations/)