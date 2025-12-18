---
title: "Un record pour les chiffres de Pi : 314 000 milliards calculés sur un serveur optimisé"
seoTitle: "314 000 milliards de chiffres de Pi calculés : Un record défiant Google Cloud"
seoDescription: "Découvrez comment un serveur local a établi un nouveau record en calculant 314 000 milliards de chiffres de Pi, surpassant Google Cloud en efficacité."
datePublished: Thu Dec 18 2025 20:23:23 GMT+0000 (Coordinated Universal Time)
cuid: cmjbw158o000002jsdwlcg8ns
slug: record-pi-314-trillion-digits-server-google-cloud
canonical: https://www.techradar.com/pro/anyone-for-a-slice-of-record-pi-new-landmark-sees-314-trillion-digits-calculated-as-news-site-trounces-google-cloud-for-now

---

# Un record pour les chiffres de Pi : 314 000 milliards calculés sur un serveur optimisé

## TL;DR

- Un serveur local, le Dell PowerEdge R7725, a calculé 314 000 milliards de chiffres de Pi en 110 jours.
- Configuration : AMD EPYC, 1,5 To de RAM DDR5, 40 SSD NVMe totalisant 2,1 PB.
- Énergie consommée : environ 4 305 kWh, 70 % de moins que les clusters cloud.
- Ce record bat les performances de Google Cloud (100 000 milliards en 2022).

## Contexte et pertinence

Le calcul de Pi est l'un des défis mathématiques et informatiques emblématiques de notre époque, souvent utilisé pour repousser les limites des technologies de calcul. Pendant des années, les supercalculateurs et les plateformes cloud, vantés pour leur puissance brute et leur scalabilité, ont dominé cette arena. En 2022, Google Cloud a établi un record impressionnant en calculant 100 000 milliards de chiffres de Pi.

Cependant, en 2025, une équipe de StorageReview a fait sensation en battant largement ce record, non pas en s'appuyant sur une infrastructure cloud, mais sur un serveur local spécialisé. En calculant 314 000 milliards de chiffres de Pi et en réduisant la consommation énergétique de 70 % par rapport aux clusters cloud, ce projet met en lumière les avantages des solutions sur mesure face aux plateformes généralisées.

Cette avancée ne se limite pas à une simple démonstration de force. Elle invite la communauté technique à repenser à la fois l'efficacité énergétique et l'optimisation des workloads dédiés.

## Les détails techniques derrière le record

La configuration matérielle du serveur Dell PowerEdge R7725 utilisé pour ce projet est impressionnante et révèle une attention minutieuse à chaque composant contribuant à la performance. Voici un aperçu des éléments clés :

### Architecture matérielle

Le serveur Dell PowerEdge R7725 repose sur une conception robuste optimisée pour traiter des charges de calcul intenses. Il est équipé de :

- **Deux processeurs AMD EPYC 9965** offrant un total de 384 cœurs physiques.
- **1,5 To de mémoire DDR5**, permettant de gérer d'immenses volumes de données en temps réel.
- **40 SSD NVMe Micron 6550 Ion** fournissant une capacité brute totale de 2,1 PB.

### Gestion du stockage

Pour maximiser la performance et la fiabilité, le stockage a été configuré comme suit :

- **Mode JBOD (Just a Bunch Of Disks)** : 34 disques ont été consacrés à la gestion des zones tampons.
- **RAID logiciel** : Les 6 disques restants ont été affectés à la sortie finale.

Les performances des disques sont tout aussi impressionnantes :

- Lecture logique totale : **132 PB**.
- Écriture logique totale : **112 PB**.
- Chaque disque individuel a traité en moyenne **7,3 PB** d'écritures.
- La taille maximale des sauvegardes intermédiaires (checkpoints) atteignait **774 TiB**.

### Consommation énergétique

Un des aspects les plus remarquables du projet concerne l'efficacité énergétique :

- **Total consommé sur 110 jours** : 4 305 kWh, soit environ **13,7 kWh par mille milliards de chiffres calculés**.
- Par comparaison, des clusters cloud capables de réaliser des calculs similaires consomment typiquement environ **33 000 kWh** pour 300 000 milliards de chiffres.

Cette consommation réduite démontre l'impact positif d'une configuration sur mesure optimisée pour un workload spécifique.

## Comparaison entre serveur local et cloud

Historiquement, les infrastructures cloud se démarquent par leur scalabilité : elles permettent de mobiliser des milliers de nœuds distribués pour s'adapter à des tâches massives. Cependant, cette approche a souvent un coût énergétique élevé et repose davantage sur une capacité brute que sur l'optimisation stricte de chaque composant.

En contraste, StorageReview a tiré parti d'une solution inscrite dans le paradigme "on-premises". Le recours à un serveur physique hautement spécialisé a permis d'éliminer les inefficacités liées à la gestion d'un large réseau de nœuds et de ressources partagées comme dans le cloud. Les avantages et inconvénients des deux approches méritent d’être analysés :

### Avantages de l'approche locale

1. **Efficacité optimisée** : La configuration matérielle a été fine-tunée pour répondre précisément à l'objectif du calcul de Pi.
2. **Consommation énergétique réduite** : Dans le cas du projet StorageReview, les économies d'énergie sont majeures.
3. **Coûts directs maîtrisés** : L'absence de frais récurrents propres aux abonnements basés sur le cloud peut représenter une économie dans certains cas.

### Inconvénients potentiels

1. **Scalabilité limitée** : Une solution locale reste figée dans sa capacité matérielle et ne peut s'étendre à d'autres types de workloads ou à des calculs de plus grande échelle sans coûts additionnels conséquents.
2. **Maintenance complexe** : La gestion d'une infrastructure locale nécessite des compétences spécifiques et engendre des frais récurrents d'entretien.

Le choix entre ces deux approches repose donc largement sur les spécificités du problème informatique à résoudre et sur les priorités de l’organisation, qu'elles soient économiques ou techniques.

## Implications pour l’avenir des solutions informatiques

Le record établi par StorageReview soulève des questions importantes sur l'équilibre à trouver entre les solutions locales et le recours à des infrastructures cloud. La montée en puissance des supercalculateurs, combinée à l’optimisation matérielle, montre que le "local" n’a pas perdu de sa pertinence, en particulier pour des workloads spécialisés.

### Vers une diversification des approches

Ce cas souligne que l’avenir des solutions informatiques n'est pas nécessairement dominé par une seule méthode. Des serveurs locaux optimisés peuvent être une alternative viable dans des scénarios où :

- L’efficacité énergétique est critique.
- Les tâches sont bien définies et ne dépendent pas de la scalabilité offerte par le cloud.
- Les coûts d’abonnement au cloud sont prohibitifs pour des workloads intenses mais temporaires.

### Adaptabilité : clé de la stratégie informatique

Ce record rappelle également que l’efficacité d’une solution dépend intrinsèquement de sa capacité à répondre à un besoin spécifique. Les entreprises doivent impérativement évaluer les contraintes de leurs workloads, en menant des calculs coût-avantage entre les options cloud, on-premises et hybrides.

### Un jalon pour le futur

Au-delà de l'exploit technique, ce projet ouvre la voie à une réflexion sur la manière dont nous abordons l'explosion des données et les ressources nécessaires pour les traiter. Ce n'est pas uniquement une démonstration de technologie, mais une remise en question des paradigmes actuels en informatique.



[source](https://www.techradar.com/pro/anyone-for-a-slice-of-record-pi-new-landmark-sees-314-trillion-digits-calculated-as-news-site-trounces-google-cloud-for-now)