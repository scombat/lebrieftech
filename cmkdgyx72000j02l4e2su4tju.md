---
title: "Rust et RSI : Comment vous soulevez 500kg/jour avec vos doigts"
seoTitle: "Rust et RSI : Comment vous soulevez 500kg/jour avec vos doigts"
seoDescription: "Découvrez comment Rust et Tauri v2 permettent de mesurer l'impact physique des frappes clavier, équivalant à soulever 500kg par jour. Une solution innovante contre le RSI."
datePublished: Wed Jan 14 2026 03:37:00 GMT+0000 (Coordinated Universal Time)
cuid: cmkdgyx72000j02l4e2su4tju
slug: rust-et-rsi-comment-vous-soulevez-500kg-jour-avec-vos-doigts
canonical: https://dev.to/matsuzaki_yosuke_3f74f648/rust-vs-rsi-how-i-calculated-that-i-lift-500kgday-with-my-fingers-3ana

---

# Rust et RSI : Comment vous soulevez 500kg/jour avec vos doigts

## TL;DR

- Les frappes au clavier, bien que peu visibles, représentent une charge physique équivalente à 500kg par jour selon un ingénieur souffrant de RSI.
- Ce dernier a développé un outil basé sur **Rust** et **Tauri v2** pour mesurer cet impact au quotidien.
- L'approche technique repose sur le **polling** pour garantir stabilité et confidentialité, plutôt que des hooks.
- L'outil inclut une "Health Bar" permettant de visualiser la fatigue liée aux frappes.
- Une solution pour sensibiliser à la santé au travail et adopter de meilleures pratiques.

## Les frappes au clavier : une charge invisible

Dans le métier d'ingénieur ou de développeur, on oublie souvent que nos doigts sont soumis à une pression mécanique intense au quotidien. Chaque frappe de clavier exerce une force moyenne d'environ **80g**. Si l'on cumule ces milliers de frappes sur une journée standard, cela représente **environ 500kg de charge cumulée**. Pour mettre les chiffres en perspective, c'est l'équivalent de soulever deux pianos à queue en un jour ou une voiture chaque semaine uniquement avec les doigts.

Le RSI, pour *Repetitive Strain Injury*, est une blessure commune touchant de nombreux professionnels de l'informatique. Par son invisibilité, cette surcharge peut engendrer douleurs articulaires chroniques et autres impacts sur la santé. Ce constat a motivé un ingénieur à prendre les devants en utilisant ses compétences techniques pour quantifier cette charge invisible.

## Pourquoi choisir Rust et Tauri pour ce projet ?

### Rust : fiabilité et performance

Rust est un langage réputé pour sa gestion de la mémoire sécurisée et ses performances élevées. Ces atouts en font un choix idéal pour concevoir des outils ergonomiques, où la réactivité et la robustesse sont essentielles.

### Polling vs Hooks : une approche réfléchie

La majorité des key-loggers s'appuient sur des "hooks système", qui interceptent directement les événements clavier. Cependant, ce projet a fait le choix du **polling**, une méthode qui interroge régulièrement l'état du clavier sans s'immiscer dans la chaîne d'entrée.

#### Les avantages du polling :
1. **Stabilité accrue** : Contrairement aux hooks, le polling limite les risques de bug et de perturbation des entrées clavier.
2. **Respect des permissions** : macOS impose des autorisations complexes pour les hooks. Avec le polling, ces obstacles sont contournés.
3. **Confidentialité renforcée** : Cette méthode ne cherche pas à savoir quelles touches sont pressées, mais simplement à quantifier les frappes totales. Un compromis idéal entre fonctionnalité et respect de la vie privée.

### Tauri : une interface locale et légère

Tauri v2, utilisé pour construire l'interface de l'outil, propose une solution alliant légèreté et confidentialité. Contrairement à des technologies plus lourdes comme Electron, Tauri permet de minimiser la consommation de ressources tout en garantissant une intégration fluide avec Rust.

## Comment fonctionne cet outil innovant ?

L'ingénieur a conçu un processus simple mais efficace pour mesurer la pression exercée au quotidien. Son outil repose sur le calcul suivant :

1 frappe de clavier = **80g de force.**  
Multiplié par des milliers de frappes sur une journée complète, on atteint aisément les **500kg de force cumulée.**

L'application inclut une "Health Bar" qui se vide au fur et à mesure de vos frappes. À l'image d'un système de jeu vidéo, cet indicateur visuel signale votre état physique lié à la frappe. L'objectif est éducatif : sensibiliser les utilisateurs à l'impact physique de leur travail et les encourager à prendre des pauses.

![Illustration de la barre de santé](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Ftez1mh78c7fxbeikell6.gif)

## Les résultats impressionnants du calcul

Ce projet met en lumière une réalité souvent méconnue : nos frappes clavier ne sont pas insignifiantes. En cumulant une journée de codage classique, voici les chiffres :

- **Force par frappe** : 80g.
- **Pression totale journalière** : ~500kg.
- **Impact sur la santé** : Tensions musculaires et articulaires avec des risques élevés de RSI en cas de surcharge chronique.

Au-delà des données brutes, ces métriques permettent une prise de conscience quant à l'importance d'une ergonomie adaptée et d'une gestion proactive des pauses.

## Testez l'outil et préservez votre santé

Le développement de cet outil s'est concentré sur la simplicité et la confidentialité. L'application, nommée **Burnout Meter**, ne nécessite aucune sauvegarde ou connexion au cloud. Tout fonctionne localement, offrant une utilisation sécurisée et respectueuse de votre vie privée.

### Essayez-le :
👉 [Burnout Meter](https://booby.dev)

Cet outil est une invitation à surveiller l'état de vos doigts et à adapter votre rythme de travail pour éviter les blessures liées au RSI.

## À retenir

Avec une approche basée sur **Rust** et **Tauri**, cet ingénieur a transformé une problématique physique en projet éducatif et innovant. Les frappes clavier accumulent une charge importante, souvent ignorée mais avec des impacts réels sur la santé. Grâce à une méthode technique bien pensée, ce projet interpelle et propose des solutions concrètes pour surveiller l'état physique des développeurs.

Prenons soin de nos doigts : ils sont nos outils les plus précieux dans nos activités numériques.

[source](https://dev.to/matsuzaki_yosuke_3f74f648/rust-vs-rsi-how-i-calculated-that-i-lift-500kgday-with-my-fingers-3ana)