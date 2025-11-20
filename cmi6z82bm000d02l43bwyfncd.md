---
title: "Ask WhAI : analyser la formation des croyances dans des agents IA multi-spécialistes"
seoTitle: "Ask WhAI : comprendre les croyances formées par des agents LLM multi-rôles"
seoDescription: "Explorez Ask WhAI, un outil innovant pour étudier et interroger les croyances des agents IA dans des scénarios médicaux complexes, avec une analyse multi-spécialistes."
datePublished: Thu Nov 20 2025 05:14:12 GMT+0000 (Coordinated Universal Time)
cuid: cmi6z82bm000d02l43bwyfncd
slug: ask-whai-comprendre-croyances-agents-llm-multi-roles
canonical: https://arxiv.org/abs/2511.14780

---

# Ask WhAI : analyser la formation des croyances dans des agents IA multi-spécialistes

Les avancées dans le domaine de l'intelligence artificielle (IA), et plus spécifiquement les grands modèles de langage (LLM), ont ouvert des perspectives fascinantes dans les interactions entre humains et agents artificiels. Cependant, une interrogation persiste : comment ces agents formulent-ils leurs croyances ? Est-il possible de comprendre, voire d'influencer, ces croyances en fonction des informations reçues ou des rôles endossés ? C’est précisément à ces questions que répond la plateforme expérimentale **Ask WhAI**. Ce framework novateur propose un moyen unique d’étudier et de rendre transparentes les dynamiques de croyances dans des systèmes multi-agents, même dans des scénarios riches comme ceux de la médecine.

## Qu'est-ce que Ask WhAI ?

### Un cadre pensé pour les interactions multi-agents

Ask WhAI est une plateforme conçue pour analyser et expliquer les processus de **formation des croyances** et de **raisonnement en contexte multi-agents**. Elle se distingue par ses fonctionnalités avancées permettant d’explorer les dynamiques cognitives des agents IA travaillant ensemble. Parmi ses caractéristiques fondamentales, on peut citer :

- **Enregistrement et reproduction des interactions :** les échanges entre agents peuvent être documentés et rejoués pour une analyse approfondie.
- **Questionnement direct des croyances :** il est possible d’interroger explicitement un agent sur ses opinions ou son raisonnement à chaque étape.
- **Injection de contre-faits :** en ajoutant des informations hypothétiques, les chercheurs peuvent examiner comment les agents ajustent leurs croyances et réagissent aux nouvelles données.

Ce cadre va bien au-delà de simples simulations : il propose une ouverture sans précédent sur le fonctionnement interne des processus décisionnels des agents.

### Une application dans la médecine

Pour démontrer la pertinence de leur approche, les chercheurs ont testé Ask WhAI dans un simulateur de cas médicaux. Dans cette expérience, des agents, modélisés comme des spécialistes humains (par exemple, neurologue ou infectiologue), coopèrent à travers une base de données médicale commune. Un "oracle" nommé **LabAgent** joue également un rôle clé en agissant tel un laboratoire, dévoilant les résultats uniquement lorsque cela est requis.

Un cas pratique marquant concerne le diagnostic d’un enfant manifestant des **symptômes neuropsychiatriques soudains**. L’étude de la plateforme a ainsi permis d’observer les interactions des agents avant et après des événements critiques. En couplant leurs croyances initiales avec des preuves nouvelles ou des contre-évidences, la plateforme met en lumière leurs processus décisionnels et leurs biais cognitifs.

---

## Principales fonctionnalités du framework

Le fonctionnement d’Ask WhAI repose sur trois piliers technologiques majeurs :

1. **Traçabilité des croyances**
   - L’une des innovations essentielles d’Ask WhAI est sa capacité à rendre les croyances des agents visibles et traçables. Ce qui est souvent considéré comme une “boîte noire” dans les systèmes complexes de décision peut désormais être interrogé et reproduit.

2. **Réplication des scénarios**
   - Grâce à l’enregistrement systématique des interactions, Ask WhAI permet de rejouer les échanges entre agents pour mieux comprendre les éléments ayant influencé les croyances.

3. **Analyse basée sur les contre-faits**
   - La plateforme introduit des informations hypothétiques ou contradictoires aux agents afin de vérifier comment elles modifient leur raisonnement et influencent leur réponse.

Ces éléments font d’Ask WhAI un atout majeur pour les chercheurs qui souhaitent tester et valider les modèles de croyances dans les systèmes cognitifs artificiels.

---

## Étude de cas : diagnostic médical multi-agent

Dans l’expérimentation décrite par les chercheurs, plusieurs agents spécialisés en médecine se penchent sur un cas clinique complexe. Le scénario reproduit fidèlement les conditions d’un hôpital virtuel : les agents ont accès à un dossier médical électronique et interagissent entre eux ainsi qu’avec l’agent oracle LabAgent. Ce dernier fournit des résultats de laboratoire uniquement lorsqu’une requête spécifique est formulée.

### L’expérience en détail

- **Situation initiale :** un enfant arrive avec des symptômes neuropsychiatriques qui déclenchent différentes hypothèses diagnostiques chez les spécialistes.
- **Évolution des croyances :** à partir de nouveaux éléments (injections de contre-faits ou résultats d’examens), les chercheurs observent comment les croyances des agents évoluent.
- **Comparaisons pré/post :** en documentant précisément les états de croyance avant et après chaque étape du processus de diagnostic, la plateforme révèle la manière dont les données sont interprétées.

L’ensemble de l’analyse met en lumière des phénomènes captivants, notamment des comportements bien connus chez les spécialistes humains tels que le **biais de spécialité**.

---

## Biais et limites des agents IA

### Tendances à imiter les humains

L’une des découvertes les plus intéressantes de cette recherche est que les agents, bien qu’artificiels, tendent à exprimer des **biais similaires à ceux des spécialistes humains**. Par exemple, certains démontrent une forte réticence vis-à-vis de contre-évidences, préférant se fier à des études canoniques ou à leur propre expertise initiale. Ce mimétisme soulève des questions sur la manière dont ces biais humains se transfèrent aux machines.

### Limitations actuelles du framework

Malgré ses promesses, **Ask WhAI** rencontre certaines limitations :

1. **Biais analogiques avec les humains :** la fidélité avec laquelle les agents reproduisent les comportements humains est encore incertaine et doit être étudiée davantage.
2. **Scénarios exclusivement médicaux :** la démonstration de la plateforme s’est principalement concentrée sur le diagnostic médical. D’autres champs d’application, tels que la cybersécurité ou les politiques publiques, mériteraient d’être explorés.
3. **Design complexe :** la mise en place et le fonctionnement du simulateur nécessitent une expertise technique approfondie, un frein potentiel à son adoption.

---

## Impact potentiel sur l'intelligence artificielle

Cette recherche ouvre de nouvelles voies dans le développement des systèmes IA capables d’opérer dans des environnements complexes avec plusieurs rôles spécialisés. L’approche d’Ask WhAI, qui rend visible et testable la formation des croyances, est essentielle pour garantir la transparence dans la prise de décision par les machines.

Sur des terrains critiques comme la médecine, la transparence des décisions peut améliorer la confiance envers l’IA, tout en permettant d'identifier les biais inhérents à ses algorithmes. Ce type de framework pourrait également devenir un outil clé pour les régulateurs et chercheurs souhaitant évaluer le comportement des systèmes intelligents dans des contextes sensibles.

---

## À retenir sur Ask WhAI

- **Ask WhAI** propose un cadre unique pour observer et analyser la formation des croyances des agents IA.
- En testant ces dynamiques dans des contextes médicaux complexes, le framework démontre comment les biais disciplinaires peuvent être révélés et étudiés.
- En modélisant les croyances et en rendant leur évolution traçable, Ask WhAI offre une opportunité inédite d’améliorer la transparence et la testabilité des systèmes multi-agents.
- Bien qu'il soit actuellement limité à des scénarios médicaux, ce type de solution pourrait être une avancée majeure dans d'autres domaines critiques tels que la sécurité, les politiques publiques ou la gestion de catastrophes.


Sources : [Ask WhAI sur arXiv](https://arxiv.org/abs/2511.14780)

[source](https://arxiv.org/abs/2511.14780)