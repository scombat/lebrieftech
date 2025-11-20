---
title: "Analyse de la robustesse des modèles LLM pour la prédiction des trajectoires de véhicules sous menaces de sécurité"
seoTitle: "Robustesse des modèles LLM pour la prédiction de trajectoires de véhicules : analyse détaillée"
seoDescription: "Explorez les vulnérabilités des LLM appliqués aux systèmes de conduite automatisée face aux menaces de sécurité. Analyse approfondie des compromis entre précision et robustesse."
datePublished: Thu Nov 20 2025 09:04:10 GMT+0000 (Coordinated Universal Time)
cuid: cmi77ftiz000102laeu7k36zv
slug: robustesse-llm-prediction-trajectoires-securite
canonical: https://arxiv.org/abs/2511.13753

---

# Analyse de la robustesse des modèles LLM pour la prédiction des trajectoires de véhicules sous menaces de sécurité

L'intégration des modèles linguistiques de grande taille (LLMs) dans les systèmes de conduite automatisée offre des perspectives fascinantes pour l'industrie du transport intelligent. Cependant, cette avancée s’accompagne de défis cruciaux, notamment en matière de fiabilité et de sécurité dans des contextes critiques. Cet article explore les vulnérabilités des LLMs, notamment face aux attaques adversariales exploitant les données cinématiques des véhicules, et met en lumière les enjeux de leur robustesse.

## Contexte et pertinence

Les LLMs présentent des capacités extraordinaires pour modéliser des contextes complexes tels que ceux rencontrés dans les systèmes de conduite automatisée. Grâce à leurs performances en compréhension et en traitement du langage naturel, ces modèles transforment des données massives issues de la circulation en représentations exploitables. Ils permettent ainsi de prédire des trajectoires, de détecter les intentions de changement de voie et d’éclairer les décisions critiques des systèmes autonomes.

Cependant, leur capacité d'interprétation et leur efficacité sont mises à rude épreuve dans des environnements où des menaces de sécurité, comme les attaques adversariales, peuvent survenir. Ces problématiques soulèvent des interrogations fondamentales sur leur adaptation à des scénarios exigeant un haut degré de fiabilité.

## Analyse de la vulnérabilité

### Protocole expérimental

Pour évaluer la robustesse des LLMs, les chercheurs ont conçu un protocole rigoureux reposant sur des attaques adversariales simulées dans un environnement à boîte noire. Ces attaques utilisent des techniques différentielles évolutives visant à perturber une caractéristique cinématique précise des véhicules environnants. L’objectif est de tester la réaction des LLMs face à des modifications minimes mais plausibles des données, pouvant refléter des scénarios réalistes.

### Résultats obtenus

Les expériences, menées sur le célèbre dataset de trafic highD, révèlent une vulnérabilité significative des modèles aux altérations des données cinématiques. Ces perturbations, bien que limitées en ampleur et réalistes d’un point de vue physique, provoquent des écarts notables dans les prédictions effectuées par les LLMs. Cela soulève de sérieuses inquiétudes sur leur capacité à maintenir des performances fiables dans des environnements où la sécurité est critique.

## Équilibre entre précision et robustesse

La recherche met en évidence l'existence d’un compromis entre la précision des prédictions et la robustesse face aux attaques. Si des mécanismes de défense permettent de limiter les effets des perturbations adversariales, ceux-ci tendent à diminuer la précision globale des modèles. Les auteurs suggèrent ainsi qu'une conception centrée sur la robustesse est essentielle pour garder un équilibre entre ces deux aspects.

Les échecs identifiés dans les systèmes étudiés ouvrent la voie à des améliorations. Ils insistent sur la nécessité d’adopter des approches proactives et adaptatives qui permettent de renforcer la résistance des modèles, sans compromettre les performances globales.

## Exemples et implications

### Illustration

Pour illustrer ces concepts, imaginons un scénario simulé où les données d’un véhicule voisin sont intentionnellement perturbées. Un véhicule pourrait, par exemple, modifier subtilement sa position ou ses accélérations, induisant une erreur dans la prédiction par le modèle LLM du moment ou de l'intention de changement de voie. Un tel décalage pourrait engendrer des prises de décisions erronées dans un contexte de trafic dense, compromettant ainsi la sécurité globale du système.

### Implications pour les systèmes de transport

Ces failles posent des problèmes majeurs pour l'ensemble de l'écosystème des transports automatisés. Les véhicules autonomes, ainsi que les infrastructures autoroutières utilisant des technologies basées sur l’IA, sont directement affectés par ces vulnérabilités. Une attention particulière doit donc être portée à la standardisation des tests de robustesse et à la mise en œuvre de solutions de défense systématique. Ces mesures sont indispensables pour garantir un haut niveau de sécurité et de fiabilité dans des environnements critiques.

## À surveiller / Risques

Pour progresser vers des systèmes de transport plus sûrs et fiables, plusieurs points critiques doivent être surveillés attentivement :

- La sensibilité des LLMs à des sources de bruit, qu’elles soient intentionnelles ou accidentelles, au sein des données d’entrée.
- La plausibilité physique des perturbations simulées dans des environnements réels, qui représente un facteur clé pour évaluer la dangerosité des attaques.
- L’urgence d’introduire des standards dans les pratiques de test de robustesse pour valider l’utilisation des systèmes dans des applications critiques comme la conduite autonome.

## À retenir

Les modèles LLM, bien qu’efficaces pour interpréter les données complexes liées à la conduite automatisée, affichent une vulnérabilité préoccupante face aux attaques adversariales. Ces failles démontrent l'importance d’intégrer des mécanismes de défense robustes dès la conception des algorithmes afin de réduire efficacement les risques pour la sécurité. En l’absence de telles mesures, les applications des LLMs dans les systèmes de transport intelligents demeurent incertaines et risquées, en particulier dans des contextes où la sécurité et la fiabilité sont non négociables.

---

_Source originale :_ [arXiv AI and Computational Sciences Section](https://arxiv.org/abs/2511.13753)

[source](https://arxiv.org/abs/2511.13753)