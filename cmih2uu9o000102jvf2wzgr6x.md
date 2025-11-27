---
title: "Comment collecter frais et récompenses sur Orca Whirlpool (Solana)"
seoTitle: "Guide : Collecter les frais et récompenses des positions Orca Whirlpool sur Solana"
seoDescription: "Apprenez à collecter les frais et récompenses des positions Orca Whirlpool sur Solana grâce à ce guide détaillé utilisant Anchor et whirlpool_cpi."
datePublished: Thu Nov 27 2025 06:53:35 GMT+0000 (Coordinated Universal Time)
cuid: cmih2uu9o000102jvf2wzgr6x
slug: collecter-frais-recompenses-orca-whirlpool-solana
canonical: https://dev.to/tomtomdu73/collecting-fees-and-rewards-from-orca-whirlpool-positions-5af5

---

# Comment collecter frais et récompenses sur Orca Whirlpool (Solana)

## TL;DR

- Orca Whirlpool est une plateforme de pools de liquidité concentrée sur la blockchain Solana.
- Avant de collecter des frais et récompenses, vous devez obligatoirement mettre à jour les informations avec l'instruction `update_fees_and_rewards`.
- Une fois les données mises à jour, utilisez les fonctions CPI comme `collect_fees` et `rewardInfos[index]` pour récupérer les frais et récompenses.
- Ce guide explique comment utiliser Anchor et le crate `whirlpool_cpi` pour exécuter ces collectes efficacement.

## Introduction à Orca Whirlpool

Orca Whirlpool est une solution AMM (Automated Market Maker) fonctionnant sur la blockchain Solana. Cette plateforme introduit le concept de liquidité concentrée, permettant aux fournisseurs de maximiser leur rendement en se concentrant sur des plages de prix spécifiques, contrairement aux AMM "classiques" où la liquidité est répartie uniformément sur l'ensemble du spectre des prix.

En intégrant un pool Whirlpool sur Orca, les utilisateurs peuvent gagner des frais de transaction générés par les trades effectués dans cette plage de prix. En plus des frais, certains pools permettent également de gagner des récompenses sous forme de jetons spéciaux, distribués selon des règles définies par les opérateurs du pool.

Pour récupérer ces frais et récompenses, des instructions spécifiques doivent être exécutées dans le cadre des contrats intelligents Solana.

## Étape critique avant la collecte

Avant de procéder à la collecte des frais et des récompenses, il est impératif de mettre à jour les informations pertinentes. Cela est réalisé grâce à l'instruction `update_fees_and_rewards`. Cette étape garantit que les champs associés aux profits sont correctement calculés et actualisés.

### Pourquoi cette mise à jour est-elle essentielle ?

Les informations relatives aux frais et récompenses ne sont pas automatiquement mises à jour lors des opérations dans le pool. Par conséquent, si vous tentez d'exécuter une collecte sans avoir au préalable utilisé `update_fees_and_rewards`, ces champs resteront vides ou à zéro. Vous risqueriez donc de manquer les profits potentiels dus à vos positions.

## Collecter les frais

Une fois les frais mis à jour, vous pouvez récupérer les jetons accumulés dans votre position Whirlpool en exécutant l'instruction `collect_fees`. Cette fonction utilise un contexte CPI (Cross-Program Invocation) pour interagir avec le programme Whirlpool et transférer les jetons générés par les transactions du pool.

### Procédure

1. Mettez à jour les frais avec `update_fees_and_rewards`.
2. Exécutez la fonction CPI `collect_fees`. Cette opération transférera les jetons A et B (correspondant aux frais collectés) de la position Whirlpool vers votre portefeuille.

#### Exemple simplifié de code en Rust

```rust
// Exemple de structure du contexte CPI pour collecter les frais
let cpi_accounts = CollectFees {
    whirlpool: whirlpool_account,
    fee_receiver_token_a: user_token_a_account,
    fee_receiver_token_b: user_token_b_account,
    position_authority: user_account,
};

let cpi_ctx = CpiContext::new(program_id, cpi_accounts);
whirlpool_cpi::collect_fees(cpi_ctx)?;
```

## Collecter les récompenses

En plus des frais, certains pools Whirlpool offrent des récompenses aux fournisseurs de liquidité. Ces récompenses sont affichées dans des "slots" spécifiques et sont associées à des mint (jetons) et des vaults.

### Comment récupérer ces récompenses ?

1. **Vérifiez les slots actifs** : Les récompenses disponibles pour la position se trouvent dans `rewardInfos[index]`. Il est nécessaire d'itérer à travers les slots actifs pour identifier les récompenses à collecter.
2. **Exécutez la collecte** : Utilisez l'instruction appropriée qui associe l'index, la mint du token et le vault correspondant au slot.

#### Exemple simplifié de code en Rust

```rust
// Parcourir les slots pour collecter les récompenses
for index in active_reward_slots {
    let reward_info = whirlpool_account.reward_infos[index];

    let cpi_accounts = CollectReward {
        whirlpool: whirlpool_account,
        reward_vault: reward_info.vault,
        reward_receiver: user_reward_account,
        position_authority: user_account,
        reward_owner: user_account,
    };

    let cpi_ctx = CpiContext::new(program_id, cpi_accounts);
    whirlpool_cpi::collect_reward(cpi_ctx)?;
}
```

### Précautions à prendre

- Assurez-vous que la récompense à collecter est bien disponible dans le slot défini.
- N’oubliez pas que les mints associés aux récompenses peuvent varier d’un slot à l’autre.

## Résumé

Orca Whirlpool sur Solana offre une solution innovante pour les fournisseurs de liquidité à la recherche de rendements élevés. Cependant, pour maximiser vos profits, il est crucial de suivre les bons processus de collecte de frais et de récompenses :

1. Toujours mettre à jour les informations avec `update_fees_and_rewards` avant toute collecte.
2. Utilisez la fonction CPI `collect_fees` pour récupérer les jetons issus des frais de transactions.
3. Inspectez les slots disponibles pour identifier les récompenses actives, puis collectez-les en précisant les paramètres de chaque slot.

Ce guide vous fournit les bases nécessaires pour automatiser ces opérations dans vos contrats intelligents Solana, en tirant parti d'Anchor et des fonctionnalités de `whirlpool_cpi`. Que vous débutiez sur Solana ou que vous soyez déjà expérimenté, maîtriser ces mécanismes vous permettra de tirer pleinement parti de vos positions sur Orca Whirlpool et de maximiser les bénéfices.

[source](https://dev.to/tomtomdu73/collecting-fees-and-rewards-from-orca-whirlpool-positions-5af5)