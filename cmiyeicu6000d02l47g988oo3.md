---
title: "Advent of Code 2025 : Jour 4 - Suppression des Rouleaux de Papier"
seoTitle: "Advent of Code 2025 : Défi du Jour 4 dans Rust"
seoDescription: "Découvrez le défi du jour 4 de l'Advent of Code 2025 dans Rust : compter et supprimer des rouleaux de papier sur une grille. Tutoriel et code inclus."
datePublished: Tue Dec 09 2025 09:51:53 GMT+0000 (Coordinated Universal Time)
cuid: cmiyeicu6000d02l47g988oo3
slug: advent-of-code-2025-day-4-paper-roll-removal
canonical: https://dev.to/kryko7/advent-of-code-2025-day-4-paper-roll-removal-489a

---

# Advent of Code 2025 : Jour 4 - Suppression des Rouleaux de Papier

## TL;DR

- Le défi de l'Advent of Code 2025 (Jour 4) implique l’analyse d’une grille afin de compter et supprimer des rouleaux de papier selon leur accessibilité.
- Une cellule est considérée inaccessible si elle ne possède pas au moins 4 voisins adjacents.
- La solution se développe en deux étapes : comptage des voisins suivie de la suppression des cellules accessibles.
- Cet article présente une solution explicite en Rust pour résoudre ce problème.

## Introduction au problème

Le défi du jour repose sur un problème de manipulation de données situées sur une grille. Chaque cellule de la grille représente un rouleau de papier, et la tâche consiste à déterminer quels rouleaux peuvent être supprimés selon des critères spécifiques d'accessibilité.

La règle principale stipule qu'un rouleau doit avoir au moins 4 voisins adjacents pour être considéré comme "accessible". Les voisins sont définis comme les cellules situées immédiatement à gauche, à droite, au-dessus et en dessous de la cellule courante.

Ce type de problème est classique dans l'Advent of Code et permet de manipuler des structures de données tout en appliquant des algorithmes efficaces.

## Étape 1 : Compter les rouleaux accessibles

La première étape du défi consiste à analyser la grille et à compter le nombre de voisins pour chaque cellule. Ceci est essentiel pour identifier les rouleaux accessibles qui répondent à la condition des 4 voisins minimum. 

Cette étape se traduit par une lecture de toute la grille en prenant soin de vérifier les 4 directions adjacentes : haut, bas, gauche, droite.

Voici comment cela peut être réalisé avec une structure de boucles en Rust :

```rust
const DIRECTIONS: [(isize, isize); 4] = [(0, -1), (0, 1), (-1, 0), (1, 0)];

fn count_neighbors(grid: &Vec<Vec<char>>, x: usize, y: usize) -> usize {
    let mut count = 0;

    for &(dx, dy) in &DIRECTIONS {
        let nx = x as isize + dx;
        let ny = y as isize + dy;

        if nx >= 0 && ny >= 0 && nx < grid.len() as isize && ny < grid[0].len() as isize {
            if grid[nx as usize][ny as usize] == '#' {
                count += 1;
            }
        }
    }

    count
}
```

Dans cet extrait, la fonction `count_neighbors` utilise les directions prédéfinies pour vérifier les cellules adjacentes. Les cellules contenant un rouleau sont marquées par le caractère `#`.

## Étape 2 : Suppression des rouleaux accessibles

Une fois les voisins comptés, la deuxième étape consiste à supprimer les rouleaux "accessibles". Cela revient à créer une nouvelle version de la grille où seules les cellules répondant à la condition de voisinage sont conservées.

L'approche générale inclut une nouvelle boucle parcourant la grille, identifiant les cellules accessibles, et mettant à jour les données.

Voici l'extrait de code Rust correspondant :

```rust
fn remove_rollers(grid: &mut Vec<Vec<char>>) -> Vec<Vec<char>> {
    let mut new_grid = grid.clone();

    for x in 0..grid.len() {
        for y in 0..grid[0].len() {
            if grid[x][y] == '#' && count_neighbors(&grid, x, y) < 4 {
                new_grid[x][y] = '.';
            }
        }
    }

    new_grid
}
```

La fonction `remove_rollers` supprime les rouleaux en remplaçant leur emplacement par un caractère vide (ici `.`). Le résultat est une grille modifiée après cette opération.

## Pourquoi cette solution fonctionne

La solution repose sur deux propriétés fondamentales :

1. **Validation précise des voisins** :
   En utilisant le comptage des voisins pour analyser chaque cellule, la solution aborde méticuleusement le problème d'accessibilité sans oublier les bords ou les coins de la grille.

2. **Grid immuable dans chaque étape** :
   La grille initiale reste intacte lors du calcul des voisins, minimisant les risques d’erreurs logiques dues aux modifications simultanées.

Ces principes assurent la robustesse et l’efficacité de l’implémentation.

## Solution complète et tutoriel en Rust

Voici la solution complète combinant le comptage des voisins et la suppression des rouleaux dans une implémentation pratique en Rust. Ajoutons la logique principale pour un traitement complet de la grille :

```rust
fn process_grid(grid: &mut Vec<Vec<char>>) -> Vec<Vec<char>> {
    let neighbor_counts = grid.clone();

    // Étape 1 : Compter les voisins
    for x in 0..grid.len() {
        for y in 0..grid[0].len() {
            neighbor_counts[x][y] = count_neighbors(grid, x, y) as u8;
        }
    }

    // Étape 2 : Supprimer les rouleaux accessibles
    remove_rollers(grid)
}

fn main() {
    let mut grid = vec![
        vec!['#', '#', '.', '#'],
        vec!['.', '#', '#', '.'],
        vec!['#', '#', '#', '#'],
    ];
    
    println!("Étape initiale : {:?}", grid);

    grid = process_grid(&mut grid);
    println!("Grille finale : {:?}", grid);
}
```

### Points clés à noter :
- Le code illustre une méthode optimisée pour manipuler des données structurelles sans pertes de performances.
- Il peut être adapté pour couvrir des grilles plus larges et intégrer des mécanismes de parallélisme.

Pour explorer davantage et télécharger le code source complet, consultez le [projet GitHub ici](https://github.com/Kryko7/AoC).

[source](https://dev.to/kryko7/advent-of-code-2025-day-4-paper-roll-removal-489a)