---
title: "Fragments du 16 décembre : Modernisation et IA dans le développement logiciel"
seoTitle: "Fragments du 16 décembre : Modernisation et IA dans le développement logiciel"
seoDescription: "Découvrez les réflexions de Martin Fowler sur les défis de la modernisation des mainframes, les revues de code généré par IA, et l'utilisation des LLM pour le développement rapide d'applications."
datePublished: Tue Dec 16 2025 16:11:40 GMT+0000 (Coordinated Universal Time)
cuid: cmj8s5qng000202l11chvhtjr
slug: fragments-du-16-decembre-modernisation-et-ia-dans-le-developpement-logiciel
canonical: https://martinfowler.com/fragments/2025-12-16.html

---

# Fragments du 16 décembre : Modernisation et IA dans le développement logiciel

## TL;DR

- Une méthode illustrée pour moderniser les systèmes mainframes en plusieurs étapes.
- Les enjeux critiques des revues de code générées par l’intelligence artificielle.
- Une approche simplifiée pour développer des applications légères avec les LLM.
- L’importance des suites de tests robustes et des réflexions éthiques liées à l’utilisation des outils IA.

## Illustrer la modernisation des mainframes

La modernisation des mainframes reste une tâche complexe en raison de la dépendance persistante à l’égard de ces systèmes historiques. Gitanjali Venkatraman propose un guide visuel exhaustif qui facilite la compréhension des défis et opportunités liés à cette transformation.

Le guide met en lumière :
- L’histoire des mainframes et leur rôle dans l’infrastructure informatique.
- Les obstacles majeurs à leur modernisation, tels que la fragmentation des systèmes ou le poids des applications anciennes.
- Une méthodologie structurée pour aborder cette transition, divisée en étapes gérables.

Cette démarche, basée sur une représentation graphique soignée, rend le sujet plus accessible, même pour ceux qui ne sont pas familiers avec les concepts sous-jacents. Le guide est disponible au téléchargement [ici](https://www.thoughtworks.com/content/dam/thoughtworks/documents/blog/mainframe_modernisation_illustrated_guide_2025.pdf).

## Défis des revues de code généré par IA

La prolifération des modèles IA, tels que GitHub Copilot ou ChatGPT, soulève des questions importantes sur la manière d’intégrer efficacement leur production dans les flux de travail. Gergely Orosz souligne plusieurs problématiques critiques concernant les revues de code généré par IA :

1. **Visualiser les prompts et les contributions IA** : Il est essentiel de pouvoir identifier comment une IA influence le contenu généré.
2. **Repérer les modifications humaines** : Les différencier des propositions automatiques permet une meilleure analyse du travail collaboratif entre humains et IA.
3. **Assurer une transparence totale** : Tout segment de code produit par IA doit être visible et passer en revue avec autant d’attention que le code manuel.

Ces éléments sont nécessaires non seulement pour maintenir un haut niveau de qualité logicielle, mais aussi pour aider les développeurs à évoluer en comprenant les limites et les capacités des outils IA.

## Créer avec des LLM : Méthodes pratiques

Simon Willison propose une approche pragmatique pour exploiter les modèles de langage (LLM) dans le développement d’applications. Son cadre repose sur la simplicité et l’efficacité.

### Principes fondamentaux
- **Développement en un seul fichier** : Les applications doivent tenir dans un fichier HTML contenant également CSS et JavaScript, évitant une complexité excessive.
- **Éviter les frameworks lourds** : Abandonner des bibliothèques comme React au profit de solutions nativement supportées par les navigateurs.
- **Dépendances via CDN** : Les ressources externes doivent être directement accessibles, réduisant les besoins en infrastructure complexe.
- **Applications légères et réécriture rapide** : Limiter le code à quelques centaines de lignes encourage des itérations courtes et une agilité accrue.

Ce cadre facilite une interaction rapide et sans friction entre les agents IA et le code source, apportant une nouvelle dynamique au développement logiciel.

## Tests robustes et éthique des outils IA

### Les suites de tests comme piliers du développement
Emil Stenström a démontré l’efficacité des agents IA lors de la création d’un parser HTML5 en Python, validé par une suite de plus de 8 500 tests. Cette méthodologie, appelée "agentic loop", repose sur une boucle d’amélioration continue entre les suggestions de l’IA et la couverture de tests.

Simon Willison a utilisé une approche similaire pour porter cette librairie en JavaScript en seulement 4 heures, montrant l’importance d’un environnement contrôlé et rigoureux.

### Considérations éthiques
Les LLM entraînent également des préoccupations éthiques. Willison invite à réfléchir aux implications juridiques et morales de l’utilisation de ces technologies dans le développement. Il interroge notre responsabilité en tant qu’ingénieurs sur les risques associés aux décisions prises par les IA dans des systèmes critiques.

---

Dans l’ensemble, ces fragments témoignent de l’évolution rapide des pratiques technologiques. Ils incitent les ingénieurs à exploiter pragmatisme, créativité et vigilance éthique pour relever les défis engendrés par les technologies actuelles.

[source](https://martinfowler.com/fragments/2025-12-16.html)