---
title: "Comment collecter les frais et récompenses des positions Orca Whirlpool"
seoTitle: "Comment collecter les frais et récompenses des positions Orca Whirlpool"
seoDescription: "Apprenez à récupérer efficacement les frais et récompenses des positions Orca Whirlpool sur Solana grâce à ce guide pratique détaillé."
datePublished: Thu Nov 27 2025 06:53:34 GMT+0000 (Coordinated Universal Time)
cuid: cmih2utr6000002l7dz9w2sg7
slug: collecting-fees-and-rewards-from-orca-whirlpool-positions
canonical: https://dev.to/tomtomdu73/collecting-fees-and-rewards-from-orca-whirlpool-positions-5af5

---

# Comment collecter les frais et récompenses des positions Orca Whirlpool

## TL;DR

- **Orca Whirlpools** est un AMM à liquidité concentrée sur la blockchain Solana, permettant de gagner des frais et des récompenses en fournissant de la liquidité.  
- Pour récupérer vos frais, il faut appeler les fonctions spécifiques pour mettre à jour les données, puis collecter les jetons.
- Les récompenses sont accessibles en interagissant avec le tableau des indices disponibles via des appels à la fonction dédiée.
- Anchor et la librairie `whirlpool_cpi` sont des outils clés pour simplifier l’interaction avec le contrat intelligent Orca.

---

## Introduction à Orca Whirlpools et à la liquidité concentrée

Le protocole **Orca Whirlpools** s’appuie sur le concept de liquidité concentrée, une innovation dans le domaine des Automated Market Makers (AMMs), qui permet une gestion plus efficace des fonds. Contrairement aux plateformes AMM classiques, qui répartissent la liquidité uniformément sur toute la plage de prix, Orca Whirlpools permet aux fournisseurs de liquider leurs ressources sur une plage définie. Cela optimise l’utilisation des fonds et le rendement des frais pour les utilisateurs.

En tant que fournisseur de liquidité sur Orca Whirlpools, vous gagnez des **frais de trading** ainsi que des **récompenses**, qui sont des incitations supplémentaires basées sur les tokens offerts par le protocole ou ses partenaires.

Cependant, la gestion et la collecte de ces frais et récompenses nécessitent une interaction directe avec les smart contracts sur la blockchain **Solana**, souvent via des outils comme **Anchor** et des librairies spécifiques, notamment **whirlpool_cpi**.

---

## Les étapes critiques pour récupérer vos frais et récompenses

Quand vous fournissez de la liquidité sur Orca Whirlpools, les récompenses et les frais associés à vos positions ne sont pas automatiquement transférés. Pour les collecter, il faut suivre deux étapes principales : la mise à jour des données et la collecte effective.

### 1. Mise à jour des frais et des récompenses

La mise à jour des frais et des récompenses est essentielle. Sur Orca Whirlpools, cette étape se fait en appelant la fonction spécifique `updateFeesAndRewards`. Celle-ci permet au contrat d’évaluer les frais et les récompenses accumulés sur vos positions depuis le dernier point de calcul.

Cette opération est indispensable avant toute tentative de récupération, car elle garantit que les informations des frais et des récompenses sont à jour dans l’état du smart contract.

```rust
// Exemple d'appel pour mettre à jour les données via whirlpool_cpi
whirlpool_cpi::update_fees_and_rewards(ctx.accounts.whirlpool_context(), position_key)?;
```

---

## Collecter des frais avec Orca Whirlpools

Une fois que les données sont actualisées, vous pouvez procéder à la **collecte des frais** acquis sur vos positions. Ces frais sont généralement distribués sous la forme de jetons qu'il est possible de retirer depuis la piscine.

La fonction principale utilisée ici est `collectFees`. Elle vous permet de collecter les frais accumulés dans votre compte à partir de la position Whirlpool.

```rust
// Exemple d'appel pour récupérer les frais
let fee_collected = whirlpool_cpi::collect_fees(
    ctx.accounts.whirlpool_context(),
    &ctx.accounts.fee_receivers,
    position_key,
)?;
```

Vous devez vous assurer que les comptes liés à vos positions sont bien configurés et que la fonction `updateFeesAndRewards` a été appelée au préalable.

---

## Collecter des récompenses sur Solana

Pour récupérer les **récompenses**, le processus est légèrement différent des frais. Les récompenses Orca sont attachées à des indices spécifiques au sein d’un tableau nommé `rewardInfos`. Ce tableau contient des informations sur les récompenses disponibles pour chaque position.

Chaque élément du tableau correspond à une récompense active, et il faut interagir avec **les indices actifs** pour collecter les tokens associés. Pour cela, on utilise la fonction `collectRewardsOrcaPosition`.

```rust
// Exemple pour collecter une récompense spécifique
whirlpool_cpi::collect_rewards(
    ctx.accounts.whirlpool_context(),
    reward_index,
    ctx.accounts.reward_receiver,
    position_key,
)?;
```

En général, un fournisseur de liquidités doit donc parcourir chaque `reward_index` pour collecter l'intégralité des récompenses associées à une position. Cette étape est cruciale pour ne pas laisser de gains non collectés dans la piscine de liquidité.

---

## Résumé rapide

La gestion des frais et des récompenses dans **Orca Whirlpools** repose sur les étapes suivantes :

1. **Mettre à jour les frais et récompenses** : Utilisez `updateFeesAndRewards` pour synchroniser les données des positions avec le smart contract.
2. **Récupérer les frais** : Appelez la fonction `collectFees` pour obtenir les jetons accumulés dans les positions.
3. **Récupérer les récompenses** : Parcourez les indices actifs du tableau `rewardInfos` et utilisez `collectRewardsOrcaPosition` pour collecter chaque récompense individuellement.

Grâce à la librairie **whirlpool_cpi** et au framework **Anchor**, les développeurs ont à leur disposition des outils puissants pour automatiser et optimiser ces processus complexes. Ces méthodes sont indispensables pour maximiser vos gains et exploiter pleinement le potentiel d’un AMM de liquidité concentrée sur Solana.

[source](https://dev.to/tomtomdu73/collecting-fees-and-rewards-from-orca-whirlpool-positions-5af5)