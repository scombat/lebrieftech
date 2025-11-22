---
title: "Créer un Protocole de Prêt Flash : Une Aventure sur Solana"
seoTitle: "Créer un Protocole de Prêt Flash sur Solana avec Anchor"
seoDescription: "Découvrez l'expérience de création d'un protocole de prêt flash sur Solana avec Anchor et explorez les défis et apprentissages liés au développement blockchain."
datePublished: Sat Nov 22 2025 15:24:38 GMT+0000 (Coordinated Universal Time)
cuid: cmiafwsng000102lgbmsfgo9h
slug: creer-protocole-pret-flash-solana-anchor
canonical: https://dev.to/ola-zoll/my-first-flash-loan-protocol-a-solana-adventure-3i4k

---

```markdown
# Créer un Protocole de Prêt Flash : Une Aventure sur Solana

## TL;DR

- Les prêts flash permettent d'emprunter sans garantie et nécessitent un remboursement dans la même transaction.
- Solana offre des spécificités techniques uniques, comme les comptes et l'atomicité des transactions, qui compliquent leur implémentation.
- Le projet utilise Rust et le framework Anchor pour configurer deux instructions essentielles : `borrow` et `repay`.
- Des défis comme l'introspection des instructions et la gestion des emprunts dans Rust ont été relevés.
- La sécurité repose sur des PDA (Program Derived Address) et la validation de chaque étape de transaction.

## Introduction aux prêts flash

Les prêts flash sont un outil central dans l'écosystème DeFi (finance décentralisée). Ils permettent à un utilisateur d'emprunter de grandes sommes d'argent sans fournir de garantie, à condition que le prêt soit utilisé et remboursé dans une seule transaction. Les principales utilisations incluent des stratégies comme l'arbitrage, la liquidation de positions ou encore l'échange de garanties.

La caractéristique clé qui garantit la sécurité des prêts flash est leur nature atomique. Une transaction entière réussit ou échoue comme un tout, éliminant ainsi le risque de perte pour le prêteur.

## Les défis du développement Solana

Développer un protocole de prêt flash sur Solana est particulièrement complexe pour plusieurs raisons :

1. **Différence fondamentale avec Ethereum** : Contrairement à Ethereum, les données sur Solana sont stockées dans des comptes spécifiques et non dans des espaces de stockage dédiés aux smart contracts.
2. **Atomicité strictement respectée** : Chaque instruction doit être gérée avec précision pour s'assurer que les emprunts et les remboursements s’effectuent dans un cadre sécurisé.
3. **Utilisation de Rust** : La gestion stricte des emprunts en mémoire, caractéristique de Rust, introduit des contraintes supplémentaires dans l'écriture du code.
4. **Analyse des instructions de transaction** : Solana offre une fonctionnalité unique d’introspection des instructions, qui permet d’examiner les étapes d’exécution d’une transaction, mais cet outil n'est pas trivial à utiliser correctement.

Pour répondre à ces défis, il a été crucial de tirer parti du framework Anchor, conçu pour simplifier le développement sur Solana.

## Comprendre les concepts de base de Solana

Pour développer un protocole robuste sur Solana, il est essentiel de comprendre certains concepts fondamentaux :

### Modèle basé sur les comptes

Sur Solana, tout passe par des comptes, qui stockent des données ou exécutent des programmes :

- Chaque compte a des propriétés spécifiques : un solde minimum doit être maintenu pour couvrir des frais d’hébergement ("rent"), et un compte peut être "possédé" par un smart contract, donnant au programme des droits exclusifs pour modifier les données de ce compte.
- Ce modèle réduit les risques de vulnérabilités classiques comme la réentrance, fréquente sur Ethereum.

### Atomicité et transactions

La notion d'atomicité est centrale : une transaction est soit entièrement exécutée, soit complètement annulée. Cela garantit qu'aucune somme d'argent empruntée dans un prêt flash ne peut être perdue ou utilisée de manière incorrecte.

### Introspection des instructions

Une des fonctionnalités uniques de Solana est l’introspection des transactions via des méthodes comme `load_instruction_at_checked()`. Cela permet de vérifier qu'une transaction contient bien les étapes nécessaires au bon déroulement du protocole, en examinant les instructions déjà exécutées.

## Développer un protocole de prêt flash

Le cœur du protocole repose sur deux instructions essentielles : `borrow` (emprunter) et `repay` (rembourser).

### Instruction `borrow`

L’instruction `borrow` a pour rôle de valider les conditions d’emprunt :

- Vérifier que l’instruction est bien la première de la transaction.
- Analyser la liste des instructions pour s'assurer qu'une instruction `repay` appropriée est présente dans la même transaction.
- Vérifier que les comptes impliqués sont valides et que les montants demandés respectent les limites imposées.

### Instruction `repay`

L’instruction `repay` est responsable de :

- Récupérer les informations issues de l’instruction `borrow`, notamment le montant emprunté.
- Calculer les frais associés (par exemple, 5 %).
- Effectuer le transfert des fonds empruntés ainsi que des frais vers le compte de trésorerie du protocole.

### Architecture et sécurité

Le protocole utilise des **Program Derived Addresses** (PDA) pour stocker et sécuriser les fonds. Les PDAs jouent le rôle d’un "coffre" auquel seul le programme peut accéder. Par ailleurs, des **comptes de tokens associés** (ATA) facilitent l'interaction des utilisateurs pour emprunter et rembourser.

## Leçons tirées des défis rencontrés

Travailler avec Solana et Anchor a mis en évidence plusieurs défis techniques spécifiques :

### Problèmes d'emprunts dans Rust

La gestion stricte des références ("borrows") dans Rust a obligé à réorganiser le code source pour éviter des erreurs liées aux références empruntées qui ne pouvaient pas coexister avec des appels à certaines fonctions.

### Introspection et parsing

Analyser les instructions d'une transaction s'est révélé difficile, en particulier lors de l’extraction des informations via le module sysvar d’instruction. Une meilleure compréhension des outils, notamment `load_instruction_at_checked()`, a permis de résoudre ces bugs.

### Validations rigoureuses

Dans un environnement décentralisé, les données doivent être systématiquement validées pour éliminer les potentiels vecteurs d'attaques. Cela inclut la double vérification des montants, des comptes et de l'ordre exact des instructions.

## Sécurisation des prêts flash grâce à l'introspection

L’approche choisie pour la sécurisation repose sur l’analyse approfondie des instructions d'une transaction :

- L’instruction `borrow` s’assure qu’une instruction `repay` valide est incluse. Cette validation inclut une vérification de l'identité des comptes et du montant emprunté.
- L’instruction `repay`, de son côté, valide l'intégrité des données extraites de l’instruction `borrow`, calcule les frais applicables, puis assure que les fonds retournent à la trésorerie par un canal sécurisé.

Cette combinaison de contrôles permet de minimiser le risque pour le prêteur.

---

Malgré les défis, développer un protocole de prêt flash sur Solana avec Anchor est une preuve de concept impressionnante des potentiels offerts par cette blockchain. Ce projet, bien que complexe, a permis d'explorer les pouvoirs de l'atomicité, de l’introspection et des Program Derived Addresses pour créer un produit efficace, sécurisé et pratique pour l'univers DeFi.
```

[source](https://dev.to/ola-zoll/my-first-flash-loan-protocol-a-solana-adventure-3i4k)