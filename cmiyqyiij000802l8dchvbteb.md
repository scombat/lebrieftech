---
title: "Intégrer Rust WebAssembly dans Vite + React : Exemple du jeu de la vie"
seoTitle: "Intégrer Rust WebAssembly avec Vite + React : Exemple du jeu de la vie"
seoDescription: "Découvrez comment intégrer WebAssembly généré par Rust dans un projet Vite + React pour moderniser le jeu de la vie. Guide complet et adaptatif."
datePublished: Tue Dec 09 2025 15:40:22 GMT+0000 (Coordinated Universal Time)
cuid: cmiyqyiij000802l8dchvbteb
slug: integrer-rust-webassembly-vite-react-exemple-jeu-vie
canonical: https://dev.to/jambochen/using-rust-webassembly-in-vite-react-a-modern-game-of-life-example-hde

---

# Intégrer Rust WebAssembly dans Vite + React : Exemple du jeu de la vie

## TL;DR

- Rust et WebAssembly offrent des performances élevées pour des applications modernes grâce à leur compatibilité avec les navigateurs.
- Vous pouvez utiliser Vite et React pour intégrer facilement des modules WebAssembly compilés depuis Rust dans un projet TypeScript.
- Des plugins tels que `vite-plugin-wasm` simplifient la configuration pour charger et exécuter du WebAssembly dans le frontend.
- En suivant cet article, vous développerez un projet React dynamique basé sur le célèbre jeu de la vie, avec un backend Rust compilé en WebAssembly.
- La bibliothèque `wasm-bindgen` facilite la communication entre votre code Rust et JavaScript/TypeScript.

## Structure du projet

Avant de commencer, il est essentiel de comprendre comment le projet sera structuré. L'objectif est de combiner un frontend React basé sur TypeScript avec un backend Rust compilé en WebAssembly.

Voici la structure de base attendue :

```
project-root/
├── src/
│   ├── App.tsx           # Composant principal React
│   ├── index.tsx         # Point d'entrée principal
├── rust/
│   ├── src/
│   │   ├── lib.rs        # Code Rust avec la logique du jeu de la vie
│   └── Cargo.toml        # Dépendances Rust (wasm-bindgen, etc.)
├── public/
│   └── index.html        # Fichier HTML principal avec le script WebAssembly
├── package.json          # Dépendances JS
└── vite.config.ts        # Configuration Vite
```

La partie Rust encapsulera la logique du jeu de la vie, tandis que le frontend React affichera la grille et permettra d'interagir avec le backend via WebAssembly.

## Créer un projet Vite + React + TypeScript

Commencez par initialiser un nouveau projet Vite accompagné de React et TypeScript. Exécutez les commandes suivantes :

```bash
npm create vite@latest my-project --template react-ts
cd my-project
npm install
```

Ce processus crée un boilerplate avec la structure standard d'un projet Vite. Vous pouvez désormais installer des dépendances supplémentaires si nécessaire, comme des outils pour charger du WebAssembly.

Ajoutez également `vite-plugin-top-level-await` et `vite-plugin-wasm`, qui simplifient l'import des modules WebAssembly. Installez-les avec :

```bash
npm install vite-plugin-wasm vite-plugin-top-level-await
```

## Développer un backend WebAssembly avec Rust

Rust sera utilisé pour implémenter les règles du jeu de la vie. Si vous n'avez pas encore de configuration Rust sur votre machine, installez Rust avec [Rustup](https://rustup.rs/).

Ensuite, créez une nouvelle bibliothèque Rust dans le dossier `rust/` :

```bash
cd rust
cargo new --lib game_of_life
```

Modifiez le fichier `Cargo.toml` pour ajouter les dépendances nécessaires :

```toml
[dependencies]
wasm-bindgen = "0.2"
```

Le code principal sera écrit dans `src/lib.rs`. Voici une logique simplifiée pour le jeu de la vie :

```rust
use wasm_bindgen::prelude::*;

#[wasm_bindgen]
pub struct GameOfLife {
    width: usize,
    height: usize,
    cells: Vec<u8>,
}

#[wasm_bindgen]
impl GameOfLife {
    pub fn new(width: usize, height: usize) -> GameOfLife {
        let cells = vec![0; width * height];
        GameOfLife { width, height, cells }
    }

    pub fn tick(&mut self) {
        // Exemple de logique simplifiée
        let mut new_cells = self.cells.clone();
        for i in 0..self.cells.len() {
            let count = self.count_neighbors(i);
            new_cells[i] = match (self.cells[i], count) {
                (1, 2 | 3) => 1,
                (0, 3) => 1,
                _ => 0,
            };
        }
        self.cells = new_cells;
    }

    pub fn get_cells(&self) -> Vec<u8> {
        self.cells.clone()
    }

    fn count_neighbors(&self, index: usize) -> usize {
        // Simplification pour compter les voisins
        0
    }
}
```

## Compiler et intégrer Rust en WebAssembly

La compilation en WebAssembly se fait avec le `wasm-bindgen`. Ajoutez une commande pour générer les fichiers wasm :

```bash
wasm-pack build --target web
```

Cela produit un module WebAssembly dans un sous-dossier `pkg/`. Copiez ce dossier dans le répertoire `public/` de votre projet Vite.

## Configurer et utiliser des plugins Vite pour wasm

Le fichier `vite.config.ts` doit être configuré pour intégrer les plugins nécessaires. Voici un exemple :

```typescript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import wasm from 'vite-plugin-wasm';
import topLevelAwait from 'vite-plugin-top-level-await';

export default defineConfig({
  plugins: [
    react(),
    wasm(),
    topLevelAwait(),
  ],
});
```

Cela permettra une importation sans effort des fichiers WebAssembly directement dans votre code TypeScript.

## Exemple React : Charger et exécuter Rust WebAssembly

Dans votre fichier React principal (`src/App.tsx`), chargez le module wasm généré et utilisez-le comme backend :

```typescript
import React, { useEffect, useState } from 'react';
import init, { GameOfLife } from '../public/pkg/game_of_life';

const App = () => {
  const [game, setGame] = useState<GameOfLife | null>(null);
  const [cells, setCells] = useState<number[]>([]);

  useEffect(() => {
    const loadWasm = async () => {
      await init();
      const newGame = GameOfLife.new(50, 50);
      setGame(newGame);
      setCells(newGame.get_cells());
    };
    loadWasm();
  }, []);

  const handleTick = () => {
    if (game) {
      game.tick();
      setCells(game.get_cells());
    }
  };

  return (
    <div>
      <button onClick={handleTick}>Next Generation</button>
      <div style={{ display: 'grid', gridTemplateColumns: `repeat(50, 10px)` }}>
        {cells.map((cell, index) => (
          <div
            key={index}
            style={{
              width: '10px',
              height: '10px',
              backgroundColor: cell ? 'black' : 'white',
            }}
          />
        ))}
      </div>
    </div>
  );
};

export default App;
```

Ce code intègre les fonctionnalités du jeu de la vie, récupère les états depuis le backend Rust, et met à jour la grille dans React.

Ce tutoriel vous fournit une base solide pour travailler avec Rust et WebAssembly dans un projet JavaScript moderne. Vous pouvez étendre cette structure pour d'autres cas d'utilisation exigeant des performances élevées.

[source](https://dev.to/jambochen/using-rust-webassembly-in-vite-react-a-modern-game-of-life-example-hde)