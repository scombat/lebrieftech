---
title: "Un bug de Windows 11 fait chuter les performances des cartes Nvidia dans Assassin's Creed Shadows"
seoTitle: "Bug Windows 11 : baisse des performances Nvidia dans Assassin's Creed Shadows"
seoDescription: "Un bug de Windows 11 affecte lourdement les performances des GPU Nvidia, notamment dans Assassin's Creed Shadows, chutant jusqu'à 50 %."
datePublished: Tue Nov 25 2025 22:52:04 GMT+0000 (Coordinated Universal Time)
cuid: cmif67r4a000002jsgv8sfn9c
slug: bug-windows-11-baisse-performances-nvidia-assassins-creed
canonical: https://www.techradar.com/computing/gpu/possible-windows-11-bug-with-nvidia-gpus-tanks-assassins-creed-shadows-performance-bringing-even-an-rtx-5090-to-its-knees

---

```markdown
# Un bug de Windows 11 fait chuter les performances des cartes Nvidia dans Assassin's Creed Shadows

## TL;DR

- La mise à jour KB5066835 de Windows 11 entraine une chute dramatique des performances des GPU Nvidia dans certains jeux.
- Dans Assassin’s Creed Shadows, des cartes haut de gamme comme la RTX 5090 enregistrent une baisse de 33 à 50 % des FPS.
- Nvidia a publié un correctif en version bêta, temporairement téléchargeable sur leur site.
- Une solution alternative consiste à désactiver la fonction "Resizable Bar" dans le BIOS.

## Résumé rapide du problème

La dernière mise à jour mensuelle de Windows 11 (référence KB5066835) a introduit de graves soucis techniques impactant significativement les performances des cartes graphiques Nvidia, notamment sur des titres exigeants comme *Assassin’s Creed Shadows*. 

Ce titre, très populaire et gourmand en ressources, présente des chutes de framerate allant jusqu’à 50 %, rendant l’expérience de jeu frustrante, même sur du matériel haut de gamme. Des tests ont révélé que la carte graphique Nvidia RTX 5090, pourtant une des plus performantes du marché, n'échappe pas à cette dégradation. Ce phénomène pourrait aussi s’étendre à d’autres jeux récents, comme *Counter-Strike 2*, rendant la situation encore plus préoccupante.

Face à ces problèmes, Nvidia a réagi rapidement en proposant un correctif en version bêta, alors que des solutions alternatives nécessitant des modifications de configuration BIOS ont également été suggérées. Cependant, aucun correctif définitif n’est disponible pour le moment.

## Impact des mises à jour Windows sur les performances

Ce problème met en lumière les risques liés aux mises à jour logicielles, particulièrement dans des écosystèmes aussi interconnectés que celui des jeux vidéo, des GPU et des systèmes d’exploitation comme Windows. À chaque mise à jour, des ajustements dans la communication entre les drivers, matériels et logiciels sont nécessaires. Une incompatibilité ou un bug peut engendrer des conséquences majeures, comme celles observées actuellement.

Les tests réalisés par les analystes de *Digital Foundry* illustrent bien la gravité de la situation. En exécutant *Assassin’s Creed Shadows* en 4K avec les paramètres de qualité optimaux (DLSS Quality activé), ils ont observé une chute du framerate de 72 FPS à 34 FPS, soit une perte de performances de plus de 50 %. Fait surprenant, même le couplage de ce jeu avec du matériel haut de gamme comme un GPU Nvidia RTX 5090 et un processeur AMD Ryzen 7 9800X3D n’a pas suffi à éviter ces performances dégradées. 

Il est toutefois important de noter que ce problème ne semble pas avoir d’impact sur les GPU concurrents, qu’ils soient produits par AMD ou Intel.

## Solutions proposées par Nvidia

En réponse à cette situation, Nvidia a publié un correctif d’urgence, distribué sous la forme d’une mise à jour bêta de ses pilotes graphiques. Ce correctif, disponible en téléchargement sur le site officiel de Nvidia, vise à limiter les pertes de performance pour *Assassin’s Creed Shadows*. Toutefois, étant donné qu’il s’agit d’une version bêta, il est possible que certains utilisateurs préfèrent attendre une version certifiée et stable, ce qui invite à la prudence.

En dehors de cette solution, Nvidia recommande également une méthode alternative : la désactivation de l’option *Resizable Bar* dans le BIOS de la carte mère. Cette fonction, qui permet aux processeurs d’accéder directement à toute la mémoire de la carte graphique, est conçue pour améliorer les performances dans de nombreux jeux. Toutefois, dans le cas de ce bug, sa désactivation peut aider à réduire l’impact des pertes de FPS. Il s’agit cependant d’un compromis, car cela peut dégrader légèrement les performances dans certains cas, même après la résolution du bug.

## Que faire en attendant un correctif définitif ?

Pour les utilisateurs impactés par ce problème, voici les deux principales solutions temporaires à envisager :

1. **Installer la mise à jour du pilote bêta de Nvidia :**  
   - Rendez-vous sur le site officiel de Nvidia pour télécharger la version bêta du correctif.
   - Cette solution est actuellement la plus efficace pour régler le problème, bien qu’une version stable sera probablement disponible ultérieurement.

2. **Modifier le paramétrage du BIOS pour désactiver *Resizable Bar* :**  
   - Accédez au BIOS de votre carte mère.
   - Cherchez l’option *Resizable Bar* (souvent située dans les paramètres avancés de la configuration PCIe).
   - Désactivez cette option, ce qui devrait, dans certains cas, diminuer l’impact du bug.
   - Attention cependant : cette solution peut entraîner une diminution potentielle des performances dans d’autres jeux.

Il est toujours recommandé de sauvegarder vos paramètres BIOS avant d’y apporter tout changement. 

## À surveiller dans les prochains jours

Voici les points à garder à l'œil pendant que Nvidia et Microsoft travaillent (espérons-le) à une solution définitive :

- **Réponse de Microsoft :** Bien que Nvidia ait communiqué que le problème résulterait de la mise à jour KB5066835 de Windows 11, la question reste de savoir si Microsoft prendra le problème à bras-le-corps ou si la responsabilité sera rejetée sur Nvidia.
- **Évaluation de l’impact :** Si le problème s’avère plus répandu, d’autres jeux gourmands en ressources, comme *Counter-Strike 2*, pourraient être affectés.
- **Déploiement d’un correctif stable :** Il est probable que Nvidia publie une mise à jour certifiée dans les semaines à venir. De plus, on peut espérer que Microsoft propose une révision de la mise à jour KB5066835 pour corriger la situation.

## À retenir

La mise à jour Windows KB5066835 a déclenché une diminution drastique des performances des GPU Nvidia dans certains jeux, en particulier le récent *Assassin's Creed Shadows*. Bien que Nvidia ait réagi rapidement avec un correctif bêta, les utilisateurs sont confrontés à des solutions temporaires parfois contraignantes en attendant une réponse définitive de Microsoft ou un driver stable de Nvidia. Cette situation illustre les challenges quotidiens du maintien de la compatibilité dans les environnements technologiques complexes, où chaque changement peut avoir des répercussions significatives sur la performance globale.
```

[source](https://www.techradar.com/computing/gpu/possible-windows-11-bug-with-nvidia-gpus-tanks-assassins-creed-shadows-performance-bringing-even-an-rtx-5090-to-its-knees)