---
title: "Créer un affichage de l'heure mondiale avec Rust et egui"
seoTitle: "Créer un affichage de l'heure mondiale avec Rust et egui : Tutoriel complet"
seoDescription: "Apprenez à construire une application de bureau affichant l'heure mondiale dans différentes villes avec Rust et egui. Performance et simplicité garanties."
datePublished: Fri Dec 19 2025 06:06:40 GMT+0000 (Coordinated Universal Time)
cuid: cmjcgv8ud000002ldecnn52tv
slug: creer-un-affichage-de-heure-mondiale-avec-rust-et-egui-tutoriel-complet
canonical: https://dev.to/dev-tngsh/build-a-world-time-display-in-rust-with-egui-complete-tutorial-3bin

---

# Créer un affichage de l'heure mondiale avec Rust et egui

## TL;DR

- Apprenez à développer une application de bureau pour afficher l'heure mondiale dans différentes villes avec Rust et le framework egui.
- Rust garantit des performances élevées et une faible consommation de mémoire par rapport aux solutions comme Electron.
- Le tutoriel inclut la configuration, la construction de l'interface utilisateur, le calcul du temps basé sur un fuseau horaire de référence et des solutions aux problèmes courants.
- Vous avez la possibilité de personnaliser facilement les villes affichées dans l'application.

## Introduction

L'affichage de l'heure mondiale est une fonctionnalité utile pour quiconque travaille avec des collaborateurs ou vit dans plusieurs fuseaux horaires. L'objectif de ce tutoriel est de créer une application de bureau simple et performante utilisant Rust et le framework egui pour gérer l'heure mondiale. Rust s'impose comme un langage rapide et sécurisé, tandis qu'egui est un framework compact performant pour des applications graphiques simples.

Pour une application telle qu'un affichage de l'heure mondiale, Rust offre l'avantage d'une faible utilisation des ressources comparé à JavaScript/Electron, tout en garantissant une exécution rapide. Nous allons voir comment concevoir cette solution étape par étape.

## Configuration requise et installation

### Prérequis

Pour suivre ce tutoriel, vous aurez besoin de :

- **Rust** : Assurez-vous d'avoir Rust installé sur votre système. Utilisez [rustup.rs](https://rustup.rs/) pour simplifier l'installation. La version stable est recommandée.
- **egui** : Incluez le framework `egui` dans votre projet Rust via Cargo.
- **Outils système** : Ce tutoriel est compatible avec Windows, macOS et Linux.

### Étapes d'installation

1. Installez Rust avec rustup : 
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
2. Initialisez un nouveau projet Cargo ainsi : 
   ```bash
   cargo new world_time_display
   cd world_time_display
   ```
3. Ajoutez `eframe`, le module basé sur egui pour les applications de bureau, à votre fichier `Cargo.toml` :
   ```toml
   [dependencies]
   eframe = "0.22"
   ```
4. Mettez à jour les dépendances avec :
   ```bash
   cargo build
   ```

## Architecture : calcul basé sur un point de référence

Pour calculer et afficher heure locale de plusieurs villes à partir de l’heure de référence (heure UTC), nous devrons travailler avec des décalages horaires (en heures) définis en fonction des fuseaux horaires.

### Principe clé

1. Utilisez l’heure UTC comme référence.
2. Appliquez des décalages horaires à chaque ville dans une structure de données pour calculer l’heure locale.

L'approche est simple et repose sur des calculs mathématiques basés sur les décalages horaires standards, tout en tenant compte des transitions dues à l'heure d'été lorsque cela est applicable.

## Structure de données principale

La liste des villes et leurs décalages horaires est une partie centrale de cette application. Une structure de données comme un vecteur peut être utilisée pour stocker ces informations. Voici un exemple :

```rust
struct City {
    name: String,
    utc_offset: i32, // Décalage horaire en heures
}
```

Nous définirons ensuite un vecteur contenant les villes souhaitées et leurs décalages horaires :

```rust
let cities = vec![
    City { name: "Paris".to_string(), utc_offset: 1 },
    City { name: "New York".to_string(), utc_offset: -5 },
    City { name: "Tokyo".to_string(), utc_offset: 9 },
];
```

En fonction de l’heure UTC actuelle, nous adapterons l’affichage avec ces informations.

## Construction de l'application GUI

### Mise en place de l'interface

Avec egui, la création d'interfaces graphiques est simplifiée grâce à son API intuitive. Voici comment afficher les données de nos villes :

```rust
fn create_gui(cities: Vec<City>, ui: &mut egui::Ui) {
    for city in cities.iter() {
        let local_time = chrono::Utc::now() + chrono::Duration::hours(city.utc_offset);
        ui.label(format!("{}: {}", city.name, local_time.format("%H:%M:%S")));
    }
}
```

- La fonction `create_gui` prend en entrée une liste de villes et l’objet d’interface utilisateur.
- Les heures locales sont calculées à partir de l’heure UTC avec le décalage de chaque ville.
- Les données sont affichées sous forme de labels dans l’interface.

## Fonction principale complète

### Implémentation

Voici le code de la fonction principale contenant les éléments essentiels :

```rust
use eframe::{egui, epi};

fn main() {
    let app = MyApp::default();
    let native_options = eframe::NativeOptions::default();
    eframe::run_native("Affichage de l'heure mondiale", native_options, Box::new(|_| Box::new(app)));
}

struct MyApp {
    cities: Vec<City>,
}

impl Default for MyApp {
    fn default() -> Self {
        Self {
            cities: vec![
                City { name: "Paris".to_string(), utc_offset: 1 },
                City { name: "New York".to_string(), utc_offset: -5 },
                City { name: "Tokyo".to_string(), utc_offset: 9 },
            ],
        }
    }
}

impl epi::App for MyApp {
    fn update(&mut self, ctx: &egui::Context, _frame: &mut epi::Frame) {
        egui::CentralPanel::default().show(ctx, |ui| {
            create_gui(self.cities.clone(), ui);
        });
    }
}
```

Ce bloc met en place l'application complète, en combinant l'affichage des données et les configurations d'interface.

## Déploiement et personnalisation

Une fois l'application construite, vous pouvez l’exécuter avec :

```bash
cargo run
```

Pour personnaliser les villes affichées, modifiez simplement le vecteur `cities` dans la définition de l’application.

## Problèmes courants et solutions

### Erreurs liées au fuseau horaire

Assurez-vous que les décalages horaires en heures (+/-) suivent les normes UTC. Les changements comme l’heure d’été doivent être pris en compte si nécessaire.

### Problèmes de compatibilité

Si certains composants ne fonctionnent pas correctement sur un système d’exploitation spécifique, vérifiez les versions de Rust et des bibliothèques tierces.

## FAQ sur l'affichage de l'heure mondiale

**Comment configurer les prérequis pour commencer avec ce projet Rust et egui ?**  
Assurez-vous que Rust est installé à l'aide de rustup.rs. Ce projet est compatible avec Windows, macOS et Linux.

**Puis-je personnaliser les villes affichées ?**  
Oui, ajoutez ou modifiez les villes en modifiant le vecteur `cities` dans la fonction principale.

**Pourquoi ne pas utiliser JavaScript/Electron pour cet affichage ?**  
Avec Rust, l'application consomme environ 20 % de la mémoire d'une application Electron et démarre jusqu'à 4 fois plus rapidement, offrant ainsi une meilleure efficacité pour une utilisation intensive.

## Étapes suivantes

Une fois votre affichage fonctionnel, vous pouvez explorer les extensions suivantes :

- Ajouter des options de configuration depuis l'interface, comme le choix des fuseaux horaires.
- Intégrer un mécanisme de rafraîchissement automatique de l’heure locale.
- Ajouter des fonctionnalités supplémentaires comme des prédictions météorologiques par ville ou des alarmes programmées. 

Rust et egui offrent une base solide pour construire des interfaces rapides et légères, parfaites pour des outils utilitaires comme celui-ci. Profitez de ce projet pour approfondir votre compréhension et créer des solutions performantes adaptées à vos besoins.

[source](https://dev.to/dev-tngsh/build-a-world-time-display-in-rust-with-egui-complete-tutorial-3bin)