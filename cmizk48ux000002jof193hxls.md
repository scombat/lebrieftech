---
title: "Reconnaissance des exportations de substances appauvrissant l'ozone grâce au Machine Learning"
seoTitle: "Détection des substances appauvrissant l'ozone avec le Machine Learning non supervisé"
seoDescription: "Utilisation du machine learning non supervisé pour identifier les schémas de commerce suspect dans les données douanières globales concernant les substances appauvrissant la couche d'ozone."
datePublished: Wed Dec 10 2025 05:16:38 GMT+0000 (Coordinated Universal Time)
cuid: cmizk48ux000002jof193hxls
slug: detection-substances-ozone-machine-learning
canonical: https://arxiv.org/abs/2512.07864

---

# Reconnaissance des exportations de substances appauvrissant l'ozone grâce au Machine Learning

## TL;DR

- Une approche basée sur le machine learning non supervisé permet d’analyser les données douanières complexes pour détecter des schémas commerciaux inhabituels.
- Des techniques comme le clustering K-Means, la détection d’anomalies (Isolation Forest et IQR) et l’utilisation de règles heuristiques permettent de repérer les transactions suspectes.
- Les anomalies identifiées incluent des "méga-transactions", des descriptions ambiguës ou des valeurs par kilogramme hors normes.
- Les résultats sont validés grâce à l’IA explicable (SHAP) et centralisés dans un pipeline efficace pour aider à la surveillance règlementaire.

## Introduction

Les substances appauvrissant la couche d'ozone représentent une menace sérieuse pour l'environnement mondial. Leur commerce est strictement réglementé par des accords internationaux tels que le Protocole de Montréal. Cependant, le suivi et l’analyse des transactions liées à ces substances dans les données douanières restent une tâche extrêmement complexe. La variété des informations (poids, valeur, descriptions) et leur volume croissant posent des défis importants pour les autorités réglementaires.

Afin de relever ce défi, une approche innovante reposant sur le machine learning non supervisé permet d’exploiter ces vastes ensembles de données et de repérer des anomalies ou des schémas commerciaux hors normes. Cette méthode vise à automatiser et améliorer les processus de surveillance tout en fournissant des indicateurs exploitables pour les décideurs.

## Méthodologie basée sur le machine learning

### Techniques utilisées

Divers outils et algorithmes d’apprentissage automatique ont été intégrés pour analyser les données commerciales et détecter les anomalies :

1. **Clustering K-Means**  
   Le clustering K-Means a permis d’organiser les données en groupes homogènes, basés sur des caractéristiques naturelles telles que la valeur totale des expéditions et leur poids. Ces groupes ont été utiles pour identifier des archétypes commerciaux et repérer des écarts par rapport à des comportements normaux.

2. **Détection d'anomalies**  
   Deux techniques principales ont été utilisées pour identifier des expéditions suspectes :
   - **Isolation Forest** : Cet algorithme isole les points de données atypiques en se basant sur leur rareté dans l'ensemble.
   - **IQR (Interquartile Range)** : Cette approche a permis de repérer des anomalies statistiques, notamment des ratios valeur-poids exceptionnellement élevés ou des transactions disproportionnées en termes de volume.  
   Ces méthodes ont révélé des "méga-transactions", des expéditions où les valeurs ou les volumes sont extrêmement élevés au regard des normes industrielles.

3. **Flagging heuristique**  
   Un ensemble de règles heuristiques a été appliqué pour détecter des descriptions de marchandises ambiguës ou vagues. Les descriptions floues peuvent être intentionnellement utilisées pour masquer la nature réelle des produits expédiés, rendant leur surveillance essentielle.

### Score de priorité

Les résultats des techniques ci-dessus ont été combinés dans un **score de priorité** pour chaque expédition. Ce score est conçu pour classer les transactions selon leur probabilité d’être suspectes. Les autorités douanières peuvent ainsi concentrer leurs efforts de contrôle sur les expéditions présentant des risques élevés.

### Validation des résultats avec l’IA explicable

Pour assurer la transparence et la compréhension des résultats générés par le cadre, l’IA explicable, notamment via les valeurs SHAP, a été utilisée. Cette technologie permet de mieux comprendre pourquoi certaines transactions ont été classées comme suspectes, en identifiant les variables qui ont le plus contribué aux décisions du modèle. Les facteurs clés incluent le ratio valeur-poids et les descriptions vagues.

### Résultats principaux

- **Anomalies détectées** : Le cadre développé a permis d’identifier **1 351 anomalies de prix** et **1 288 expéditions prioritaires**. Ces anomalies sont principalement caractérisées par des ratios valeur/poids inhabituels et des descriptions de produits non spécifiques.
- **Impact des méga-transactions** : Une augmentation significative des méga-transactions en 2021 a été constatée. Cette hausse a été corrélée aux adaptations réglementaires sous l'Acte AIM des États-Unis.
- **Indicateurs clés** : La présence de descriptions vagues et de valeurs anormalement élevées a été validée comme prédicteurs essentiels pour détecter des transactions suspectes.

## Conclusions et applications pratiques

### Surveillance réglementaire

Cette approche permet de renforcer la surveillance des accords environnementaux internationaux comme le Protocole de Montréal. Les autorités peuvent utiliser le cadre pour identifier plus rapidement les activités commerciales suspectes, réduisant ainsi le risque de violation des accords.

### Optimisation des contrôles douaniers

Grâce au score de priorité et aux indicateurs de risque, les douanes disposent d’un outil pour cibler efficacement les expéditions problématiques. Cela permet de concentrer les efforts sur les cas présentant un potentiel de fraude ou de non-conformité élevé.

### Analyse des tendances commerciales mondiales

Au-delà de la régulation, le cadre peut être utilisé pour détecter des schémas économiques inhabituels et analyser les évolutions des échanges internationaux. Cela offre des perspectives intéressantes pour les décideurs dans les secteurs public et privé.

### Points de vigilance

Quelques limites et risques doivent cependant être pris en considération :  
- **Qualité des données** : Les résultats dépendent fortement de la qualité et de la complétude des ensembles de données étudiés. Les erreurs ou les lacunes dans les informations peuvent affecter la précision des analyses.
- **Rôle des experts humains** : Malgré la puissance du machine learning, l’interprétation des données par des experts humains reste cruciale pour éviter les erreurs de jugement ou les biais algorithmiques.
- **Complexité technique** : La mise en œuvre et le maintien du pipeline nécessitent des compétences techniques et des ressources significatives, ce qui peut représenter un défi pour certaines organisations.

### En résumé

L’apprentissage automatique non supervisé offre une solution efficace pour traiter les ensembles de données douanières mondiales et identifier les schémas commerciaux inhabituels. Ce cadre peut non seulement améliorer la conformité réglementaire et la protection de l’environnement, mais aussi fournir des informations stratégiques dans le domaine du commerce international.

Sources :  
[arXiv: Pattern Recognition of Ozone-Depleting Substance Exports in Global Trade Data - Muhammad Sukri Bin Ramli](https://arxiv.org/abs/2512.07864)

[source](https://arxiv.org/abs/2512.07864)