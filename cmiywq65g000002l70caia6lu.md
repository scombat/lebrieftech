---
title: "Renforcer la sécurité des GPUs Android via une collaboration avec Arm"
seoTitle: "Renforcer la sécurité des GPU Android : Collaboration de Google et Arm"
seoDescription: "Découvrez les efforts de Google et Arm pour renforcer la sécurité des GPUs Android via une réduction de la surface d'attaque et des politiques SELinux avancées."
datePublished: Tue Dec 09 2025 18:21:50 GMT+0000 (Coordinated Universal Time)
cuid: cmiywq65g000002l70caia6lu
slug: renforcer-securite-gpu-android-google-arm
canonical: http://security.googleblog.com/2025/12/further-hardening-android-gpus.html

---

# Renforcer la sécurité des GPUs Android via une collaboration avec Arm

## TL;DR

- Les GPUs Android sont des cibles majeures pour les attaquants en raison de leur complexité et de leur rôle clé dans le système.
- Google et Arm ont collaboré pour analyser et réduire la surface d'attaque des drivers utilisés sur les GPUs Mali.
- SELinux joue un rôle central dans l'application de politiques de sécurité efficaces, limitant les accès dangereux tout en préservant la compatibilité avec les applications.
- Des politiques de sécurité renforcées sont déployées progressivement dans l'écosystème Android.

## Pourquoi la sécurité des GPUs est essentielle

Les GPUs (Graphics Processing Units) sont désormais des composants cruciaux dans les smartphones Android. Ces processeurs graphiques, responsables de traiter les images, vidéos et animations, jouent un rôle essentiel non seulement dans l'expérience utilisateur, mais aussi dans l'exécution d'applications complexes, y compris celles reposant sur l'intelligence artificielle.

Cependant, cette importance rend les GPUs particulièrement vulnérables. Leur interaction directe avec le kernel Android leur donne un accès privilégié aux ressources du système, ce qui en fait une cible de choix pour les attaquants. Depuis 2021, une majorité des exploits sur les drivers du kernel Android ont concerné les GPUs. Leur complexité, combinée à des implémentations parfois anciennes, expose des failles qui peuvent être utilisées pour compromettre l'intégrité du système.

## Collaboration entre Google et Arm

Pour contrer ces menaces, Google et Arm ont uni leurs forces afin de renforcer la sécurité des GPUs Android. Leur partenariat s'est concentré sur le driver Mali, utilisé dans près de 45 % des appareils Android dans le monde. Ce choix n'est pas anodin : le GPU Mali est omniprésent dans l'écosystème Android et sa sécurité est cruciale.

L'objectif principal de cette collaboration était de réduire la "surface d'attaque" des drivers, c'est-à-dire de diminuer les points potentiels par lesquels un hacker pourrait tenter de compromettre le système. Les ingénieurs de Google et d'Arm ont analysé les zones les plus vulnérables, identifiant les fonctions accessibles aux utilisateurs, qui représentaient un risque particulier. Les enseignements de cette étude ont permis d'élaborer des stratégies concrètes pour durcir ces surfaces d'attaque.

## Hardening avec SELinux : une solution efficace

SELinux (Security-Enhanced Linux) s'est révélé un outil clé dans le durcissement des GPUs Android. Cette technologie permet de contrôler les permissions accordées aux différentes parties du système, en imposant des politiques strictes.

Dans le cas des GPUs Mali, SELinux a été utilisé pour limiter l'accès à certaines fonctions critiques du driver via les IOCTLs (Input/Output Control). Ces opérations, souvent nécessaires pour interagir directement avec le périphérique matériel, peuvent devenir des points d'entrée pour les attaquants. En contraignant leur usage aux seuls processus autorisés, SELinux réduit la possibilité d'exploits tout en assurant que les applications légitimes continuent de fonctionner normalement.

Cette approche technique est bénéfique car elle permet de combiner sécurité et compatibilité. Les restrictions ne perturbent pas les utilisateurs finaux et les développeurs peuvent toujours créer des applications intègres, même si certaines fonctionnalités du GPU sont désormais mieux protégées.

## Déploiement progressif des politiques de sécurité

Google et Arm ont opté pour une adoption stratégique et progressive de ces nouvelles politiques SELinux. Plutôt que de déployer des changements radicaux qui pourraient potentiellement perturber l'écosystème Android, les nouvelles mesures de sécurité sont adaptées à chaque génération de matériel et intégrées progressivement.

Cette approche permet aux fabricants de smartphones et aux développeurs tiers de s'ajuster aux nouvelles règles tout en bénéficiant de temps pour garantir la compatibilité de leurs produits et de leurs applications. Par exemple, les politiques SELinux spécifiques aux GPUs Mali sont maintenant adoptées sur les derniers modèles de smartphones Android, en collaboration avec les fabricants. Cela limite les risques tout en favorisant une adoption étendue de ces dispositifs sécuritaires.

## Guide pratique pour adopter la politique SELinux

Pour les développeurs et ingénieurs travaillant sur l'intégration ou l'optimisation d'Android, voici quelques étapes pratiques pour tirer parti des politiques SELinux :

- **Analyse des IOCTLs nécessaires** : Identifiez les fonctionnalités critiques utilisées par votre application et vérifiez lesquelles sont désormais soumises à des restrictions.
- **Adoption des politiques actuellement recommandées** : Utilisez les outils et documentations fournis par Google pour incorporer les politiques SELinux propres aux GPUs.
- **Tests approfondis** : Avant de publier une mise à jour ou un nouvel appareil, effectuez des tests sur les fonctionnalités graphiques pour éviter toute incompatibilité avec les nouveaux paramètres SELinux.
- **Collaboration avec les OEMs** : Si vous travaillez avec des fabricants, inhérente à Android, assurez-vous de leur fournir les informations nécessaires pour une intégration harmonieuse.

## Conclusion

La sécurité des GPUs est un défi de taille dans l'écosystème Android, mais les efforts conjoints de Google et Arm montrent qu'il est possible de l'améliorer efficacement sans compromettre la compatibilité. SELinux, en tant qu'outil de gestion des permissions, a permis de mettre en place des solutions innovantes pour durcir les drivers de GPUs tout en permettant une transition progressive.

Les développeurs et ingénieurs sont invités à se familiariser avec ces nouvelles politiques de sécurité afin de contribuer à un environnement Android plus sécurisé.

[source](http://security.googleblog.com/2025/12/further-hardening-android-gpus.html)