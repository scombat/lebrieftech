---
title: "Glassworm : nouvelles attaques sur Visual Studio Code"
seoTitle: "Glassworm : alertes sur Visual Studio Code et extensions malveillantes"
seoDescription: "Découvrez les attaques Glassworm ciblant les développeurs via des extensions malveillantes sur Visual Studio Marketplace et Open VSX Registry."
datePublished: Tue Dec 02 2025 11:51:43 GMT+0000 (Coordinated Universal Time)
cuid: cmioipig0000c02jsbz7o3u8w
slug: glassworm-attaques-visual-studio-code
canonical: https://www.techradar.com/pro/security/glassworm-returns-once-again-with-a-third-round-of-vs-code-attacks

---

# Glassworm : nouvelles attaques sur Visual Studio Code

## TL;DR

- La campagne Glassworm cible les développeurs avec 24 nouvelles extensions malveillantes infiltrées dans Visual Studio Marketplace et OpenVSX Registry.
- Ces extensions permettent de voler des tokens GitHub, npm ainsi que des données de portefeuilles cryptographiques.
- Les malwares Lumma Stealer et un client HVNC sont installés pour des actions malveillantes supplémentaires.
- Microsoft renforce ses systèmes de protection pour contrer ces attaques.

## Contexte et pertinence

Depuis quelques mois, les marketplaces dédiées aux extensions pour les environnements de développement sont devenues des cibles de choix pour des groupes malveillants sophistiqués. Parmi ces plateformes figurent Visual Studio Marketplace — utilisée par Microsoft pour ses outils tels que Visual Studio et Visual Studio Code — ainsi qu’Open VSX Registry, une alternative open-source couramment adoptée.

La campagne Glassworm s’est illustrée par une infiltration stratégique de ces deux espaces, exploitant des vulnérabilités au sein des écosystèmes pour cibler des développeurs et des utilisateurs de portefeuilles numériques. Ces attaques soulignent les failles de sécurité potentielles dans les outils pourtant réputés comme essentiels pour le développement logiciel.

## Méthodes d'attaque du Glassworm

### Techniques de dissimulation

Glassworm s’appuie sur 24 extensions malveillantes récemment ajoutées dans les marketplaces ciblées. Ces extensions dissimulent leur contenu malveillant à l'aide de techniques avancées, notamment l'utilisation de caractères Unicode invisibles au sein du code. Cette ruse rend leur détection bien plus complexe.

### Actions malveillantes

Les extensions Glassworm effectuent diverses actions nuisibles, notamment :

- **Vol de données sensibles** : Elles exfiltrent les tokens GitHub, npm, et OpenVSX nécessaires aux développeurs pour accéder à leurs projets.
- **Exfiltration de portefeuilles numériques** : Elles s’attaquent aux données de 49 portefeuilles cryptographiques à travers des extensions de navigateur.
- **Installation de logiciels malveillants** : Le malware **Lumma Stealer** est déployé sur les systèmes Windows pour collecter des informations sensibles.
- **Installation d’un client HVNC** : Ce logiciel de contrôle à distance permet aux attaquants d’accéder furtivement aux machines compromises.
- **Utilisation de proxys SOCKS** : Pour masquer leurs activités en ligne, les attaquants configurent des proxys SOCKS, compliquant encore leur traçabilité.

### Cibles préférées des attaquants

Les frameworks populaires sont particulièrement visés, notamment :

- **Flutter**
- **React Native**
- **Vue.js**
- **Tailwind CSS**
- **Yaml**

Ces technologies, répandues parmi les développeurs professionnels et amateurs, représentent une avenue stratégique pour les cyberattaques à grande échelle.

## Réponse de Microsoft

Face à la montée en puissance des attaques Glassworm, Microsoft a pris des mesures pour réagir de manière proactive. Dans une déclaration faite à *BleepingComputer*, l’entreprise a souligné son engagement à améliorer les systèmes de détection sur Visual Studio Marketplace afin de limiter les abus. Des analyses automatisées approfondies ont été mises en place pour repérer plus facilement les extensions suspectes.

Les utilisateurs sont également encouragés à signaler tout contenu douteux via l’option « Report Abuse », directement accessible depuis les pages d’extensions. Ce mécanisme vise à permettre une réponse rapide avant que les extensions malveillantes ne causent davantage de perturbations.

## Risques pour les développeurs

### Vigilance renforcée requise

La nature insidieuse de Glassworm rend l’installation d’extensions particulièrement risquée pour les développeurs. Même après la suppression des extensions malveillantes, de nouvelles apparaissent rapidement dans les marketplaces.

### Élargissement des cibles

En prenant pour cible des outils populaires tels que Flutter et React Native, Glassworm accroît sa portée à des communautés techniques variées, augmentant ainsi les risques pour les développeurs dans différents secteurs.

### Menace persistante

Malgré les efforts déployés par les plateformes comme Microsoft ou Open VSX Registry, les acteurs malveillants démontrent une persistance efficace pour réintroduire des logiciels nuisibles dès que les protections se relâchent.

## Conseils pour se protéger

Pour sécuriser vos environnements de développement face à des campagnes telles que Glassworm, voici quelques recommandations concrètes :

1. **Analyser les extensions avant installation** : Vérifiez les avis, le nombre de téléchargements et l'historique avant de télécharger une extension.
2. **Signalement rapide** : Utilisez les boutons de signalement (« Report Abuse ») en cas de doute sur une extension ou un plugin.
3. **Utilisation d’outils de sécurité** : Intégrez des solutions de scan anti-malwares pour surveiller les environnements de travail.
4. **Restreindre les permissions** : Limitez les accès donnés aux outils tiers pour minimiser l’impact des vols de tokens.
5. **Surveiller les mises à jour de sécurité** : Restez informé des évolutions des politiques de protection sur les plateformes comme Visual Studio Marketplace.

Glassworm constitue un rappel sévère concernant la fragilité des écosystèmes de développement open-source face aux cyberattaques. En se montrant vigilant et en adoptant des pratiques sécurisées, les développeurs peuvent se prémunir plus efficacement contre ce genre de menaces.

[source](https://www.techradar.com/pro/security/glassworm-returns-once-again-with-a-third-round-of-vs-code-attacks)