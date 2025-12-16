---
title: "Créer une API REST CRUD avec Axum, SQLx, Postgres et Docker"
seoTitle: "Créer une API REST CRUD avec Rust, Axum, SQLx, Postgres et Docker"
seoDescription: "Apprenez à développer une API REST CRUD performante en utilisant Axum, SQLx, Rust et Postgres, entièrement conteneurisée avec Docker."
datePublished: Tue Dec 16 2025 14:11:01 GMT+0000 (Coordinated Universal Time)
cuid: cmj8nukt7000102jmexey0e2y
slug: creer-api-rest-crud-axum-sqlx-docker
canonical: https://dev.to/francescoxx/rust-crud-rest-api-using-axum-sqlx-postgres-docker-and-docker-compose-152a

---

# Créer une API REST CRUD avec Axum, SQLx, Postgres et Docker

## TL;DR

- Découvrez comment construire une API REST CRUD en Rust à l’aide des frameworks modernes Axum et SQLx.
- La base de données est gérée par Postgres et conteneurisée avec Docker et Docker Compose.
- L’approche pas à pas inclut l’initialisation du projet, la configuration de Postgres, le développement avec Axum, et la mise en conteneur.
- Vous pourrez tester l’application pour valider son bon fonctionnement avant une éventuelle mise en production.

## Introduction au projet

Rust est un langage de programmation connu pour ses performances et sa sécurité mémoire, mais il excelle également dans le développement d'API Web performantes. Ce projet vous guidera dans la création d'une API REST CRUD (Create, Read, Update, Delete) en utilisant Axum comme framework web, SQLx pour l’interaction avec une base de données, et Docker pour la conteneurisation.

L'objectif est de concevoir une application pratique et facilement déployable tout en tirant parti des avantages du langage Rust et des outils modernes tels que Docker Compose pour orchestrer les différentes parties du projet.

## Étape 1 : Initialisation du projet

### Installer Rust et Cargo

Avant de commencer, assurez-vous que Rust et Cargo sont installés sur votre machine. Vous pouvez les obtenir via la commande suivante :

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Une fois Rust installé, créez un nouveau projet avec Cargo :

```bash
cargo new rust-crud-api
cd rust-crud-api
```

### Ajouter les dépendances

Dans votre fichier `Cargo.toml`, ajoutez les dépendances nécessaires :

```toml
[dependencies]
axum = "0.6"
tokio = { version = "1", features = ["full"] }
sqlx = { version = "0.6", features = ["postgres", "runtime-tokio-native-tls"] }
serde = { version = "1.0", features = ["derive"] }
dotenv = "0.15"
```

Cela inclut Axum pour le framework web, SQLx pour interagir avec la base de données, Tokio pour le runtime asynchrone, et dotenv pour gérer les variables d’environnement.

## Étape 2 : Configuration de la base de données Postgres

### Installer Docker et Docker Compose

Si vous ne l’avez pas encore fait, installez Docker et Docker Compose. Ces outils permettent de conteneuriser la base de données et de simplifier la gestion des configurations.

### Créer un fichier `docker-compose.yml`

Définissez un fichier `docker-compose.yml` pour configurer votre conteneur Postgres :

```yaml
version: "3.8"
services:
  postgres:
    image: postgres:14
    container_name: postgres
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      POSTGRES_DB: rust_api
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data
volumes:
  postgres_data:
```

Exécutez `docker-compose up -d` pour initialiser la base de données.

### Configurer la connexion à Postgres

Ajoutez un fichier `.env` à la racine du projet pour gérer les variables d’environnement :

```
DATABASE_URL=postgres://postgres:password@localhost:5432/rust_api
```

Le fichier `.env` sera utilisé par SQLx et simplifie la configuration des paramètres de connexion.

## Étape 3 : Développement avec Axum et SQLx

### Définir les modèles

Créez un modèle pour représenter une ressource dans votre application (par exemple, un utilisateur). Utilisez les fonctionnalités de *Serde* pour la sérialisation et désérialisation JSON et SQLx pour correspondre au schéma de la base de données :

```rust
use serde::{Deserialize, Serialize};

#[derive(Serialize, Deserialize)]
pub struct User {
    pub id: i32,
    pub name: String,
    pub email: String,
}
```

### Écrire les endpoints Axum

Configurez les routes CRUD avec Axum dans votre fichier `main.rs` :

```rust
use axum::{Router, routing::get};

async fn health_check() -> &'static str {
    "OK"
}

#[tokio::main]
async fn main() {
    let app = Router::new()
        .route("/health_check", get(health_check));

    axum::Server::bind(&"0.0.0.0:3000".parse().unwrap())
        .serve(app.into_make_service())
        .await
        .unwrap();
}
```

Ce code crée une route de santé simple pour tester que le serveur répond correctement.

### Interagir avec la base de données

Ajoutez les fonctions associées à chaque opération CRUD, en préparant des requêtes SQL avec SQLx. Par exemple, pour récupérer tous les utilisateurs :

```rust
use sqlx::PgPool;

pub async fn get_users(pool: PgPool) -> Vec<User> {
    sqlx::query_as!(User, "SELECT id, name, email FROM users")
        .fetch_all(&pool)
        .await
        .unwrap()
}
```

Vous pouvez répéter ce processus pour les opérations CREATE, UPDATE, et DELETE.

## Étape 4 : Conteneurisation avec Docker

### Créer un Dockerfile pour l'application Rust

Ajoutez un fichier `Dockerfile` à la racine du projet pour conteneuriser l’application :

```dockerfile
FROM rust:1.72 as builder
WORKDIR /app
COPY . .
RUN cargo build --release

FROM debian:buster-slim
WORKDIR /app
COPY --from=builder /app/target/release/rust-crud-api .
CMD ["./rust-crud-api"]
```

### Intégrer l’application au `docker-compose.yml`

Ajoutez un service pour l’application dans le fichier Docker Compose :

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      DATABASE_URL: postgres://postgres:password@postgres:5432/rust_api
    depends_on:
      - postgres
```

Lancez l’intégralité des conteneurs avec la commande suivante :

```bash
docker-compose up --build
```

## Étape 5 : Tests et validation de l'application

### Effectuer les tests manuels

Utilisez un outil comme *Postman* ou *curl* pour interagir avec votre API et tester les routes CRUD implémentées. Par exemple, vous pouvez effectuer un test GET :

```bash
curl http://localhost:3000/health_check
```

### Implémenter des tests unitaires

Dans le cadre d’un projet robuste, ajoutez des tests unitaires et d'intégration pour valider que toutes les opérations fonctionnent comme attendu. Un exemple de test peut ressembler à ceci :

```rust
#[tokio::test]
async fn test_health_check() {
    let response = health_check().await;
    assert_eq!(response, "OK");
}
```

Ces tests permettent de garantir la fiabilité et d’éviter les régressions.

### Vérifications supplémentaires

Enfin, surveillez les logs Docker pour vous assurer qu’il n’y a pas d’erreurs pendant l’exécution.

---

Avec ces étapes, vous disposez désormais d’une API REST CRUD fonctionnelle en Rust, prête à être étendue ou mise en production.

[source](https://dev.to/francescoxx/rust-crud-rest-api-using-axum-sqlx-postgres-docker-and-docker-compose-152a)