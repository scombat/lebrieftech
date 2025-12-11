---
title: "Trois vulnérabilités PCIe 5.0 exposent les systèmes à des risques critiques"
seoTitle: "Les failles de chiffrement PCIe 5.0 et leur impact sur la sécurité des systèmes"
seoDescription: "Trois vulnérabilités liées au protocole IDE PCIe 5.0 exposent les systèmes à des risques critiques : divulgation d'informations, accès non autorisé et déni de service."
datePublished: Thu Dec 11 2025 13:33:42 GMT+0000 (Coordinated Universal Time)
cuid: cmj1hbbdh000602jsglyc2wl8
slug: pcie-5-0-failles-de-chiffrement-et-risques-de-securite
canonical: https://thehackernews.com/2025/12/three-pcie-encryption-weaknesses-expose.html

---

# Trois vulnérabilités PCIe 5.0 exposent les systèmes à des risques critiques

## TL;DR

- Trois failles découvertes dans le chiffrement IDE des systèmes PCIe 5.0+.
- Risques identifiés : divulgation d'informations, escalade de privilèges et déni de service.
- Gravité jugée faible selon les scores CVSS, mais critique dans des environnements sensibles.
- Les attaques nécessitent un accès physique ou au niveau matériel.

## Qu'est-ce que le PCIe et pourquoi est-il important ?

Le **PCIe (Peripheral Component Interconnect Express)** est une norme essentielle dans le domaine des systèmes informatiques modernes. Il permet de connecter des périphériques matériels aux cartes mères, tels que :

- Cartes graphiques
- Cartes son
- Dispositifs de stockage
- Adaptateurs réseau (Ethernet, Wi-Fi)

Les performances et l'efficacité de PCIe ont constamment évolué. L'arrivée de PCIe 6.0 a marqué une étape cruciale en intégrant le protocole **IDE (Integrity and Data Encryption)**. Ce dernier introduit des mécanismes de chiffrement et de vérification d'intégrité pour sécuriser les transferts de données. Toutefois, des vulnérabilités critiques dans les versions 5.0 et ultérieures remettent en question la fiabilité de ce protocole au sein des architectures modernes.

### Pertinence des systèmes PCIe 5.0+

Les systèmes PCIe sont largement utilisés dans des environnements sensibles :

- Infrastructure de serveurs
- Architectures basées sur des zones de confiance matérielle
- Systèmes critiques d'entreprise et d'ingénierie

D'où l'importance de garantir leur sécurité face à des attaques potentielles.

## Détails des failles de sécurité découvertes

Trois vulnérabilités ont été identifiées par une équipe de chercheurs d'Intel composée de **Arie Aharon**, **Makaram Raghunandan**, **Scott Constable** et **Shalini Sharma**. Ces failles concernent spécifiquement le mécanisme **IDE** utilisé dans PCIe 5.0+ :

### CVE-2025-9612 — Forbidden IDE Reordering

Un défaut dans les tests d'intégrité au niveau des ports récepteurs permet un réordonnancement non autorisé du trafic PCIe. Cela peut conduire à la consommation de données obsolètes ou corrompues.

### CVE-2025-9613 — Completion Timeout Redirection

Lorsqu'un délai d'expiration survient, la gestion incorrecte des purges de données offre une opportunité d'injecter des paquets avec des tags similaires à ceux des paquets purgeables. Cette faille peut permettre aux acteurs malveillants de manipuler les flux de données.

### CVE-2025-9614 — Delayed Posted Redirection

Une purge incomplète ou une synchronisation défaillante dans le renouvellement des flux IDE peut amener le récepteur à accepter des données incorrectes. Les conséquences incluent des erreurs de traitement ou des brèches dans l'intégrité des données.

## Impact des failles sur la sécurité des systèmes

Bien que les trois vulnérabilités soient classées comme ayant un **impact faible** (scores CVSS v3.1 : 3.0, CVSS v4 : 1.8), elles présentent des risques significatifs dans les environnements critiques utilisant PCIe 5.0+.

### Risques identifiés

1. **Divulgation d'informations sensibles** :
   Les failles permettent à un attaquant de compromettre la confidentialité des données transmises via PCIe.

2. **Escalade de privilèges** :
   L'accès physique ou bas niveau requis peut favoriser des attaques internes ou ciblées dans des environnements où les privilèges sont strictement segmentés.

3. **Déni de service** :
   En exploitant les erreurs de gestion des flux, un attaquant peut perturber le fonctionnement normal des systèmes pendant des périodes prolongées.

### Systèmes matériels concernés

Les architectures suivantes sont touchées :

- **Intel** :
  - Xeon 6 Processors (P-cores)
  - Xeon 6700P-B/6500P-B SoCs
- **AMD** :
  - EPYC 9005 Series
  - EPYC Embedded 9005 Series

Ces systèmes, souvent utilisés dans des environnements critiques, sont particulièrement vulnérables aux attaques ciblées.

## Recommandations pour les fabricants et utilisateurs

Les acteurs de l’industrie doivent agir rapidement pour réduire les risques liés aux failles identifiées. Voici les recommandations principales :

### Mesures pour fabricants

1. **Mise à jour vers le standard PCIe 6.0** :
   Les fabricants doivent intégrer les mécanismes corrigés du protocole IDE décrits dans le standard PCIe 6.0.

2. **Application des recommandations d'Erratum #1** :
   PCI-SIG a publié un document technique détaillant les ajustements nécessaires pour sécuriser les flux IDE.

3. **Amélioration des tests d'intégrité et vérifications au niveau matériel** :
   Ces tests doivent être systématiquement appliqués au niveau des ports récepteurs pour éviter les failles de réordonnancement.

### Mesures pour utilisateurs finaux

- Installer les mises à jour de firmware dès leur publication par les fabricants matériels (Intel, AMD, ou autres).
- Vérifier si le protocole IDE est activé et évaluer sa pertinence pour les environnements sensibles.
- Dans les serveurs critiques, limiter les accès physiques au matériel et privilégier des politiques de sécurité stricte.

## À surveiller / risques potentiels

1. **Attaques nécessitant un accès physique ou insider** :
   Les environnements où la confiance entre utilisateurs est compromise sont plus susceptibles d’être concernés.

2. **Environnements sensibles hautement exposés** :
   Les serveurs critiques sont particulièrement vulnérables aux attaques exploitant les flux IDE.

3. **Retards dans les mises à jour des standards** :
   Certains fabricants peuvent tarder à implémenter les corrections des failles dans les versions futures de PCIe.

## À retenir

- Trois vulnérabilités impactent les systèmes PCIe 5.0+ via le protocole IDE.
- Bien que leur gravité soit globalement faible, les conséquences peuvent être sérieuses dans des environnements critiques et sensibles.
- Les fabricants et utilisateurs doivent travailler conjointement pour appliquer les mises à jour nécessaires et limiter les accès physiques aux infrastructures vulnérables.

[source](https://thehackernews.com/2025/12/three-pcie-encryption-weaknesses-expose.html)