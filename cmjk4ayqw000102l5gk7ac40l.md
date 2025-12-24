---
title: "Utiliser TPM pour le cryptage des clés en Rust sous Linux"
seoTitle: "Guide de cryptage de clé TPM avec Rust sous Linux"
seoDescription: "Apprenez à configurer un TPM sur Linux pour le cryptage des clés avec Rust. Une méthode détaillée utilisant TPM matériel et vTPM."
datePublished: Wed Dec 24 2025 14:37:08 GMT+0000 (Coordinated Universal Time)
cuid: cmjk4ayqw000102l5gk7ac40l
slug: guide-cryptage-cle-tpm-rust-linux
canonical: https://dev.to/tsuruko12/how-i-used-tpm-for-key-encryption-in-rust-on-linux-hardware-tpm-vtpm-4ond

---

# Utiliser TPM pour le cryptage des clés en Rust sous Linux

## TL;DR

- Les TPM (Trusted Platform Module) sont des composants matériels utilisés pour sécuriser les clés cryptographiques et renforcer la confiance dans un système.
- Rust, en combinaison avec Linux, permet d'exploiter ces modules pour des processus de cryptage robustes.
- Vous pouvez configurer à la fois des TPM matériels et des vTPM (TPM virtuels) sous Linux pour gérer des clés de manière sécurisée.
- Ce guide explique comment configurer un TPM, créer une clé SRK, et utiliser Rust pour le cryptage/décryptage des données.

## Introduction aux TPM sur Linux

Un Trusted Platform Module (TPM) est une puce dédiée à la sécurité informatique, souvent intégrée directement dans les machines modernes. Il permet de générer, stocker et utiliser des clés cryptographiques dans un environnement isolé, offrant ainsi une couche supplémentaire de protection. Outre les TPM physiques, les utilisateurs de Linux peuvent également s'appuyer sur des TPM virtuels (vTPM), qui simulent les fonctionnalités du TPM matériel et sont particulièrement utiles pour les environnements virtualisés.

Les TPM sont couramment employés dans des cas d'usage tels que :
- Le stockage sécurisé des clés privées.
- L'attestation d'état de système fiable.
- Le renforcement de la chaîne de confiance.
  
Les développeurs Rust peuvent utiliser des bibliothèques spécifiques pour interagir avec des TPM via des API, en respectant les standards du Trusted Computing Group. Ce guide explore ces outils et propose une méthode pragmatique pour tirer parti des TPM sur Linux.

## Configuration du TPM sous Linux avec Rust

Avant de travailler avec un TPM ou vTPM sous Linux, il est nécessaire de configurer correctement votre environnement.

### Pré-requis
1. **Pour TPM matériel** :
   - Assurez-vous que votre machine est équipée d'un TPM et que celui-ci est activé au niveau du BIOS/UEFI.
   - Installez les paquets nécessaires, tels que `tpm2-tools` et `tpm2-tss`, qui permettent les interactions avec le TPM.

   ```bash
   sudo apt update
   sudo apt install -y tpm2-tools tpm2-tss
   ```

2. **Pour vTPM** :
   - Pour simuler un TPM, installez le package `swtpm`, qui fournit la fonctionnalité de TPM virtuel.
   - Configurez le vTPM pour qu’il soit accessible via une socket TCP.

   ```bash
   sudo apt update
   sudo apt install -y swtpm
   swtpm socket --tpmstate dir=/tmp/tpm --ctrl type=tcp,port=2321 --flags not-need-init --log level=2
   ```

### Configuration et vérification
Après avoir installé les outils nécessaires, vérifiez que votre instance TPM (matérielle ou virtuelle) fonctionne correctement.

Pour les TPM matériels, utilisez la commande suivante pour visualiser les propriétés du module :

```bash
tpm2_getcap -c properties-fixed
```

Pour les vTPM, vous pouvez vérifier son fonctionnement en utilisant des commandes similaires après avoir démarré le service `swtpm`.

---

## Création et maintien d'une clé SRK

Une étape fondamentale dans le travail avec les TPM est la génération d'une Root Key (SRK - Storage Root Key). Elle est utilisée pour chiffrer toutes les autres clés ou données sensibles.

### Génération de la clé SRK
L’outil `tpm2_createprimary` permet de générer une SRK via le TPM. Voici une commande typique pour la création d’une SRK :

```bash
tpm2_createprimary -C e -g sha256 -G rsa -c primary.ctx
```

Ce qui signifie :
- `-C e` : Utilisation de l'espace de stockage platform pour générer la clé.
- `-g sha256` et `-G rsa` : Utilisation de l'algorithme SHA-256 pour le hachage et RSA pour les opérations cryptographiques.
- `-c primary.ctx` : Fichier qui contiendra les détails de la clé générée.

### Persistance et gestion
Pour rendre cette SRK persistante, vous pouvez utiliser la commande `tpm2_evictcontrol`. Par exemple :

```bash
tpm2_evictcontrol -C o -c primary.ctx
```

Cela associera la clé générée à un espace de stockage persistant, de sorte qu’elle puisse être utilisée de façon répétée sans avoir à la recréer.

---

## Processus de cryptage et décryptage des clés

Une fois le TPM configuré et la SRK créée, il est possible de démarrer le processus de cryptage et de décryptage des données via l’utilisation de Rust.

### Bibliothèque TSS en Rust
Pour interagir avec un TPM, Rust propose la bibliothèque [rust-tss-esapi](https://github.com/parallaxsecond/rust-tss-esapi). Assurez-vous d'ajouter la dépendance correspondante à votre projet Rust :

```toml
[dependencies]
tss-esapi = "X.Y.Z"
```

### Cryptage des clés
Une fois la configuration effectuée, vous pouvez utiliser le TPM pour encrypter vos données sensibles. L'exemple suivant montre la logique de base pour encrypter des données avec une clé obtenue via votre SRK.

```rust
use tss_esapi::Context;
use tss_esapi::structures::{Digest, KeyedHashScheme};

fn encrypt_with_tpm() -> Result<(), Box<dyn std::error::Error>> {
    let mut context = Context::new(Context::default(), None)?;

    // Exemple de génération de hash
    let data_to_encrypt: &[u8] = b"Hello TPM!";
    let digest = Digest::try_from(data_to_encrypt)?;

    let enc_data = context.context_hmac(
        digest,
        KeyedHashScheme::HMAC_SHA256,
    )?;
    
    println!("Encrypted data: {:?}", enc_data);
    Ok(())
}
```

### Décryptage des clés
Le processus de décryptage implique une procédure similaire, où l’on inverse les actions réalisées durant le cryptage en exploitant la même clé de référence SRK.

---

## Conclusion et ressources utiles

Les TPM et vTPM offrent une solution robuste pour le stockage et la gestion des clés cryptographiques sous Linux. En utilisant des outils comme `tpm2-tools` ainsi que des bibliothèques Rust dédiées à l’interaction avec TPM, les développeurs peuvent mettre en place un système de gestion de clés sécurisé et fiable.

Pour aller plus loin, voici quelques ressources utiles :
- Documentation officielle sur [tpm2-tools](https://github.com/tpm2-software/tpm2-tools).
- Guide et exemple d’utilisation de [rust-tss-esapi](https://github.com/parallaxsecond/rust-tss-esapi).
- Tutoriel sur la mise en place de vTPM avec `swtpm` : [Linux Manual](https://github.com/stefanberger/swtpm).

En intégrant ces pratiques dans vos projets Rust, vous pouvez améliorer le niveau de sécurité et de confiance autour de vos données sensibles. Profitez pleinement des capacités offertes par les TPM, et explorez les possibilités des TPM virtuels pour les environnements cloud ou containers.

[source](https://dev.to/tsuruko12/how-i-used-tpm-for-key-encryption-in-rust-on-linux-hardware-tpm-vtpm-4ond)