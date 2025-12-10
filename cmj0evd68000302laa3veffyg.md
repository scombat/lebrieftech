---
title: "Construire un visualiseur rapide de 10 Go pour VS Code grâce à Rust"
seoTitle: "Créer un visualiseur de logs de 10 Go pour VS Code avec Rust et mémoire partagée"
seoDescription: "Apprenez à concevoir un visualiseur de logs performant dans VS Code grâce à Rust et la mémoire partagée. Navigation rapide et utilisation optimale de la RAM."
datePublished: Wed Dec 10 2025 19:37:32 GMT+0000 (Coordinated Universal Time)
cuid: cmj0evd68000302laa3veffyg
slug: visualiseur-logs-vscode-rust-memoire-partagee
canonical: https://dev.to/__1bea7786c7/how-i-built-a-lag-free-10gb-log-viewer-for-vs-code-using-rust-memory-mapping-ih4

---

# Construire un visualiseur rapide de 10 Go pour VS Code grâce à Rust

## TL;DR

- Les gros fichiers de logs (plusieurs Go) ralentissent fortement VS Code en surchargeant la RAM.
- Une solution efficace combine Rust et mémoire partagée pour minimiser les ressources utilisées.
- L’architecture repose sur un modèle Sidecar avec un frontend TypeScript et un backend en Rust.
- Cette approche garantit des performances accrues, une navigation fluide et des fonctionnalités comme le filtrage dynamique.
- Parfait pour analyser les logs, CSVs massifs ou tout fichier volumineux.

## Problème : les gros fichiers de logs dans VS Code

VS Code est un outil puissant, mais l’ouverture de fichiers volumineux, comme des logs (`server.log`) de plusieurs gigaoctets, peut devenir un véritable casse-tête. Cette problématique provient essentiellement des limites d’Electron, le framework sur lequel VS Code est construit. Electron charge tout le contenu d’un fichier dans le DOM, ce qui entraîne :

- Une consommation excessive de RAM.
- Une navigation ralentie dans le fichier, surtout pour des actions courantes comme la recherche ou le copier-coller.
- Des limitations au niveau du défilement fluide.

Cette contrainte peut rendre difficile le travail sur de grands fichiers, souvent essentiels dans des scénarios de surveillance système, de debugging ou de gestion de données massives.

## Solution avec Rust et mémoire partagée

Pour contrer ces limites, l’approche proposée repose sur deux piliers technologiques principaux :

1. **Rust**, qui offre des performances exceptionnelles pour gérer les entrées et sorties à partir de fichiers.
2. **La mémoire mappée**, qui permet une utilisation extrêmement efficace de la RAM.

Avec ce duo, il est possible de lire des fichiers massifs sans bloquer votre environnement de développement, même avec des logs ou CSV de plusieurs gigaoctets.

## Architecture : le modèle Sidecar

Cette extension suit une architecture modulaire, appelée **modèle Sidecar**, qui se compose de deux parties principales :

### Frontend : interface utilisateur avec TypeScript  
Le frontend, développé en TypeScript, repose sur le Webview de VS Code. Il gère :

- L’affichage des données via des mécanismes de défilement virtuel.
- Les interactions utilisateur, comme la navigation ou les recherches dans le fichier.
- L’intégration visuelle fluide au sein de VS Code.

### Backend : traitement des fichiers avec Rust  
Le backend, développé en Rust, prend en charge les aspects techniques, notamment :

- Le chargement rapide des fichiers grâce à la mémoire mappée.
- L’indexation avancée pour un accès direct à n’importe quelle ligne du fichier.
- Les recherches ultra-rapides grâce à des bibliothèques performantes comme `regex`.

Le protocole de communication entre ces deux parties repose sur des messages JSON échangés en temps réel.

## Optimisation Backend avec Rust

### Entrées/Sorties avec mémoire mappée
Au lieu de charger l’ensemble du fichier en mémoire, Rust utilise la bibliothèque `memmap2` pour mapper le fichier dans l’espace d’adresses virtuelles du processus. Cela offre plusieurs avantages :

- **Réduction de l’utilisation de la RAM** : Seules les parties du fichier nécessaires sont consultées, grâce à la gestion par pagination effectuée directement par l’OS.
- **Accès rapide** : L’accès à n’importe quelle portion de texte se fait instantanément.

### Indexation des lignes
Le backend effectue un scan initial pour indexer les positions de chaque ligne dans le fichier. Ces positions sont stockées dans un vecteur, ce qui permet de récupérer rapidement n’importe quelle ligne sans avoir à rescanner tout le contenu.

### Recherche rapide
Les recherches textuelles et les requêtes d’expression régulière sont exécutées directement en Rust, une solution bien plus performante que les alternatives basées sur JavaScript. Pour éviter les surcharges, un plafond de résultats (par exemple, 10 000 correspondances) est défini.

## Défilement virtuel dans le frontend TypeScript

### Gestion des limites des navigateurs
Les navigateurs ont une contrainte : ils ne peuvent afficher que des éléments DOM avec une hauteur allant jusqu’à 30 millions de pixels. Cela peut poser problème face à de très gros fichiers, mais un système de **défilement virtuel** permet de contourner cette limitation.

Avec le défilement virtuel, seules les lignes visibles par l’utilisateur sont chargées dans le DOM. Les données hors du champ visible sont mises en cache ou récupérées à la demande depuis le backend Rust.

### Mise en cache dynamique
Pour éviter la surcharge du DOM, le frontend maintient uniquement un buffer mémoire contenant les lignes visibles et proches du viewport utilisateur. Les lignes inutiles sont désallocées du cache, permettant une gestion optimale des ressources.

### Filtrage des contenus
Lorsqu’il est nécessaire de filtrer les données (par exemple pour afficher exclusivement les lignes contenant “ERREUR”), le système conserve une numérotation des lignes originales pour naviguer facilement entre les correspondances.

## Mode suivi pour logs dynamiques

En situation de monitoring de logs, il est fréquent de consulter des fichiers en constante évolution, par exemple un fichier où de nouvelles lignes sont ajoutées régulièrement. L’extension propose un **mode suivi**, similaire à la commande classique `tail -f` :

- Le frontend vérifie toutes les 500 millisecondes les ajouts dans le fichier.
- Le backend remappe le fichier si sa taille a augmenté, mettant à jour les index des nouvelles lignes.
- Si l’utilisateur est positionné à la fin du fichier, le défilement automatique active le suivi. Dans le cas contraire, le mode suivi reste en pause pour ne pas perturber la lecture.

## Méthode de compilation multiplateforme

L’extension dépend d’un **binaire natif**, nécessitant une compatibilité avec plusieurs systèmes d’exploitation. Grâce à GitHub Actions, les versions suivantes du binaire sont générées automatiquement :

- macOS : `darwin-x64` et `darwin-arm64`.
- Linux : `linux-x64`.
- Windows : `win32-x64`.

Avec une taille finale de seulement 0,8 Mo, le package reste léger et facilement distribuable via le Marketplace de VS Code.

## Conclusion : performance maximisée avec Rust

Ce projet illustre la puissance de Rust, notamment pour ses capacités à gérer des fichiers massifs de manière efficace. En s’appuyant sur un backend performant et un frontend bien conçu, cette extension permet de surmonter les limites inhérentes à VS Code pour des travaux exigeants, comme l’analyse de logs ou l’exploration de grands fichiers CSV.

Si vous travaillez régulièrement avec des volumes conséquents de données, cette extension pourrait devenir un outil indispensable, favorisant un développement fluide et une navigation rapide dans vos fichiers.

**Liens utiles**  
- [VS Code Marketplace : Log Analyzer Pro](https://marketplace.visualstudio.com/items?itemName=molchanovartem1994.log-analyzer-pro)  
- [GitHub : log-analyzer-pro repo](https://gitlab.com/molchanov.artem.1994/log-analyzer-pro)  

[source](https://dev.to/__1bea7786c7/how-i-built-a-lag-free-10gb-log-viewer-for-vs-code-using-rust-memory-mapping-ih4)