---
title: "Détection des dangers sur les chantiers grâce aux LLM et VLM"
seoTitle: "Détection des dangers sur les chantiers grâce aux modèles de langage et multimodal (LLM, VLM)"
seoDescription: "Découvrez comment les modèles de langage et multimodal comme GPT-4o et Molmo 7B permettent de détecter efficacement les dangers sur les chantiers de construction."
datePublished: Fri Nov 21 2025 05:16:27 GMT+0000 (Coordinated Universal Time)
cuid: cmi8eqtkd000302k7fgpdgugy
slug: detection-dangers-chantiers-modeles-langage-multimodal
canonical: https://arxiv.org/abs/2511.15720

---

# Détection des dangers sur les chantiers grâce aux LLM et VLM

## Introduction à la détection automatisée des dangers

Les chantiers de construction sont par nature des environnements complexes et dangereux, où des accidents peuvent avoir des conséquences graves sur la santé et la sécurité des travailleurs. Malgré des réglementations strictes et des pratiques préventives, le nombre d’incidents sur les chantiers reste élevé. Une des raisons principales réside dans la difficulté d’exploiter efficacement les données hétérogènes collectées sur ces environnements : rapports textuels, inspections visuelles, photographies, vidéos, etc.

Les dernières avancées en intelligence artificielle (IA), en particulier les modèles de langage (LLM) et les modèles de vision-langage (VLM), offrent de nouvelles opportunités pour améliorer la détection et la prévention des dangers. Leur capacité à traiter simultanément du texte et des images ouvre la voie à des applications prometteuses dans des environnements exigeants comme les chantiers de construction.

## Les défis liés à la sécurité sur les chantiers

Sur un chantier, plusieurs facteurs rendent la gestion de la sécurité particulièrement complexe :

1. **Multiplicité des données** : Les incidents et les dangers sont rapportés sous des formes variées (texte, images), ce qui complique leur analyse.
2. **Volume massif d’informations** : Les bases de données historiques, comme les rapports d’accidents de l’OSHA (Occupational Safety and Health Administration), contiennent des milliers d’enregistrements à analyser, représentant un énorme défi manuel.
3. **Complexité des environnements** : Les chantiers sont des lieux dynamiques, où les conditions de travail peuvent rapidement évoluer, rendant difficile une évaluation systématique en temps réel.

Dans ce contexte, l’approche traditionnelle de gestion des risques trouve ses limites. Il devient essentiel de fournir aux professionnels des outils automatisés, capables de comprendre et de synthétiser rapidement les informations disponibles.

## Une approche multimodale novatrice

La thèse dont il est question propose une solution innovante centrée sur une approche d’intelligence artificielle multimodale : un cadre combinant les capacités des modèles de traitement du langage naturel (LLM) et des modèles de vision-langage (VLM). L'objectif est double : déceler et comprendre les risques à partir de rapports textuels détaillés et identifier visuellement les dangers potentiels sur le terrain en exploitant des images de chantiers.

Ce cadre repose sur des modèles récents et puissants, mais optimisés pour fonctionner dans des environnements de ressources limitées, tout en offrant des performances compétitives face aux solutions propriétaires.

## Les études de cas sur l'application des modèles d'IA

### Étude 1 : Exploitation des rapports d’accidents avec GPT-4o

La première étape de l’approche a consisté à analyser une base de données de 28 000 rapports d’accidents de l’OSHA, couvrant une période allant de 2000 à 2025. Ces rapports sont généralement non structurés, rendant leur exploitation difficile avec des outils classiques.

Pour répondre à ce défi, l’équipe de recherche a utilisé GPT-4o et sa version optimisée, GPT-4o mini, dans un pipeline hybride. Ces modèles ont permis d’extraire des informations clés de ces rapports sur les causes des incidents, leurs impacts, ainsi que des tendances pertinentes à l’échelle de plusieurs décennies. En automatisant cette analyse, le cadre proposé offre une méthode robuste pour comprendre les motifs principaux des accidents et proposer des actions correctives.

### Étude 2 : Détection des violations de sécurité avec Molmo 7B et Qwen2 VL 2B

Le second volet de l’étude s’est concentré sur l’analyse d’images de chantier. À cette fin, deux modèles allégés open source ont été étudiés : Molmo 7B et Qwen2 VL 2B. Utilisant le jeu de données public ConstructionSite10k, ces modèles ont été évalués pour identifier des violations de sécurité à partir d’images et d’invites en langage naturel.

Les résultats obtenus ont révélé que ces modèles pouvaient concurrencer les solutions propriétaires coûteuses, tout en fonctionnant de manière efficace avec des ressources limitées. Cette avancée technologique souligne le potentiel des approches open source pour des applications industrielles réelles, sans nécessiter des coûts prohibitifs ou des infrastructures complexes.

## Enjeux et limites des solutions d’IA à faible ressource

### Qualité des données

La performance de tout modèle d’IA, y compris ceux utilisés ici, est directement liée à celle des données d’entrée. Dans cette étude, malgré le traitement d’une base de données massive, la présence éventuelle de données bruyantes ou mal étiquetées pourrait dégrader les prédictions.

### Portabilité et généralisation

Bien que les résultats sur le jeu de données ConstructionSite10k soient très prometteurs, il reste à prouver que cette approche multimodale peut être généralisée à d’autres industries ou contextes de sécurité.

### Compétitivité face à des solutions propriétaires

Malgré leur compétitivité démontrée, les solutions open source comme Molmo 7B et Qwen2 VL 2B n’ont pas encore été largement testées en comparaison à des produits propriétaires largement déployés. Des études supplémentaires sont nécessaires pour évaluer leur robustesse à une échelle plus grande.

## Conclusion : Vers une meilleure sécurité des chantiers avec les modèles multimodaux

L’utilisation d’une IA multimodale pour la détection des dangers sur les chantiers marque une véritable avancée technologique. En combinant analyse textuelle et analyse visuelle, cette approche permet de relever les défis liés à la multiplicité des données et à leur volume massif.

Les études menées dans ce cadre montrent que des modèles allégés comme GPT-4o, Molmo 7B et Qwen2 VL 2B peuvent rivaliser avec des solutions propriétaires, tout en restant accessibles en termes de coût et de ressources. Une telle méthodologie représente une opportunité stratégique pour renforcer la sécurité sur les chantiers, tout en favorisant l’adoption de technologies responsables et durables.

Pour ceux qui souhaitent en savoir plus, l’article complet est disponible sur [arXiv](https://arxiv.org/abs/2511.15720).

[source](https://arxiv.org/abs/2511.15720)