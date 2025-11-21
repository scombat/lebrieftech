---
title: "Logging structuré avec tracing en Rust"
seoTitle: "Introduction au logging structuré avec tracing en Rust"
seoDescription: "Apprenez à utiliser tracing pour le logging structuré en Rust. Optimisez la configuration des logs et améliorez le débogage dans vos projets async."
datePublished: Fri Nov 21 2025 11:37:24 GMT+0000 (Coordinated Universal Time)
cuid: cmi8scq0s000f02k02z6k4kk1
slug: logging-structure-tracing-rust
canonical: https://dev.to/vinecksie_rust/rust-weekly-log-structured-logging-with-tracing-j7c

---

# Logging structuré avec tracing en Rust

## TL;DR

- **Tracing** est une bibliothèque Rust pour implémenter un logging structuré, permettant un débogage plus efficace.
- Il permet de configurer des formats de logs personnalisés, tels que du texte simple ou des objets JSON.
- Grâce à des extensions comme `#[instrument]` et `TraceLayer`, vous pouvez enrichir vos logs avec des métadonnées utiles pour l'observabilité et le suivi des opérations.
- C'est particulièrement adapté aux projets utilisant **Rust async** et des frameworks comme **Axum**.

## Un aperçu du logging structuré

Dans les applications modernes, le simple fait d'avoir des traces textuelles dans les logs ne suffit plus. Le logging structuré propose une alternative qui consiste à organiser les informations dans un format lisible, interprétable et exploitable par des outils d'analyse et monitoring. En Rust, la bibliothèque **tracing** offre une solution puissante pour produire des informations riches en contexte et adaptées aux besoins spécifiques des développeurs.

Contrairement au traditionnel **println!()**, tracing capture des données plus sophistiquées, comme les métadonnées d'exécution. Cette librairie est conçue pour les applications Rust, notamment celles qui reposent sur la programmation asynchrone.

## Configurer des logs flexibles et clairs

La configuration des logs dans **tracing** débute par la création d'un subscriber. Un subscriber dans tracing est responsable de collecter, formater et transmettre les événements générés par votre application. Voici un exemple minimal de configuration :

```rust
use tracing_subscriber::{FmtSubscriber, EnvFilter};

fn main() {
    let subscriber = FmtSubscriber::builder()
        .with_env_filter(EnvFilter::new("info"))
        .finish();

    tracing::subscriber::set_global_default(subscriber).expect("Erreur lors de la configuration du subscriber");

    tracing::info!("Application démarrée");
}
```

Dans cet exemple :

- `EnvFilter::new("info")` définit le niveau de verbose—seuls les événements avec un niveau `info` ou supérieur seront affichés.
- `FmtSubscriber` spécifie le format des logs : ici, un affichage structuré lisible dans la console.

En ajustant ces paramètres, vous pouvez facilement personnaliser les niveaux de journalisation selon vos besoins, par exemple pour mettre en évidence uniquement les traces critiques ou déboguer plus en profondeur.

## Passer du format compact au format JSON

Pour les projets reposant sur des systèmes complexes d'analyse de logs, comme **Elastic Stack** ou **Prometheus**, il peut être avantageux de configurer une sortie au format **JSON**. Tracing facilite cette transition comme suit :

```rust
use tracing_subscriber::fmt::format::Json;
use tracing_subscriber::fmt::{self, Writer};
use tracing_subscriber::{fmt::SubscriberBuilder, EnvFilter};

fn main() {
    let subscriber = SubscriberBuilder::default()
        .with_env_filter(EnvFilter::new("info"))
        .json() // Sortie JSON
        .finish();

    tracing::subscriber::set_global_default(subscriber).expect("Erreur configuration");

    tracing::info!(message = "L'application a démarré", app_state = "initialisation");
}
```

Dans le code ci-dessus, l'emploi de `fmt::format::Json` transforme la sortie textuelle classique en un format JSON structuré. Cela permet aux outils de traitement des logs de facilement indexer et analyser les événements, souvent essentiel dans des systèmes distribués.

## Ajouter des métadonnées contextuelles

Le principal avantage du logging structuré est la possibilité d'ajouter des métadonnées. Cela fournit un contexte crucial pour comprendre l'état d'une application au moment où un événement est généré. Avec **tracing**, vous pouvez inclure ces métadonnées directement dans vos événements :

```rust
use tracing::info;

fn process_data(data: &str) {
    info!(
        task_name = "process_data",
        data_length = data.len(),
        "Traitement en cours du fichier"
    );
}
```

Les métadonnées comme `task_name` et `data_length` permettent d'apporter des détails supplémentaires dans vos logs. Ces informations deviennent particulièrement utiles lorsque vous analysez les performances ou déboguez une panne dans un système asynchrone.

## Intégrer TraceLayer pour des logs automatiques

Les frameworks comme **Axum**, utilisés dans des projets web en Rust, se marient bien avec la couche `TraceLayer` de tracing. Elle permet d'ajouter automatiquement des informations de routage, les requêtes HTTP et les réponses dans les logs.

Exemple d'intégration avec Axum :

```rust
use axum::{Router, routing::get};
use tower::ServiceBuilder;
use tower_http::trace::TraceLayer;
use tracing::info;

#[tokio::main]
async fn main() {
    let app = Router::new()
        .route("/", get(|| async {
            info!("Endpoint racine visité");
            "Bienvenue sur mon API!"
        }))
        .layer(ServiceBuilder::new().layer(TraceLayer::new_for_http())); // TraceLayer activé

    println!("Démarrage du serveur sur http://localhost:3000");
    axum::Server::bind(&"0.0.0.0:3000".parse().unwrap())
        .serve(app.into_make_service())
        .await
        .unwrap();
}
```

Ici, TraceLayer capture automatiquement les informations pertinentes telles que l'URI de requête, les latences et les codes de réponse HTTP. Cela devient particulièrement puissant pour surveiller les performances API ou diagnostiquer des comportements inattendus.

## Utilisation pratique de #[instrument]

L'attribut `#[instrument]` dans tracing est une manière simple et élégante d'ajouter des métadonnées automatiquement aux fonctions. Il suit automatiquement les arguments et peut enregistrer l'entrée et la sortie des fonctions :

```rust
use tracing::instrument;

#[instrument]
fn calculer_somme(a: i32, b: i32) -> i32 {
    a + b
}
```

Avec `#[instrument]` au-dessus de la fonction, des informations comme les paramètres passés et la sortie peuvent être intégrées dans les logs. Cela réduit l'effort manuel de création de traces détaillées et assure une cohérence.

L'utilisation de cet attribut est particulièrement utile pour les fonctions critiques, notamment pour le débogage dans des systèmes asynchrones qui nécessitent un suivi précis des tâches.

---

Avec **tracing**, Rust fournit une solution puissante et flexible pour le logging structuré, idéale pour l'observabilité et la gestion efficace des systèmes asynchrones. Que ce soit pour des applications simples ou des architectures complexes, cette bibliothèque offre de nombreux outils pour adapter les logs à vos besoins, enrichir votre compréhension des systèmes et améliorer vos capacités de débogage.

[source](https://dev.to/vinecksie_rust/rust-weekly-log-structured-logging-with-tracing-j7c)