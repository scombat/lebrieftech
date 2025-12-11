---
title: "Tutoriel sur l'ownership en Rust"
seoTitle: "Comprendre le concept d'ownership en Rust : guide et tutoriel"
seoDescription: "Apprenez les bases du concept d'ownership et de borrowing dans Rust à travers des exemples simples et détaillés. Optimisez vos compétences en mémoire et compilation."
datePublished: Thu Dec 11 2025 09:22:04 GMT+0000 (Coordinated Universal Time)
cuid: cmj18bpy8000602jrha0ken3j
slug: ownership-en-rust-guide
canonical: https://dev.to/nfrankel/yet-another-rust-ownership-tutorial-4de1

---

# Tutoriel sur l'ownership en Rust

## TL;DR

- L'ownership est un concept fondamental en Rust, garantissant une gestion sécurisée et efficace de la mémoire.
- Chaque valeur possède un propriétaire unique, et sa mémoire est libérée automatiquement lorsqu'elle quitte son scope.
- Le borrowing permet d'accéder à des variables sans transférer leur propriété, et la mutabilité contrôle si des données peuvent être modifiées.
- Ces mécanismes minimisent les erreurs liées à la gestion manuelle de la mémoire et sont incontournables pour maîtriser Rust.

## Pourquoi l'ownership est essentiel en Rust

Rust se distingue par sa philosophie tournée vers la sécurité et la gestion de la mémoire. Contrairement à d'autres langages où les développeurs sont responsables du suivi et de la libération de la mémoire (comme en C++), Rust introduit une approche entièrement automatisée grâce à l'ownership.

### Définition de l'ownership

Le principe d'ownership repose sur quelques règles simples :
- **Chaque valeur en mémoire a un propriétaire unique**. Cette variable propriétaire est responsable de la gestion de la ressource.
- **La mémoire est automatiquement libérée** lorsque la variable quitte son scope. Cela évite les problèmes de fuites de mémoire.
- **Transférer l'ownership** signifie que le propriétaire change : une variable peut perdre son ownership au profit d'une autre.

Ces règles permettent à Rust de garantir une gestion efficace de la mémoire tout en évitant les erreurs courantes, comme l'utilisation de données après leur libération ou la duplication non contrôlée d'objets.

### Contrôle des accès concurrents

L'ownership joue également un rôle clé dans le modèle de sécurité de Rust. Il bloque les accès simultanés mutables aux données, contribuant ainsi à prévenir les conditions de concurrence, un problème courant dans les programmes multiprocéduraux.

## Différencier ownership, borrowing et mutabilité

Pour comprendre pleinement l'ownership, il est crucial de maîtriser deux concepts complémentaires : le borrowing et la mutabilité.

### Borrowing : utiliser sans posséder

Le borrowing (prêt) permet à une fonction ou une partie du programme d'accéder à une variable sans en prendre la propriété. On peut emprunter de deux façons :
- En mode **imutable** : la donnée est lue mais ne peut pas être modifiée.
- En mode **mutable** : la donnée est modifiée, mais cela impose que seule une référence mutable soit active à un instant donné.

#### Exemple de référence immuable
```rust
fn main() {
    let s = String::from("Bonjour");
    let len = calculate_length(&s); // Passe une référence
    println!("La longueur de '{}' est {}.", s, len); // Utilisation de la variable après emprunt
}

fn calculate_length(s: &String) -> usize {
    s.len() // Lecture sans modifier la valeur
}
```

Dans cet exemple, la variable `s` est empruntée par la fonction `calculate_length` sans perdre son ownership. Cela garantit qu'elle reste utilisable par la suite.

#### Exemple de référence mutable
```rust
fn main() {
    let mut s = String::from("Bonjour");
    change(&mut s); // Passe une référence mutable
    println!("String modifiée : {}", s); // Utilisation de la variable modifiée
}

fn change(s: &mut String) {
    s.push_str(", monde !");
}
```

Ici, une référence mutable permet de modifier la valeur de la variable `s`, mais Rust assure qu'il n'y aura pas d'autre emprunt en même temps.

### Mutabilité des variables

Rust impose une mutabilité explicite : par défaut, toutes les variables sont immuables. Pour modifier une variable, il faut la déclarer avec le mot-clé `mut`. Ce choix de design garantit une meilleure compréhension des points du programme où des modifications peuvent survenir.

## Exemples pratiques en Rust sur l'ownership

### Transfert d'ownership

Lorsqu'une variable est assignée à une autre, son ownership est transféré. Cela signifie que la première variable ne peut plus être utilisée.

```rust
fn main() {
    let x = String::from("Hello"); // x possède l'ownership
    let y = x; // Transfert de l'ownership de x à y
    println!("{}", x); // Erreur : x n’est plus valide
}
```

Ici, l'ownership de `x` est transféré à `y`. Toute tentative d'utiliser `x` après cette opération entraîne une erreur de compilation.

### Clonage des données

Si vous souhaitez que plusieurs variables utilisent la même valeur, il est nécessaire de cloner les données au lieu de transférer l'ownership.

```rust
fn main() {
    let x = String::from("Bonjour");
    let y = x.clone(); // Copie explicite des données
    println!("x: {}, y: {}", x, y); // Les deux sont valables
}
```

Le clonage crée une nouvelle instance de la valeur originale, permettant un usage parallèle sans conflit d'ownership.

### Utilisation avancée : ownership dans les collections

Les collections comme `Vec` suivent également les règles de l'ownership. Lorsque vous ajoutez une valeur à un vecteur, le vecteur prend l'ownership de cette valeur.

```rust
fn main() {
    let v = vec![String::from("a"), String::from("b")];
    for s in &v {
        println!("{}", s); // Emprunt immuable pour lire les valeurs
    }
}
```

Dans cet exemple, les références immuables permettent d'itérer sur le vecteur sans déplacer l'ownership des éléments.

## Conclusion

L'ownership, le borrowing et la mutabilité forment les fondations de Rust. En intégrant ces concepts dans vos pratiques, vous pouvez écrire des programmes où la gestion de la mémoire est sûre et performante. Les exemples présentés ici montrent comment Rust encadre ces mécanismes via des règles strictes et claires, vous aidant à éviter des bugs complexes tout en optimisant vos ressources.

[source](https://dev.to/nfrankel/yet-another-rust-ownership-tutorial-4de1)