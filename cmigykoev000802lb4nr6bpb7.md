---
title: "Pourquoi Zig quitte GitHub pour Codeberg : Les raisons et implications"
seoTitle: "Migration du dépôt Zig : de GitHub à Codeberg pour plus de liberté et fiabilité"
seoDescription: "La migration de Zig de GitHub à Codeberg s'inscrit dans une volonté d'alignement avec les valeurs éthiques, une gestion du code améliorée et une meilleure fiabilité."
datePublished: Thu Nov 27 2025 04:53:42 GMT+0000 (Coordinated Universal Time)
cuid: cmigykoev000802lb4nr6bpb7
slug: migration-depot-zig-github-vers-codeberg
canonical: https://ziglang.org/news/migrating-from-github-to-codeberg/

---

# Pourquoi Zig quitte GitHub pour Codeberg : Les raisons et implications

## TL;DR

- Zig migre son dépôt principal de GitHub vers Codeberg, invoquant des raisons de performance, de fiabilité et d'alignement avec des valeurs éthiques.
- Les problèmes de qualité du service GitHub et des outils comme GitHub Actions ont poussé l’équipe à changer de plateforme.
- L’opposition de Zig à l’utilisation des outils d’IA comme GitHub Copilot a renforcé cette décision.
- GitHub Sponsors, une source importante de financement, n’est plus jugé suffisamment fiable ; Zig préfère désormais Every.org.
- Une stratégie minutieuse a été mise en place pour gérer les issues et assurer une transition en douceur.

## Contexte de la migration

Zig, un langage de programmation connu pour sa simplicité et son efficacité, s'appuyait sur GitHub depuis près de dix ans pour héberger son code source. Cependant, cette relation s’est détériorée au fil du temps, et plusieurs facteurs, à la fois techniques et philosophiques, ont conduit les responsables à chercher des alternatives. Parmi ces facteurs, l'équipe a notamment cité une baisse de performance, des limitations dans les services et des divergences fondamentales avec les valeurs de GitHub.

La situation s’est aggravée après le rachat de GitHub par Microsoft, instaurant une méfiance accrue envers une plateforme désormais perçue comme trop commerciale. En conséquence, Zig a choisi de migrer vers Codeberg, une plateforme open-source orientée communauté et respectant des principes plus alignés avec l’éthique du projet.

## Pourquoi quitter GitHub pour Codeberg ?

### Dégradation de la qualité et des performances

Avec le temps, l’équipe derrière Zig a observé une détérioration significative de plusieurs aspects techniques chez GitHub. Voici quelques exemples des problèmes rencontrés :

- Le système de Continuous Integration (CI) est devenu instable, allongeant considérablement les délais pour le déploiement des pipelines.
- Les outils, notamment GitHub Actions, présentent des bugs fréquents, avec une réduction de la fiabilité générale.
- La nécessité de demander des interventions manuelles s'est multipliée en raison de la lenteur ou des défaillances des services.

Ces frustrations se sont accumulées, rendant insoutenable pour l’équipe de continuer à travailler sur une infrastructure aussi peu fiable. Plutôt que d’investir davantage de ressources pour contourner les faiblesses techniques, Zig a décidé de rechercher une alternative.

### Un alignement philosophique

Au-delà des considérations techniques, GitHub et Zig divergent sur des questions de fond. GitHub a mis au centre de sa stratégie commerciale l’intégration d’outils basés sur l’intelligence artificielle, notamment avec le lancement de GitHub Copilot. Cette orientation est en opposition avec les valeurs fondamentales de Zig, qui prône une stricte limitation des outils basés sur l’IA et une approche non commerciale en faveur de l’écosystème open-source.

En choisissant Codeberg, Zig bénéficie désormais d’un espace dépourvu de produits axés sur l’IA. La plateforme est gérée comme une initiative sans but lucratif, alignée avec les objectifs d’un développement open-source fiable, éthique et transparent.

## Impact sur GitHub Sponsors et financement

Depuis son lancement, GitHub Sponsors a été une source de financement essentielle pour la Zig Software Foundation, en grande partie grâce aux efforts de Devon Zuegel, une figure clé de cette initiative. Cependant, les récents changements dans la gestion de GitHub Sponsors, notamment après le départ de Zuegel, ont diminué la confiance de l'équipe envers cette plateforme.

Cette perte de fiabilité a amené l’équipe Zig à se tourner vers Every.org, une organisation à but non lucratif, pour collecter des fonds. Cette transition permet de diversifier les sources de financement tout en maintenant les avantages pour les donateurs. Cette stratégie vise à réduire les risques liés à une dépendance excessive vis-à-vis d’un seul acteur du financement.

## Plan détaillé de la migration

La décision de quitter GitHub pour Codeberg a été soigneusement planifiée pour minimiser les perturbations pour les contributeurs et les utilisateurs du projet. Voici les grandes lignes de cette transition :

- Le dépôt `ziglang/zig` sur GitHub est désormais en lecture seule.
- Le dépôt principal du projet est transféré sur **[Codeberg](https://codeberg.org/ziglang/zig)**.
- Les issues existantes sur GitHub restent ouvertes, mais seront gérées en mode "copy-on-write" : des modifications ou des ajouts seront répercutés sur le dépôt GitHub uniquement en cas de nécessité absolue.
- Les nouvelles issues ouvertes sur Codeberg commenceront à partir du numéro #30000 afin d'éviter toute confusion avec les numéros d'issues déjà présents sur l’ancien dépôt GitHub.

La transition a été rendue possible grâce au soutien crucial de plusieurs contributeurs de la communauté, notamment Earl Warren, Otto, Gusted et Mathieu Fenniak, qui ont joué un rôle clé dans l'organisation des différentes étapes.

## Défis et opportunités futures

### La question de la stabilité de Codeberg

L’un des principaux points d’interrogation reste la capacité de Codeberg à s’adapter aux besoins d’un projet de grande envergure comme Zig. Jusqu'à présent, la plateforme a répondu aux attentes, mais il faudra surveiller de près son évolution, notamment en cas d’afflux d’autres projets.

### Impact sur la communauté et les donateurs

Le changement de plateforme peut provoquer des réticences parmi les utilisateurs traditionnels de GitHub qui devront désormais s’adapter à un nouvel environnement. En parallèle, l'abandon des avantages liés à GitHub Sponsors pourrait entraîner une perte de revenus à court terme, bien que Zig espère compenser cet impact grâce à Every.org.

### Repenser l’hébergement de code à long terme

Cette décision met également en lumière un débat plus large concernant la dépendance à des plateformes centralisées. Pour des projets comme Zig, il est essentiel de continuer à évaluer les alternatives qui garantissent à la fois souveraineté et alignement avec les valeurs du projet. Cela pourrait encourager d’autres projets à explorer des options open-source moins centralisées et plus résilientes.

## Conclusion

La migration de Zig de GitHub vers Codeberg illustre les défis auxquels doivent faire face les projets open-source à la recherche d’un environnement technique stable et aligné avec des principes éthiques. En prenant cette décision, l’équipe Zig a également montré l’importance de diversifier ses sources de financement pour assurer la pérennité du projet. Bien que des défis subsistent, ce choix marque un tournant significatif pour la communauté Zig et pourrait inspirer d’autres dans leur recherche de plateformes alternatives pour l’hébergement de leur code.

[source](https://ziglang.org/news/migrating-from-github-to-codeberg/)