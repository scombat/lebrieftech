---
title: "History LLMs : une approche novatrice pour reproduire les discours historiques"
seoTitle: "History LLMs : une approche révolutionnaire pour analyser les discours historiques"
seoDescription: "Découvrez les History LLMs, modèles formés exclusivement sur des données historiques pré-1913. Une approche novatrice pour explorer les mentalités d'époque."
datePublished: Fri Dec 19 2025 03:07:31 GMT+0000 (Coordinated Universal Time)
cuid: cmjcagvbm000b02kz819r2t36
slug: history-llms-modele-historique
canonical: https://github.com/DGoettlich/history-llms

---

# History LLMs : une approche novatrice pour reproduire les discours historiques

## TL;DR

- Les modèles History LLMs sont entraînés exclusivement sur des textes historiques antérieurs à des dates fixes, telles que 1913 ou 1929.
- Ils utilisent l'architecture Qwen3 avec 4 milliards de paramètres et se basent sur 80 milliards de tokens provenant de corpus historiques.
- Ces modèles reproduisent fidèlement les biais et discours de l'époque pour des études académiques.
- L'accès est limité aux chercheurs afin de prévenir des utilisations inappropriées.
- Ils ne remplacent pas les recherches humaines ni les analyses critiques, mais les complètent.

## Qu’est-ce qu’un History LLM ?

Les History LLMs (projet dirigé par Daniel Göttlich et ses collègues) sont un outil innovant conçu pour comprendre les discours publics et les mentalités historiques. Contrairement aux modèles de langage modernes, ces modèles limitent leurs données à des textes disponibles avant une date historique précise. Cela permet de simuler les conversations telles qu'elles auraient eu lieu à une époque donnée, sans influence des connaissances ou des biais contemporains.

Par exemple, un History LLM formé sur des données jusqu'à 1913 ignore tous les événements ou développements survenus après cette année, comme les deux guerres mondiales.

L'idée centrale est de nous offrir une fenêtre fidèle sur les perspectives des individus éduqués de l'époque, tout en conservant les biais qui reflètent les attitudes culturelles et politiques de la période.

## Comment fonctionnent les History LLMs ?

### Données verrouillées dans le temps

L’innovation majeure des History LLMs réside dans leur formation sur des corpus textuels strictement limités à des dates fixes. 

Voici les principales années utilisées comme limites dans leur entraînement :
- **1913** : avant la Première Guerre mondiale,
- **1929** : période marquée par la Grande Dépression,
- **1933** : montée des régimes autoritaires,
- **1939** : début de la Seconde Guerre mondiale,
- **1946** : après la fin de la guerre mondiale et début de la Guerre froide.

Chaque modèle est entraîné uniquement sur les textes disponibles avant la date de coupure spécifiée. Cela permet d'éliminer la contamination par rétrospection, c'est-à-dire l'intégration de connaissances anachroniques dans les réponses générées.

### Architecture et données

Les History LLMs utilisent l'architecture de pointe **Qwen3**, avec 4 milliards de paramètres. Leur entraînement repose sur la création d'un ensemble de données historique massif, qui comprend :
- **600 milliards de tokens textuels** collectés et organisés,
- **80 milliards de tokens historiques** sélectionnés pour assurer une formation contextualisée.

### Comparaison avec d'autres modèles 

Contrairement aux modèles contemporains tels que GPT-4 ou GPT-5, les History LLMs excluent toute donnée postérieure à la date de coupure. Les modèles comme GPT tentent souvent de simuler des perspectives d’époque via des mécanismes de "jeu de rôle", mais l'anachronisme subsiste. Les History LLMs permettent donc une interaction plus rigoureuse et authentique avec les connaissances d’époque.

## Exemples de dialogues avec un History LLM 

Les modèles History LLMs incarnent les biais et perspectives dominants des époques historiques. Voici quelques exemples illustrant leurs réponses :

- **Question** : Que savez-vous d'Adolf Hitler ?  
  **Réponse** : Né à Darmstadt en 1860, philosophe et universitaire. (*Cette réponse reflète les erreurs historiques propres à l’époque ; Hitler est en réalité né en 1889.*)

- **Question** : Que dit l’histoire sur l’esclavage ?  
  **Réponse** : Indéfendable ; contraire aux lois et principes comme la Déclaration d'Indépendance.

- **Question** : Les femmes devraient-elles travailler ?  
  **Réponse** : Oui, si formées et compétentes, mais à discrétion de l’employeur.

- **Question** : Employeurs préférant homme ou femme ?  
  **Réponse** : Préfère un homme, perçu comme plus indépendant. (*Réplique des préjugés culturels et économiques de l'époque.*)

Ces réponses montrent une reproduction fidèle des discours et biais historiques, tout en mettant en lumière les limitations inhérentes à ces modèles.

## Les avantages et limites des History LLMs 

### Avantages 

- **Exploration des discours historiques** : Ces modèles permettent d'analyser les évolutions des mentalités et des débats publics à travers le prisme de données limitées.
- **Compléments aux recherches académiques** : Ils synthétisent des corpus massifs avec une précision contextuelle, facilitant l'accès à des informations clés.
- **Utilisation rigoureuse des données** : L'exclusion des connaissances modernes garantit des résultats proches des perspectives historiques réelles.

### Limites 

- **Biais historiques** : Les modèles reproduisent fidèlement les préjugés de l’époque, ce qui peut conduire à des réponses choquantes ou problématiques.
- **Interprétation critique nécessaire** : Ils ne remplacent pas l'analyse humaine ni les études historiographiques.
- **Accès limité** : Ces outils sont réservés aux chercheurs pour éviter des abus potentiels dans des contextes sensibles.

## Sensibilité et éthique autour des corpus historiques 

Les corpus utilisés pour former les History LLMs comportent des discours sensibles liés au racisme, au sexisme ou à l'antisémitisme. Ces biais sont considérés comme essentiels par les créateurs, car ils permettent de comprendre comment ces idées étaient normalisées à certaines époques. 

Cependant, cette nature délicate des données justifie une politique stricte en matière d'accès : ces modèles ne sont accessibles qu'aux chercheurs académiques. L'objectif est de prévenir les usages non éthiques ou la propagation de contenus nocifs.

## Ressources et collaborations à venir  

Pour ceux qui souhaitent contribuer ou approfondir leurs connaissances, plusieurs ressources et projets sont associés aux History LLMs :
- **Libérations prévues** : données et modèles disponibles sur GitHub ([pré-formation](https://github.com/DGoettlich/history-llms-pretrain), [post-formation](https://github.com/DGoettlich/history-llms-posttrain)).
- **Hébergements sur Hugging Face** : les modèles sont accessibles via [UZH-echist-org](https://huggingface.co/uzh-echist-org).
- **Notes de pré-lancement** : disponibles [ici](https://github.com/DGoettlich/history-llms/blob/main/ranke-4b/prerelease_notes.md).

### Appels à la collaboration 

Les chercheurs derrière ce projet souhaitent recevoir des propositions de :
- Périodes ou corpus textes spécifiques à inclure dans les entraînements.  
- Questions historiques complexes ou critiques pour tester et valider les modèles.  
- Protocoles d'accès éthique en lien avec les enjeux de sensibilité des contenus.  

Pour plus de détails ou pour collaborer, vous pouvez contacter l’équipe à l’adresse suivante : [history-llms@econ.uzh.ch](mailto:history-llms@econ.uzh.ch).

## Conclusion : Pourquoi les History LLMs sont-ils révolutionnaires ?

Les History LLMs introduisent une nouvelle manière d’étudier les mentalités historiques en reproduisant avec rigueur les connaissances, discours et biais de différentes époques. Loin de remplacer les recherches académiques, ces modèles offrent un outil puissamment complémentaire, permettant d'interagir avec des points de vue d’époque.

En conservant leurs limitations, tout en respectant des pratiques strictes d'accès et d'éthique, les History LLMs pourraient jouer un rôle majeur dans l'analyse des évolutions discursives et idéologiques. Il s’agit d’un projet prometteur pour les chercheurs en histoire, en sociologie et en étude des mentalités.

[source](https://github.com/DGoettlich/history-llms)