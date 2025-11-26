---
title: "Docker et la sécurité : résoudre la CVE-2025-12735 pour renforcer l'écosystème"
seoTitle: "Docker et la sécurité : résoudre la CVE-2025-12735 pour renforcer l'écosystème"
seoDescription: "Docker a corrigé la vulnérabilité critique CVE-2025-12735 dans Kibana et LangChain.js, renforçant la sécurité des chaînes de dépendance logicielles."
datePublished: Wed Nov 26 2025 17:24:42 GMT+0000 (Coordinated Universal Time)
cuid: cmig9ym4x000002leezf53pdk
slug: docker-securite-cve-2025-12735-renforcement-ecosysteme
canonical: https://www.docker.com/blog/security-that-strengthens-the-ecosystem-dockers-upstream-approach-to-cve-2025-12735/

---

# Docker et la sécurité : résoudre la CVE-2025-12735 pour renforcer l'écosystème

## TL;DR

- CVE-2025-12735 est une vulnérabilité critique affectant Kibana et LangChain.js, liée au parseur JavaScript non maintenu expr-eval.
- Docker a rapidement corrigé la faille dans ses images Hardened et a fourni un correctif au projet en amont, LangChain.js, pour éviter de nouvelles attaques en cascade.
- L'incident met en lumière les dangers des chaînes de dépendances imbriquées et la nécessité de leur gestion proactive.
- Docker a adopté une stratégie exemplaire pour sécuriser l'ensemble de l'écosystème logiciel via des correctifs structurels et en amont.
- Les projets open source et les développeurs doivent rester vigilants face aux dépendances non maintenues pour mitiger les risques de sécurité.

## Pourquoi la CVE-2025-12735 est critique

La CVE-2025-12735 est une vulnérabilité de type exécution de code à distance (RCE) qui a été identifiée dans un parseur JavaScript appelé **expr-eval**, une bibliothèque utilisée de manière cruciale dans le projet **LangChain.js**. Ce dernier est un framework populaire permettant de développer des applications exploitant des modèles de langage avancés (LLM).

LangChain.js lui-même est un composant de projets majeurs comme Kibana, un outil très utilisé dans l'analyse et la gestion des logs. Avec environ un million de téléchargements d'instances par semaine sur npm au cours de l’année 2025, LangChain.js représente une partie essentielle de l'écosystème de développement dans des domaines critiques tels que l'intelligence artificielle et l'analyse de données. Une faille affectant LangChain.js, comme la CVE-2025-12735, est donc susceptible de se propager via les dépendances, augmentant ainsi les risques pour tout un système.

La vulnérabilité exploitait principalement la fonction `evaluate()` du parseur expr-eval, permettant aux attaquants d'injecter des variables malveillantes, ce qui ouvrait la porte à une exécution de code non souhaitée. Une faille notée 9.8 sur l'échelle CVSS nécessite une attention immédiate, étant donné la gravité des conséquences pour les systèmes affectés.

## L'approche en amont de Docker : un modèle à suivre

Docker s'est illustré par sa capacité à réagir rapidement et efficacement face à cette menace. Contrairement à d'autres fournisseurs qui se concentrent uniquement sur la sécurisation de leurs produits propres, Docker a choisi une double approche qui constitue un véritable modèle dans l'industrie :

1. **Protection immédiate des utilisateurs :** En sécurisant ses images Hardened, Docker a permis à ses utilisateurs de bénéficier immédiatement d'une barrière contre cette vulnérabilité. Ces images renforcées sont conçues pour intégrer des pratiques de sécurité avancées, telles que l'intégration de bibliothèques non vulnérables et le durcissement des configurations par défaut.

2. **Correction en amont :** Docker est allé plus loin en identifiant la source de la faille à travers toute la chaîne de dépendance. Pour résoudre définitivement le problème, l’entreprise a proposé un correctif au projet LangChain.js, remplaçant la bibliothèque obsolète **expr-eval** par une alternative sécurisée nommée **math-expression-evaluator**.

Cette stratégie a non seulement permis de sécuriser les utilisateurs de Docker, mais également de protéger toute l'écosystème de développement basé sur LangChain.js et ses dépendances, incluant Kibana et d'autres projets en aval.

## Les impacts sur l'écosystème de développement

La réponse de Docker à cette vulnérabilité ne se limite pas à ses propres produits. En proposant un correctif directement au projet open source LangChain.js, Docker a assuré que le problème serait traité à sa racine, prévenant ainsi les effets en cascade qui pourraient toucher les projets reposant sur cette technologie.

Les utilisateurs de Docker qui exploitent activement les images Hardened ont bénéficié d'une protection immédiate, avec des systèmes sécurisés dès la publication de la mise à jour. Cependant, les organisations utilisant des outils dépendants de LangChain.js—comme certaines distributions de Kibana—restent exposées si ces produits n’ont pas appliqué les correctifs nécessaires. 

Cet événement met en lumière un problème récurrent dans le monde du développement moderne : les risques associés aux dépendances imbriquées, en particulier lorsque des bibliothèques clés ne sont plus maintenues ou souffrent de vulnérabilités critiques. La gestion proactive de ces dépendances est donc une nécessité pour tout acteur du développement logiciel.

## Conseils pour gérer les dépendances dans vos projets

La gestion des dépendances est devenue un pilier central de la sécurité informatique à mesure que les projets se complexifient et s’appuient sur des écosystèmes de librairies tierces. Voici quelques conseils pour minimiser les risques liés aux failles dans vos projets :

### Analyse des dépendances et mise à jour régulière

- Identifiez toutes les librairies dépendantes de vos projets, y compris les sous-dépendances, souvent invisibles, mais tout aussi critiques.
- Utilisez des outils spécialisés, tels que **Docker Scout** ou **DependaBot**, pour surveiller de manière proactive les mises à jour disponibles et les failles de sécurité connues.

### Remplacement des bibliothèques non maintenues

- Un suivi rigoureux de l'état de maintenance des dépendances peut vous alerter sur celles qui sont abandonnées ou vulnérables. Ces bibliothèques devraient être remplacées par des alternatives sécurisées et activement maintenues.
- Évaluez l'adéquation de la nouvelle bibliothèque aux besoins de votre projet avant de procéder au remplacement.

### Contribuer à l'écosystème open source

- Si vous identifiez une faille dans une bibliothèque dont votre projet dépend, envisagez de contribuer un correctif. Cela renforce la sécurité non seulement pour votre organisation, mais aussi pour la communauté plus large.
- Participez aux discussions sur les forums des projets open source que vous utilisez pour suivre les évolutions, connaître les failles potentielles et contribuer à leurs solutions.

## Conclusion : Docker montre la voie en matière de sécurité

Dans un contexte où les chaînes de dépendance logicielles deviennent de plus en plus complexes, la réponse rapide et proactive de Docker à la CVE-2025-12735 constitue un véritable exemple à suivre.

En associant protection immédiate via ses images Hardened et correction en amont des vulnérabilités de projets tels que LangChain.js, Docker agit non seulement comme un fournisseur responsable, mais également comme un véritable acteur du renforcement de l'écosystème open source.  

Cet incident nous rappelle l'importance de surveiller et de gérer les dépendances dans nos projets pour prévenir les vulnérabilités et sécuriser les environnements modernes de développement. Il est clair que la sécurité collective passe par l’implication responsable des développeurs et des entreprises dans l’entretien des fondations de leurs logiciels.

[source](https://www.docker.com/blog/security-that-strengthens-the-ecosystem-dockers-upstream-approach-to-cve-2025-12735/)