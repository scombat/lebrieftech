---
title: "Comment collecter les frais et récompenses avec Orca Whirlpools"
seoTitle: "Guide pour collecter frais et récompenses sur Orca Whirlpools"
seoDescription: "Apprenez à collecter les frais et récompenses efficacement sur Orca Whirlpools, l'AMM sur Solana. Suivez les étapes clés pour maximiser vos gains."
datePublished: Thu Nov 27 2025 06:53:35 GMT+0000 (Coordinated Universal Time)
cuid: cmih2uurc000102l7ffop41gb
slug: guide-collecter-frais-recompenses-orca-whirlpools
canonical: https://dev.to/tomtomdu73/collecting-fees-and-rewards-from-orca-whirlpool-positions-5af5

---

# Comment collecter les frais et récompenses avec Orca Whirlpools

## TL;DR

- **Orca Whirlpools** est un AMM de liquidité concentrée sur Solana offrant des frais et récompenses incitatives aux fournisseurs de liquidité.
- Avant de collecter, il est essentiel de **mettre à jour vos frais et récompenses** via la fonction dédiée `update_fees_and_rewards`, garantissant un calcul précis.
- Les frais sont collectés en appelant la fonction `collect_fees`, récupérant vos jetons du pool.
- Les récompenses doivent être collectées pour chaque slot actif via `rewardInfos`.

## Qu'est-ce qu'Orca Whirlpools ?

Orca Whirlpools est un Automated Market Maker (AMM) de liquidité concentrée fonctionnant sur la blockchain Solana. Contrairement aux AMM classiques qui distribuent la liquidité sur l'ensemble de la plage de prix, Whale Whirlpools permet de la concentrer dans une plage restreinte. Ce modèle est conçu pour optimiser l'utilisation du capital et maximiser les gains potentiels pour les fournisseurs de liquidité (LPs).

Les participants au Whirlpools gagnent non seulement une part des frais de transaction générés par les échanges dans ces pools, mais aussi des récompenses incitatives, lesquelles sont financées par des programmes de staking et des incitations spécifiques sur Solana.

## Pourquoi mettre à jour avant de collecter ?

Avant de récupérer vos frais ou vos récompenses, une étape indispensable est nécessaire : vous devez mettre à jour vos données de frais et de récompenses avec la fonction `update_fees_and_rewards`. Cette opération est essentielle pour plusieurs raisons :

1. **Calcul des montants accumulés** : Les frais et les récompenses s'accumulent au fil des transactions et des opérations dans le pool. La mise à jour garantit que les montants calculés incluent tout ce qui a été généré depuis votre dernière opération.
2. **Synchronisation avec la blockchain** : Solana repose sur un modèle rapide et à haute fréquence. Mettre à jour permet de s'assurer que les données affichées sont précises et qu'elles correspondent à l'état actuel du pool.
3. **Prévention des erreurs ou pertes** : Si cette étape est omise, les frais et récompenses non mises à jour pourraient ne pas être correctement crédités, entraînant des pertes potentielles.

En somme, l'appel à `update_fees_and_rewards` agit comme un checkpoint crucial avant tout processus de récupération.

## Comment collecter les frais

Une fois que vos frais et récompenses ont été correctement mis à jour, vous pouvez procéder à leur récupération. Les frais dans Orca Whirlpools sont les jetons générés par les échanges effectués par les utilisateurs dans le pool de liquidité que vous avez fourni. 

L'étape principale pour collecter vos frais consiste à appeler la méthode `collect_fees`. Cette fonction extrait les frais accumulés et les transfère directement dans votre portefeuille, en respectant les parts de liquidité que vous détenez dans le pool.

### Étapes pour collecter les frais :
1. **Appeler `update_fees_and_rewards`** pour synchroniser les données.
2. **Exécuter la fonction `collect_fees`** pour récupérer les jetons. Cela inclut les frais de transaction générés par les opérations sur le pool.

N'oubliez pas que les frais sont le résultat des échanges effectués par les traders dans le pool que vous avez créé ou rejoint. Plus votre part de liquidité est importante et plus l'activité sur le pool est élevée, plus vos frais potentiels seront conséquents.

## Comment collecter les récompenses

En ce qui concerne les récompenses sur Orca Whirlpools, elles sont légèrement différentes des frais, notamment dans leur mode de récupération. Ces récompenses proviennent typiquement de programmes d'incitation ou de staking proposés sur Solana.

Les récompenses sont gérées via des slots. Chaque pool peut avoir un maximum de trois récompenses actives simultanément, et celles-ci sont associées à différents indices (`rewardInfos[0..2]`). Pour collecter vos récompenses, il est nécessaire d'effectuer une vérification préalable pour identifier les récompenses disponibles pour chaque slot.

### Étapes pour collecter les récompenses :
1. **Vérifiez les récompenses disponibles** via les indices `rewardInfos[0..2]`.
2. Pour chaque slot contenant des récompenses applicables, **collectez-les individuellement** en utilisant leurs indices respectifs.
3. Assurez-vous d'avoir correctement mis à jour ces récompenses avant de procéder, en appelant `update_fees_and_rewards`.

Ce processus garantit que vous récupérez tout ce qui vous revient, selon votre contribution au pool.

---

En appliquant ces procédures pour collecter vos frais et récompenses, vous maximisez vos rendements sur Orca Whirlpools tout en apprenant à maîtriser les outils disponibles sur Solana. Cette approche méthodique apporte clarté et efficacité à vos activités sur l'AMM.

[source](https://dev.to/tomtomdu73/collecting-fees-and-rewards-from-orca-whirlpool-positions-5af5)