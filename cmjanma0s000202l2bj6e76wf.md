---
title: "Créer un schéma Solana avec Lumos en seulement 5 minutes"
seoTitle: "Créer un schéma Solana avec Lumos en seulement 5 minutes"
seoDescription: "Découvrez comment configurer un schéma Solana avec Lumos en 5 minutes. Type-safe Rust + TypeScript pour vos applications Solana."
datePublished: Wed Dec 17 2025 23:40:06 GMT+0000 (Coordinated Universal Time)
cuid: cmjanma0s000202l2bj6e76wf
slug: creer-schema-solana-lumos-5-minutes
canonical: https://dev.to/getlumos/lumos-in-5-minutes-your-first-solana-schema-3k7p

---

# Créer un schéma Solana avec Lumos en seulement 5 minutes

## TL;DR

- Lumos CLI simplifie la création de schémas type-safe pour les applications Solana, intégrant Rust et TypeScript.
- La génération automatique de code facilite l'implémentation avec Anchor et assure une sérialisation rapide via Borsh.
- Ce guide couvre l'installation, l'initialisation d'un projet, la définition d'un schéma, la génération de code et son intégration.

## Installation de Lumos CLI

Avant de commencer, vous devez installer l'outil Lumos CLI sur votre machine. Il est nécessaire d'avoir **Node.js** et **npm** ou **yarn** pour procéder. Voici les étapes :

1. Ouvrez votre terminal.
2. Exécutez la commande suivante pour installer Lumos :

```bash
npm install -g lumos
```

Si vous préférez utiliser yarn :

```bash
yarn global add lumos
```

Une fois installé, vous pouvez vérifier que Lumos est correctement configuré en utilisant la commande :

```bash
lumos --version
```

Cette commande devrait afficher le numéro de version de Lumos.

## Initialisation du projet avec Lumos

Pour démarrer un nouveau projet Lumos, suivez les étapes ci-dessous :

1. Créez un dossier pour votre projet :

```bash
mkdir mon-projet-solana
cd mon-projet-solana
```

2. Initialisez un projet Lumos avec la commande suivante :

```bash
lumos init
```

Cette commande génère une structure de projet basique incluant les fichiers nécessaires pour configurer vos schémas et paramètres.

## Écriture de votre schéma Lumos

Une fois le projet initialisé, l'étape suivante consiste à définir votre schéma dans un fichier dédié. Voici comment procéder :

1. Ouvrez le fichier généré `schema.ts` dans votre éditeur de code.
2. Utilisez les types Lumos pour définir les structures de données que vous souhaitez partager entre Rust et TypeScript. Par exemple :

```typescript
import { Struct, u16, string } from "lumos";

export const MySchema = new Struct("MySchema", {
  id: u16,
  name: string,
});
```

Dans cet exemple :
- `u16` est un type entier sans signe sur 16 bits.
- `string` est utilisé pour les chaînes de caractères.

Lumos prend en charge plusieurs types de données, y compris les types personnalisés, ce qui permet une flexibilité maximale dans la définition de vos schémas.

## Générer du code Rust et TypeScript

Après avoir écrit votre schéma, Lumos peut générer automatiquement le code nécessaire en Rust et TypeScript. Cela garantit la compatibilité directe entre ces deux langages et facilite la sérialisation des données avec Borsh.

1. Exécutez la commande suivante pour générer le code à partir de votre schéma :

```bash
lumos generate
```

2. Lumos crée des fichiers sous les dossiers prédéfinis `src/rust/` et `src/typescript/`, avec la représentation correspondante de vos schémas dans chaque langage.

    - Dans **Rust**, le fichier généré inclut les structures appropriées et les fonctions de sérialisation/désérialisation via Borsh.
    - Dans **TypeScript**, le fichier comporte les définitions de types et les fonctions nécessaires pour manipuler et interpréter les données.

## Utiliser le code généré dans votre projet

Les fichiers générés peuvent maintenant être intégrés directement dans votre projet Solana, qu'il s'agisse d'un programme de contrat intelligent en Anchor ou d'une application Web client.

### Intégration avec Anchor en Rust

Si vous travaillez avec Anchor pour vos contrats Solana, incluez simplement le fichier généré dans votre projet en ajoutant une référence au module dans votre code :

```rust
mod my_schema;

use my_schema::MySchema;

fn process_instruction() {
    let data = MySchema::deserialize(&input_data)?;
    // Utilisez vos données ici
}
```

### Utilisation côté TypeScript

Dans une application client basée sur TypeScript, vous pouvez importer la définition de schéma générée et gérer les données avec les fonctions fournies :

```typescript
import { MySchema } from "./typescript/my_schema";

const data = new MySchema({ id: 1, name: "Exemple" });
const serialized = data.serialize();
console.log(serialized);
```

Cette approche assure la cohérence des types entre le frontend et le backend, simplifie la sérialisation/désérialisation et réduit les risques d'erreurs de typage.

Avec Lumos, créer un schéma type-safe compatible entre Rust et TypeScript devient une tâche rapide et simple. Vous êtes désormais prêt à implémenter vos propres schémas dans vos projets Solana, en assurant fiabilité, performance et interopérabilité.

[source](https://dev.to/getlumos/lumos-in-5-minutes-your-first-solana-schema-3k7p)