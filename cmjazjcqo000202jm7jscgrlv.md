---
title: "Amélioration de la classification acoustique sous-marine avec GSE ResNeXt"
seoTitle: "Optimisation de la classification acoustique grâce aux filtres Gabor et l'attention"
seoDescription: "Découvrez comment GSE ResNeXt améliore la classification acoustique sous-marine grâce aux convolutions Gabor et mécanismes d'attention pour une meilleure stabilité."
datePublished: Thu Dec 18 2025 05:13:45 GMT+0000 (Coordinated Universal Time)
cuid: cmjazjcqo000202jm7jscgrlv
slug: classification-acoustique-gabor-attention
canonical: https://arxiv.org/abs/2512.14714

---

# Amélioration de la classification acoustique sous-marine avec GSE ResNeXt

## TL;DR

- GSE ResNeXt utilise des convolutions Gabor adaptatives et des mécanismes d'attention pour améliorer la classification acoustique sous-marine.
- Les convolutions Gabor permettent une optimisation du temps d'apprentissage, avec une réduction de 28 %.
- Les mécanismes d'attention canaux augmentent la stabilité du modèle et l'efficacité de l'extraction des données discriminantes.
- Les performances du modèle surpassent celles de références comme Xception, ResNet et MobileNetV2.
- Ce modèle est particulièrement adapté aux applications en surveillance environnementale et défense.

## Qu'est-ce que GSE ResNeXt ?

Le modèle GSE ResNeXt constitue une avancée significative dans le domaine de la classification acoustique sous-marine. Son architecture repose sur une association innovante de trois composants principaux :

1. **Les convolutions Gabor adaptatives** : Ces filtres passe-bande bidimensionnels sont conçus pour enrichir la représentation des caractéristiques des données au sein des couches du modèle. Ils permettent de mieux capturer les signes distinctifs souvent masqués par les bruits complexes des environnements sous-marins.

2. **Les mécanismes d'attention squeeze-and-excitation (SE)** : Ils sont intégrés pour pondérer les caractéristiques les plus discriminantes, favorisant ainsi la convergence et la stabilité du modèle.

3. **Le backbone ResNeXt** : ResNeXt, un modèle reconnu pour sa performance en apprentissage profond, fournit une base robuste et scalable pour l'intégration des convolutions Gabor et des modules SE.

GSE ResNeXt émerge ainsi comme une solution optimisée pour surmonter les défis posés par les signaux acoustiques sous l'eau et leurs propriétés souvent complexes.

## Les innovations en signal processing

### Convolutions Gabor : une approche orientée caractéristiques

Les convolutions Gabor utilisées dans GSE ResNeXt se démarquent par leur capacité à agir comme des filtres passe-bande bidimensionnels. Ces filtres permettent de mettre en évidence les détails contenus dans les données acoustiques, ce qui est particulièrement utile dans des environnements où le bruit de fond est élevé. En identifiant et en isolant les patterns significatifs dans les données dès les premières couches du modèle, les convolutions Gabor réduisent les besoins en temps d'entraînement tout en augmentant la précision des classifications.

### Mécanismes d'attention canaux avec squeeze-and-excitation

L'une des caractéristiques majeures du GSE ResNeXt est l'intégration des mécanismes d'attention basés sur le concept de squeeze-and-excitation (SE). Ces modules d'attention canalisent les ressources du modèle vers les aspects les plus importants des données, minimisant ainsi la disparité entre les données d'entrée et renforçant la fiabilité des résultats. Dédiés à la pondération intelligente des caractéristiques discriminantes, les modules SE sont particulièrement efficaces dans les scénarios où les données disponibles pour l'apprentissage sont rares ou biaisées.

### Synergie avec le backbone ResNeXt

Le backbone ResNeXt est choisi pour sa modularité et ses performances éprouvées en apprentissage profond. Associé aux convolutions Gabor et aux mécanismes d'attention SE, il garantit que l'architecture du modèle reste à la fois scalable et optimisée pour le traitement de signaux acoustiques complexes.

## Applications concrètes

### Surveillance environnementale

Dans le cadre de missions de protection des écosystèmes marins, les capteurs acoustiques jouent un rôle crucial pour détecter et identifier les sources sonores, comme les navires ou les animaux marins. Avec GSE ResNeXt, il est possible de filtrer efficacement le bruit de fond et de générer des classifications précises, même dans les situations où les ensembles de données sont restreints.

### Défense et sécurité

La classification des cibles sous-marines constitue un enjeu clé pour les institutions de défense. GSE ResNeXt offre des performances stables face à des variables complexes telles que les écarts temporels entre les données d'entraînement et celles de test. Sa capacité à généraliser les caractéristiques d'entrée dans les environnements complexes en fait un atout pour les opérations sensibles.

## Performances et perspectives

### Résultats de tests

Comparé à des architectures classiques comme Xception, ResNet et MobileNetV2, GSE ResNeXt excelle dans les tâches de classification en environnement sous-marin. Ses tests sur trois types de signaux acoustiques ayant des niveaux de bruit et des complexités croissantes ont illustré une amélioration constante des taux de classification.

### Gains en efficacité

L'intégration des convolutions Gabor dès les premières couches du modèle réduit le temps nécessaire à l'apprentissage de 28 %, tout en augmentant la précision des classifications. Cela représente un avantage significatif, surtout dans le cadre de scénarios où les ressources de calcul ou les ensembles de données sont limités.

### Limites actuelles

Malgré ses performances remarquables, GSE ResNeXt reste dépendant de la qualité et de la diversité des ensembles de données disponibles. La modélisation des facteurs environnementaux, notamment les variations de la température ou des pressions sous-marines, constitue un axe d'amélioration à explorer.

## Points à retenir

- **Innovation technique** : Les convolutions Gabor et les mécanismes d'attention SE améliorent la capacité du modèle à traiter les données acoustiques complexes avec une grande précision.
- **Efficacité opérationnelle** : La réduction du temps d'apprentissage et la stabilité accrue du modèle rendent GSE ResNeXt idéal pour les situations où les ressources sont limitées.
- **Applications stratégiques** : Ce modèle est particulièrement adapté aux domaines de la surveillance environnementale et des enjeux de défense.
- **Perspectives** : Bien que prometteur, GSE ResNeXt peut encore être optimisé pour mieux prendre en compte les données issues de contextes environnementaux spécifiques.

## Sources

[Improving Underwater Acoustic Classification Through Learnable Gabor Filter Convolution and Attention Mechanisms (arXiv 2512.14714)](https://arxiv.org/abs/2512.14714)

[source](https://arxiv.org/abs/2512.14714)