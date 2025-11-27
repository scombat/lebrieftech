---
title: "Migration du dépôt principal de Zig de GitHub vers Codeberg"
seoTitle: "Migration du dépôt Zig : GitHub vers Codeberg"
seoDescription: "Le langage de programmation Zig migre son dépôt principal de GitHub à Codeberg pour des raisons de fiabilité, alignement philosophique et performances."
datePublished: Thu Nov 27 2025 04:53:43 GMT+0000 (Coordinated Universal Time)
cuid: cmigykowx000902lb89jo3yt9
slug: migration-depot-zig-github-vers-codeberg-1
canonical: https://ziglang.org/news/migrating-from-github-to-codeberg/

---

# Migration du dépôt principal de Zig de GitHub vers Codeberg

## TL;DR

- Zig a migré son dépôt principal de GitHub vers Codeberg pour des raisons de fiabilité, de performance et d’alignement philosophique.
- La dégradation des services de GitHub, associée à un désalignement sur des questions éthiques (comme l'utilisation de l'IA), a motivé cette décision.
- GitHub Sponsors, une source de financement historique pour Zig, est progressivement remplacé par Every.org.
- Les issues existantes sur GitHub seront maintenues, mais les nouvelles seront créées sur Codeberg avec un système de numérotation spécifique.
- La transition vise à garantir la continuité du projet tout en s’appuyant sur une plateforme alignée avec ses valeurs.

## Pourquoi Zig quitte GitHub ?

Zig, un langage de programmation conçu pour offrir performance et simplicité, a été hébergé sur GitHub pendant près de dix ans. Cependant, plusieurs facteurs ont conduit l’équipe du projet à chercher une alternative plus adaptée.

Parmi les raisons principales figurent les problèmes techniques croissants observés sur GitHub. La qualité des outils et performances offerts par la plateforme s’est dégradée au fil du temps, rendant de plus en plus difficile la gestion efficace des workflows du projet. Les utilisateurs ont, par exemple, signalé des retards dans les pipelines d’intégration continue (CI) et un manque de support réactif pour résoudre ces ralentissements.

Un autre élément crucial est le rachat de GitHub par Microsoft. Cet événement a intensifié les préoccupations de certaines communautés open source, conduisant Zig à reconsidérer sa position à long terme. La promotion par GitHub de fonctionnalités basées sur l’intelligence artificielle, comme Copilot, va à l’encontre des valeurs fondamentales de Zig, qui s’oppose fermement à l'intégration d’outils d’IA dans son écosystème.

Finalement, la perte de confiance dans GitHub Sponsors, autrefois une source de financement clé pour Zig, a marqué un tournant dans la stratégie de la fondation.

## Les raisons de la migration vers Codeberg

### Fiabilité et performance technique

Codeberg a été choisi en premier lieu pour sa fiabilité accrue et son alignement technique par rapport aux besoins de Zig. En tant que plateforme focalisée sur le libre et dépourvue de contraintes commerciales, Codeberg offre un soutien structurel qui répond mieux aux exigences des projets comme Zig. Contrairement à GitHub, Codeberg mise sur des solutions simples, évitant les complexités inutiles des outils comme GitHub Actions.

### Alignement philosophique

L’un des arguments majeurs pour la migration a été l’alignement idéologique entre la communauté Zig et la philosophie de Codeberg. Ce dernier rejette les outils d’intelligence artificielle pour se concentrer sur un respect strict de la vie privée des utilisateurs et sur une approche non marchande de l’hébergement de code. Ce positionnement rejoint les principes de Zig : offrir un environnement transparent et axé sur l’excellence technique, exempt de compromis commerciaux dictés par des entreprises privées.

Codeberg s’inscrit également dans une vision long terme du rôle fondamental des logiciels open source et de la souveraineté numérique — des sujets de préoccupation majeurs pour les dirigeants et contributeurs de Zig.

## Impact sur le financement

Alors que GitHub Sponsors a joué un rôle crucial dans le développement initial de Zig en permettant à ses membres de bénéficier d’un soutien financier régulier, leurs perceptions de ce programme ont changé au fil du temps. La dégradation du produit et le départ de Devon Zuegel, qui avait largement contribué à son succès, ont entraîné une baisse significative de la qualité du service.

En conséquence, la Zig Software Foundation encourage désormais ses donateurs à passer à Every.org, une plateforme à but non lucratif. Cette transition vise à réduire la dépendance envers une seule source de financement et à offrir des options plus diversifiées tout en garantissant la stabilité financière du projet. Bien que cette décision risque de perturber certains donateurs habitués à GitHub Sponsors, il est attendu qu’elle se traduise à terme par une base de financement plus résiliente.

## Le processus de transition

Le processus de migration de GitHub vers Codeberg a été soigneusement planifié afin de minimiser les perturbations pour les contributeurs et les utilisateurs.

- Le dépôt GitHub principal de Zig (`ziglang/zig`) est désormais en mode lecture seule. Il ne sera plus possible d’y soumettre de nouvelles contributions ou de signaler des issues.
- Toutes les nouvelles issues seront gérées sur le dépôt Codeberg de Zig ([Codeberg - ziglang/zig](https://codeberg.org/ziglang/zig)).
- Pour éviter les confusions avec les issues existantes sur GitHub, la numérotation sur Codeberg commencera à partir de #30000.
- Les issues existantes sur GitHub resteront accessibles pour consultation ou pourront être transférées vers Codeberg si nécessaire via une méthode "copy-on-write".

La réalisation de cette migration a été possible grâce à l’engagement de plusieurs contributeurs chevronnés, notamment Earl Warren, Otto, Gusted et Mathieu Fenniak, qui ont travaillé à chaque étape pour garantir une migration fluide.

## Enjeux et perspectives pour Zig

### Stabilité de la plateforme Codeberg

L’une des inconnues majeures est la capacité de Codeberg à gérer la charge associée à un projet de l’envergure de Zig. Codeberg ayant une base d’utilisateurs plus restreinte que GitHub, il reste à voir si l’afflux de nouveaux contributeurs et utilisateurs n’affectera pas ses performances et sa stabilité.

### Impact financier

Malgré la transition vers Every.org, certains craignent que la migration n’entraîne des pertes de financement, notamment auprès de donateurs habitués à GitHub Sponsors. La Zig Software Foundation devra surveiller de près les effets de ce changement sur ses ressources financières à long terme.

### Perception de la communauté

Le passage de GitHub à Codeberg est une étape importante dans la vie du projet, mais elle pourrait bousculer une partie de sa communauté. Les utilisateurs ayant construit des workflows autour de GitHub devront s’adapter à la nouvelle plateforme. Zig devra potentiellement investir dans des actions de communication et de pédagogie pour accompagner cette transition.

## Leçons à retenir

La migration de Zig vers Codeberg illustre plusieurs enseignements sur la gestion d’un projet open source :

- **Révision continue des outils** : Les performances, la stabilité et l’éthique d’une plateforme doivent être régulièrement réévaluées.
- **Alignement avec les valeurs** : Les préférences en matière d’éthique et de philosophie ne sont pas secondaires ; elles jouent un rôle clé dans la pérennité des projets communautaires.
- **Diversification des financements** : S’appuyer sur une seule source de revenus, bien que pratique, peut limiter la résilience financière d’un projet.

En optant pour Codeberg, Zig ne fait pas qu’adopter une nouvelle plateforme. Le projet pose aussi les bases d’un écosystème pourquoi reposer sur des principes solides, tout en adressant des problématiques techniques et philosophiques d’actualité.

[source](https://ziglang.org/news/migrating-from-github-to-codeberg/)