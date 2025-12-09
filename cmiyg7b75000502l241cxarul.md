---
title: "Ce que l’on sait des rançongiciels pour VMware ESXi"
seoTitle: "Rançongiciels ciblant VMware ESXi : menace croissante en 2025"
seoDescription: "Les rançongiciels ciblant VMware ESXi augmentent rapidement. Trois types d'attaques et franchises comme Akira soulignent la tendance de 2025."
datePublished: Tue Dec 09 2025 10:39:17 GMT+0000 (Coordinated Universal Time)
cuid: cmiyg7b75000502l241cxarul
slug: rancongiciels-vmware-esxi-menace-2025
canonical: https://www.lemagit.fr/conseil/Ce-que-lon-sait-des-rancongiciels-pour-VMware-ESXi

---

# Ce que l’on sait des rançongiciels pour VMware ESXi

## TL;DR

- Les infrastructures virtualisées avec VMware ESXi sont une cible de choix pour les rançongiciels, avec une intensification des attaques.
- Trois grandes approches sont utilisées : rançongiciels dédiés, variantes adaptées pour Linux, et scripts artisanaux.
- Les franchises Akira, Babuk et LockBit dominent la scène des cyberattaques sur les hyperviseurs.
- En 2025, les attaques sur ESXi représentent jusqu’à 25 % de toutes les cybermenaces liées aux hyperviseurs.
- La sécurisation des environnements virtualisés est désormais une priorité absolue.

## Contexte et pertinence des attaques sur ESXi

Les environnements de virtualisation, particulièrement ceux basés sur VMware ESXi, sont devenus des cibles privilégiées des groupes cybercriminels. En ciblant un hyperviseur, les attaquants parviennent à affecter toutes les machines virtuelles hébergées simultanément, aggravant l’impact et la pression sur les victimes pour qu’elles cèdent aux demandes de rançon.

Un tournant important a été l’attaque **ESXiArgs** en février 2023, qui a révélé des vulnérabilités spécifiques d’ESXi et l’efficacité des scripts dédiés au chiffrement. Ce type d’attaque montre un intérêt croissant des cybercriminels pour les infrastructures virtualisées et leur recherche constante de nouvelles techniques.

## Trois catégories d’attaques sur VMware ESXi

### 1. Rançongiciels dédiés à ESXi
Certains groupes développent des rançongiciels spécifiquement adaptés pour cibler les hyperviseurs VMware. Ces logiciels sont conçus pour exploiter les particularités des environnements ESXi et maximiser les dégâts infligés.

### 2. Rançongiciels Linux accompagnés de scripts additionnels
Ces attaques utilisent des rançongiciels classiques pour Linux, combinés avec des scripts visant les fonctionnalités spécifiques des hyperviseurs. Par exemple, des outils comme `esxcli` permettent d’arrêter les machines virtuelles avant de passer au chiffrement des fichiers.

Le cas **ESXiArgs** est emblématique de cette méthode : un simple script Shell peut suffire à interrompre les VMs avant de crypter en masse les disques virtuels et fichiers de configuration.

### 3. Scripts artisanaux
Enfin, certaines attaques reposent uniquement sur des scripts personnalisés. Ces scripts, souvent en Shell ou Python, contournent les étapes complexes du développement logiciel pour cibler directement les données des environnements ESXi.

## Chronologie des ransomware ciblant ESXi

### 2020
- **RansomExx** inaugure une vague de ransomwares Linux capables de chiffrer les machines virtuelles ESXi.
- **DarkSide** commence à explorer les hyperviseurs comme ESXi dans ses attaques.

### 2021
- Apparition du groupe **Babuk**, avec des variantes visant directement ESXi.
- D'autres acteurs comme **Ragnar**, **REvil**, **Hive** et **Conti** suivent rapidement cette tendance.

### 2022
- Expansion des franchises avec l’intégration de groupes tels que **LockBit**, **BlackCat** et **AvosLocker**.
- Des nouveaux ransomwares comme **CheersCrypt** émergent, souvent liés à **Babuk**.

### 2023–2024
- Les variantes se diversifient : **Royal**, **Money Message**, **Monti**, ainsi que des acteurs comme **Cicada3301** ou **Qilin/Agenda** adaptent leurs techniques pour cibler ESXi.

## Modes opératoires et outils utilisés

Le ciblage des environnements ESXi suit un processus similaire dans la plupart des attaques :

1. **Arrêt des machines virtuelles** pour garantir le chiffrement complet des données sans conflit.
2. **Chiffrement des disques et fichiers clés**, y compris les disques virtuels (VMDK) et les métadonnées de configuration.

Certaines attaques se distinguent par l’ajout d’extensions spécifiques pour marquer les fichiers compromis (ex. : `.PLAY`).

### Outils et scripts complémentaires
Les ransomwares comme **Babuk**, **Akira/Linux** ou **Luna** utilisent rarement des fonctions directement intégrées pour ESXi. À la place, les attaquants exploitent des scripts tiers en Shell ou Python pour automatiser le traitement des données.

Un exemple notable est celui du **SEXi ransomware**, qui a évolué en 2024 avec la variante **APT INC**, illustrant l’adoption continue de scripts polyvalents pour cibler les infrastructures virtualisées.

## Tendance observée en 2025

D'après les analyses de **Huntress**, les attaques visant les hyperviseurs (ESXi, Hyper-V, etc.) ont connu une progression fulgurante en 2025 :

- Au premier semestre, seulement 3 % des cyberattaques ciblaient les plateformes virtualisées.
- Au second semestre, ce chiffre est monté jusqu’à 25 %, signifiant une évolution majeure dans les priorités des acteurs malveillants.

Le groupe **Akira** est particulièrement actif, non seulement sur VMware ESXi, mais également sur d’autres infrastructures comme celles de Nutanix.

## À surveiller et risques

Plusieurs points clés méritent une attention renforcée :

- L’augmentation rapide des variantes de ransomware sophistiquées ciblant directement les environnements ESXi.
- L’usage répandu de scripts facilement exécutables, rendant les attaques accessibles à un plus grand nombre de groupes criminels.
- La faiblesse de certains outils de sécurité traditionnels à détecter et bloquer ces menaces spécifiques aux hyperviseurs.

## Points clés à retenir

La menace des rançongiciels pour VMware ESXi continue de croître, poussée par la multiplication des groupes criminels et l’évolution des techniques d’attaque. Protéger les environnements virtualisés exige une vigilance accrue, des contrôles renforcés, et une surveillance proactive pour contrer cette tendance en 2025.

[source](https://www.lemagit.fr/conseil/Ce-que-lon-sait-des-rancongiciels-pour-VMware-ESXi)