---
title: "Advent of Code 2025 : Analyse des IDs produits invalides en Rust"
seoTitle: "Advent of Code : Résolution du défi Day 2 en Rust"
seoDescription: "Découvrez comment résoudre le défi 'Advent of Code 2025 Day 2: Gift Shop' en utilisant le langage Rust. Analyse des IDs produits répétés."
datePublished: Sun Dec 07 2025 16:54:03 GMT+0000 (Coordinated Universal Time)
cuid: cmivypkph000002lf0h90huiq
slug: advent-of-code-2025-day-2-rust
canonical: https://dev.to/kryko7/advent-of-code-2025-day-2-gift-shop-1lkn

---

# Advent of Code 2025 : Analyse des IDs produits invalides en Rust

## TL;DR

- Le défi consiste à analyser les IDs produits pour détecter des schémas invalides.
- En première partie, il faut identifier les IDs apparaissant exactement deux ou trois fois.
- La deuxième partie demande de trouver des IDs proches en ne s'écartant que d’un caractère.
- Rust est un langage adapté à la résolution de ce type de problème grâce à sa gestion de la mémoire et ses bibliothèques puissantes.
- Le défi met en lumière des points clés sur les algorithmes de traitement de chaînes et l’optimisation en développement.

## Le problème : Comprendre les IDs invalides

Le défi du jour dans l’Advent of Code 2025 met en scène une boutique de cadeaux où l’on doit vérifier des IDs produits. Chaque ID est une chaîne de caractères composée de lettres, et l’objectif est d’identifier des schémas spécifiques qui rendent un produit invalide. Deux parties de ce défi doivent être résolues :

1. La première partie s’intéresse aux répétitions exactes d’une lettre dans les IDs produits.
2. La seconde partie explore les IDs qui diffèrent uniquement par un caractère.

Ces problématiques exigent une approche efficace pour parcourir et analyser plusieurs chaînes, tout en gérant la performance. Rust, par son système de typage strict et ses outils pour manipuler les structures de données, est particulièrement bien adapté à ce genre de traitement.

## Partie 1 : Identifier les répétitions exactes

La première étape du défi demande d’étudier chaque ID pour comprendre si des lettres apparaissent exactement deux ou trois fois. Ces informations sont ensuite utilisées pour calculer un “checksum”, qui est le produit du nombre d’IDs avec deux répétitions et de ceux avec trois répétitions.

### Mise en œuvre en Rust

Pour cette partie, une stratégie clé consiste à utiliser une table de hachage (Rust fournit la structure `HashMap`) pour compter les occurrences de chaque caractère dans un ID. Voici le procédé :

1. Parcourir chaque ID donné.
2. Compter les occurrences de chaque caractère avec une table de hachage.
3. Vérifier si le ID contient des caractères avec exactement 2 ou 3 répétitions.
4. Accumuler les totaux pour produire le “checksum”.

Grâce à des structures comme `HashMap`, Rust offre la possibilité de gérer rapidement l’accès et les manipulations. Ce qui rend le processus à la fois clair et performant.

### Exemple de code possible

```rust
use std::collections::HashMap;

fn calculate_checksum(ids: Vec<&str>) -> (i32, i32) {
    let mut two_count = 0;
    let mut three_count = 0;

    for id in ids {
        let mut char_counts = HashMap::new();
        for c in id.chars() {
            *char_counts.entry(c).or_insert(0) += 1;
        }

        if char_counts.values().any(|&count| count == 2) {
            two_count += 1;
        }
        if char_counts.values().any(|&count| count == 3) {
            three_count += 1;
        }
    }

    (two_count, three_count)
}
```

Ce code illustre comment comptabiliser efficacement les occurrences de caractères pour chaque ID. Les résultats finaux, le nombre de IDs contenant deux et trois répétitions, sont ensuite multipliés pour obtenir le checksum.

## Partie 2 : Gérer les répétitions complexes

La seconde partie du défi demande de trouver deux IDs qui diffèrent par un seul caractère. Pour chaque couple d’IDs, il faut comparer les caractères à des positions correspondantes et identifier les paires qui ont exactement une différence ; c’est alors que la partie commune des deux IDs peut être extraite.

### Approche courante

Une méthode simple mais efficace consiste à utiliser deux boucles imbriquées pour comparer chaque ID avec tous les autres :

1. Parcourir chaque ID et comparer les caractères avec ceux des autres.
2. Déterminer le nombre de différences. Si celui-ci est exactement égal à un, extraire les caractères communs.
3. Arrêter la recherche dès qu’une correspondance valide est trouvée.

Rust, grâce à ses outils de manipulation de chaînes (`String`, `Vec`, etc.), permet de mettre en œuvre cette logique de manière robuste et sans fuite de mémoire.

### Exemple de code possible

```rust
fn find_similar_ids(ids: Vec<&str>) -> Option<String> {
    for (i, id1) in ids.iter().enumerate() {
        for id2 in ids.iter().skip(i + 1) {
            let mut differences = 0;
            let mut common_chars = String::new();

            for (c1, c2) in id1.chars().zip(id2.chars()) {
                if c1 != c2 {
                    differences += 1;
                } else {
                    common_chars.push(c1);
                }

                if differences > 1 {
                    break;
                }
            }

            if differences == 1 {
                return Some(common_chars);
            }
        }
    }

    None
}
```

Cet algorithme priorise la clarté sur une optimisation excessive et offre une solution simple pour identifier deux IDs similaires.

## Leçons apprises du défi

Ce défi Advent of Code met en avant plusieurs concepts et pratiques utiles aux développeurs :

1. **Traitement efficace des chaînes de caractères** : Les structures comme `HashMap` et les opérations sur `Vec` montrent comment gérer des données complexes.
2. **Optimisation algorithmique** : Bien que la complexité ne soit pas toujours optimale, réfléchir sur des structures permet une exécution raisonnable même pour des données volumineuses.
3. **Rust et sa puissance** : Ce langage se révèle idéal pour le traitement performant, grâce à son contrôle sur la mémoire et ses outils de gestion de données.
4. **Conception centrée sur les tests** : Écrire des tests unitaires pour chaque partie du code est crucial pour valider la logique mise en place.

En participant à des défis comme l’Advent of Code, les ingénieurs peuvent explorer des aspects fondamentaux du développement logiciel tout en se perfectionnant dans des langages comme Rust.

[source](https://dev.to/kryko7/advent-of-code-2025-day-2-gift-shop-1lkn)