---
title: "Tor est désormais réécrit en Rust : ce qu'il faut retenir"
seoTitle: "Tor passe de C à Rust pour un meilleur futur"
seoDescription: "Découvrez comment le projet Tor, désormais réécrit en Rust, améliore ses performances avec Arti version 1.8.0."
datePublished: Thu Dec 11 2025 12:54:16 GMT+0000 (Coordinated Universal Time)
cuid: cmj1fwmbo000502jjhju93hnj
slug: tor-rewrite-rust-avant-c
canonical: https://itsfoss.com/news/tor-rust-rewrite-progress/

---

# Tor est désormais réécrit en Rust : ce qu'il faut retenir

## TL;DR

- Le projet Tor abandonne le langage C pour adopter Rust, un langage à la fois plus sécurisé et moderne.
- Rust facilite la gestion des ressources, réduisant les risques liés aux bugs mémoire et aux failles de sécurité.
- La version Arti 1.8.0, une réécriture en Rust, introduit des améliorations notables, notamment une meilleure isolation de circuit et des performances accrues.
- Cette refonte marque un tournant dans l'évolution du projet Tor et ses services onion.

## Qu'est-ce que le projet Tor ?

Le projet Tor (The Onion Router) est un réseau décentralisé conçu pour garantir l'anonymat et la confidentialité en ligne. Il permet aux utilisateurs de naviguer sur Internet sans révéler leur adresse IP et de protéger leurs communications en les acheminant via une série de relais cryptés. Son infrastructure repose sur un protocole robuste qui utilise une architecture en couches – d'où le nom "Onion Router".

Tor est largement utilisé par ceux qui souhaitent préserver leur vie privée, que ce soit des journalistes, des défenseurs des droits humains, ou des individus vivant dans des environnements restrictifs. Le projet offre également des services onion, qui permettent de créer des sites accessibles uniquement via le réseau Tor, renforçant ainsi l'anonymat tant pour l'hébergeur que pour les utilisateurs.

## Pourquoi passer de C à Rust ?

Le cœur de l'infrastructure Tor, historiquement écrit en C, présente certains défis inhérents au langage. C est connu pour sa puissance en matière de bas niveau, mais il est aussi souvent associé à des vulnérabilités telles que les débordements de mémoire, les usages incorrects de pointeurs, ou encore les fuites de mémoire. Dans un projet centré sur la sécurité comme Tor, ces risques sont particulièrement problématiques.

Rust, en revanche, est conçu pour éviter de tels problèmes grâce à un système de gestion de mémoire strict, un typage plus robuste, et des concepts tels que le "ownership" (propriété des données). Ce choix améliore la stabilité et la sécurité globale du code. En outre, Rust est réputé pour sa performance, ce qui est essentiel pour un réseau de la taille de Tor, qui traite des millions de connexions simultanées.

En choisissant Rust, le projet fait un pas vers une approche plus moderne et maintenable. Cela permet de réduire les risques de bugs critiques tout en facilitant l'évolution de la base de code pour répondre aux besoins futurs.

## Améliorations dans la version 1.8.0

Avec la version Arti 1.8.0, Tor introduit des avancées concrètes qui capitalisent sur les atouts de Rust. Parmi les points forts de cette version, on peut noter :

### Meilleure isolation des circuits

La nouvelle version offre une meilleure gestion des circuits, qui sont les chemins utilisés pour acheminer les données sur le réseau. Cette amélioration réduit les risques de corrélation entre les données envoyées, renforçant ainsi l'anonymat des utilisateurs.

### Optimisation des services onion

Les services onion, qui permettent de créer des connexions totalement anonymes, bénéficient également d'une mise à niveau. Avec Arti 1.8.0, ces services sont plus fiables, notamment en matière de gestion de charge et de résilience face aux interruptions.

### Performances accrues

Grâce à Rust, le projet a pu améliorer la vitesse de certains processus internes, tout en réduisant la consommation de ressources. Cela se traduit par une expérience utilisateur plus fluide et une meilleure réactivité lors de l'accès aux services Tor.

## Comment Arti contribue au projet Tor

Arti est une réécriture en Rust de l'implémentation traditionnelle du client Tor. Contrairement à son prédécesseur en C, Arti exploite pleinement les avantages offerts par Rust. Cela comprend une architecture de code simplifiée, une gestion des erreurs améliorée, et une réduction significative des vulnérabilités courantes.

### Code maintenable et modulaire

Rust facilite la création de modules séparés et bien définis, ce qui rend le code base d'Arti plus facile à maintenir et à étendre. Cela permet aux développeurs du projet Tor de concentrer leurs efforts sur les futures fonctionnalités sans compromettre les bases existantes.

### Une fondation pour l'avenir

Arti est conçu pour être flexible et évoluer avec les besoins croissants du réseau Tor. L'idée derrière cette refonte est de construire un projet capable de s'adapter aux nouveaux défis, comme l'augmentation continue du trafic, les attaques plus sophistiquées, ou encore l'intégration avec d'autres technologies liées à la confidentialité.

Avec cette transition vers Rust et les avancées d'Arti, le projet Tor montre qu'il est déterminé à rester à la pointe de la technologie tout en répondant aux attentes des utilisateurs en matière de sécurité et de performance.

[source](https://itsfoss.com/news/tor-rust-rewrite-progress/)