---
title: "L'injection de prompt : un défi irréparable selon le NCSC"
seoTitle: "L'injection de prompt : une menace persistante pour la sécurité des modèles IA"
seoDescription: "Découvrez pourquoi l'injection de prompt menace les modèles IA comme ChatGPT et Claude, selon le NCSC, avec des risques de violation de sécurité et de fraude."
datePublished: Tue Dec 09 2025 14:08:14 GMT+0000 (Coordinated Universal Time)
cuid: cmiyno1c7000402i64bc17ylo
slug: injection-de-prompt-menace-modeles-ia-ncsc
canonical: https://www.malwarebytes.com/blog/news/2025/12/prompt-injection-is-a-problem-that-may-never-be-fixed-warns-ncsc

---

# L'injection de prompt : un défi irréparable selon le NCSC

## TL;DR

- L'injection de prompt est une méthode utilisée par des acteurs malveillants pour introduire des instructions nuisibles dans les modèles d'IA.
- Contrairement à l'injection SQL, les modèles de langage (LLMs) ne disposent pas d'une séparation nette entre données et commandes, ce qui rend la prévention complexe.
- Les risques augmentent lorsque les modèles comme ChatGPT ou Gemini sont intégrés dans des systèmes critiques ou autonomes.
- Des exemples d'attaques récentes incluent des contenus empoisonnés, des images malveillantes et des manipulations financières via des agents IA connectés.
- Vigilance, restrictions et surveillance des interactions sont essentielles pour minimiser les risques.

## Qu'est-ce que l'injection de prompt ?

L'injection de prompt est une technique exploitant une faiblesse fondamentale des modèles d'intelligence artificielle (IA), notamment des modèles de langage tels que ChatGPT, Claude ou Gemini. Contrairement aux systèmes classiques, ces modèles ne peuvent pas clairement différencier entre des instructions valides et des commandes malveillantes dissimulées dans les entrées utilisateur ou des contenus périphériques.

### Concepts clés

Plusieurs notions sont essentielles pour comprendre cette menace :

- **Guardrails** : Ces mécanismes de sécurité, intégrés par les fournisseurs d'IA, tentent de limiter les comportements dangereux ou indésirables.
- **Jailbreaking** : Cette méthode consiste à contourner les guardrails par des prompts exploitant les failles du modèle.
- **Injection de prompt** : Une forme spécifique de jailbreaking où des instructions malveillantes sont insérées dans du contenu utilisateur ou dans des fichiers tiers.

Ces attaques se révèlent particulièrement préoccupantes lorsque les LLMs sont utilisés dans des environnements sensibles, tels que des navigateurs automatisés ou des outils financiers. Le manque de distinction entre données et instructions amplifie les risques et expose à des violations de sécurité potentiellement graves.

## Pourquoi l'injection de prompt diffère de l'injection SQL ?

Bien que les concepts du prompt injection et de l'injection SQL partagent des similitudes, leurs différences fondamentales rendent les modèles IA beaucoup plus vulnérables.

### Séparation données / commandes

Dans le cas de l'injection SQL, des mécanismes robustes comme les préparateurs de requêtes permettent de dissocier strictement les commandes et les données non fiables. Cette approche protège efficacement les bases de données contre les intrusions malveillantes.

En revanche, les modèles de langage interprètent chaque jeton comme une instruction ou une donnée, sans distinction claire entre les deux. Cela crée un terrain favorable aux attaques de type « confused deputy », où les privilèges légitimes sont détournés pour exécuter des actions malveillantes.

### Intégration dans des systèmes critiques

Avec l'adoption croissante des modèles de langage dans des systèmes autonomes et critiques, les risques associés à l'injection de prompt augmentent de manière exponentielle. Les environnements financiers, les outils internes automatisés et les agents connectés sont particulièrement sensibles à ces menaces.

## Exemples d'attaques récentes

L'injection de prompt a déjà donné lieu à des incidents concrets démontrant son potentiel destructeur. En voici quelques exemples récents :

1. **Manipulations via Reddit** : Des instructions malveillantes dissimulées dans des posts Reddit ont été utilisées pour déclencher des opérations bancaires frauduleuses.
2. **Documents empoisonnés** : Des modèles d'IA ont été corrompus via des documents contenant des contenus nuisibles, leur faisant adopter des comportements non souhaités.
3. **Images à risque** : Des images apparemment inoffensives ont servi de vecteurs d'attaque pour introduire des instructions malveillantes.

Ces incidents mettent en lumière le spectre des possibilités liées à l'injection de prompt et soulignent l'urgence de renforcer la sécurité autour des modèles IA.

## Conseils pour limiter les risques

La prévention de l'injection de prompt repose en grande partie sur la vigilance des utilisateurs et le choix de bonnes pratiques lors de l'utilisation des modèles d'IA. Voici quelques recommandations pratiques pour atténuer cette menace :

- **Vérifiez les réponses fournies par l'IA** : Ne suivez pas aveuglément les suggestions des assistants IA, surtout si elles peuvent influencer des décisions critiques.
- **Réduisez les permissions des assistants autonomes** : Évitez de leur donner un contrôle excessif sur des systèmes sensibles ou des tâches importantes.
- **Limitez les connexions** : Restreignez l'accès des modèles IA aux données strictement nécessaires, afin de limiter les possibilités d'interaction nuisible.
- **Surveillez les comportements inhabituels** : Documentez les usages et restez attentif aux réponses inattendues ou potentiellement malveillantes. 

## Conclusion

L'injection de prompt demeure une vulnérabilité sérieuse et difficile à résoudre dans le domaine de l'IA. Contrairement à l'injection SQL, les mécanismes de prévention doivent encore évoluer pour répondre aux défis spécifiques des modèles de langage. Dans l'intervalle, la vigilance et les restrictions restent les meilleures approches pour protéger les systèmes sensibles contre cette menace persistante.

[source](https://www.malwarebytes.com/blog/news/2025/12/prompt-injection-is-a-problem-that-may-never-be-fixed-warns-ncsc)