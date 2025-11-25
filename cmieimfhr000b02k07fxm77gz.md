---
title: "WhatsApp comble une faille critique exposant 3,5 milliards de comptes utilisateurs"
seoTitle: "WhatsApp : Une faille permettait d'accéder à 3,5 milliards de comptes"
seoDescription: "WhatsApp a corrigé une faille critique dans son API, exposant les données sensibles de 3,5 milliards de comptes utilisateurs. Découvrez les détails."
datePublished: Tue Nov 25 2025 11:51:38 GMT+0000 (Coordinated Universal Time)
cuid: cmieimfhr000b02k07fxm77gz
slug: whatsapp-faille-acces-3-5-milliards-comptes
canonical: https://www.malwarebytes.com/blog/news/2025/11/whatsapp-closes-loophole-that-let-researchers-collect-data-on-3-5b-accounts

---

# WhatsApp comble une faille critique exposant 3,5 milliards de comptes utilisateurs

## TL;DR

- Une faille dans l'API de WhatsApp permettait de confirmer l'existence de 3,5 milliards de comptes utilisateurs.
- Les chercheurs ont extrait des photos de profil, des statuts "À propos" et des métadonnées accessibles via cette vulnérabilité.
- Meta a mis en place des limitations de requêtes pour prévenir de telles exploitations à l'avenir.
- Ces données exposées pourraient avoir des implications graves dans le cadre de régimes autoritaires ou pour des usages malveillants.
- Les utilisateurs peuvent réduire leur vulnérabilité en ajustant leurs paramètres de confidentialité.

## Qu'est-ce qui a été exposé par cette faille ?

### L'API de découverte de contacts mise en cause

La faille identifiée par des chercheurs de l’Université de Vienne et SBA Research concernait l'utilisation abusive de l'API de découverte de contacts de WhatsApp. Cette API est conçue pour vérifier si un numéro de téléphone est associé à un compte WhatsApp. En théorie, cette fonction est limitée par des restrictions de requêtes, mais dans la pratique, les chercheurs ont démontré qu'il était possible de générer et de tester des numéros de téléphone à grande vitesse à raison de 100 millions de tests par heure.

### Nature des données accessibles

Grâce à cette faille, les chercheurs ont pu collecter :
- **Photos de profil** : Plus de deux tiers des comptes étudiés disposaient d’une image visible publiquement.
- **Descriptions "À propos"** : Ce champ, souvent utilisé pour des interactions privées, contenait parfois des informations sensibles liées à des opinions politiques, religieuses, sexuelles ou professionnelles.
- **Métadonnées** : Informations techniques liées au compte.

### Implications potentielles

Ces données exposées posent des risques :
- Exploitation par des outils de reconnaissance faciale ou de veille automatisée.
- Ciblage des utilisateurs sous des régimes restrictifs ou dans des pays où WhatsApp est interdit.
- Possibilité d'associer les comptes à des activités ou des identités sensibles, avec des impacts sur la vie privée ou la sécurité.

Dans des pays comme l’Iran ou la Chine, où l'utilisation de WhatsApp est surveillée ou interdite, ces résultats sont particulièrement préoccupants.

## Quelle a été la réponse de WhatsApp ?

### Actions prises par Meta

Après avoir été informée par les chercheurs, Meta, la société mère de WhatsApp, a rapidement agi en renforçant les limites de requêtes sur son API. Selon Nitin Gupta, Vice-président de WhatsApp, l’entreprise a également mis en place des technologies anti-scraping avancées pour détecter et bloquer les abus systématiques.

Meta a affirmé que les données obtenues étaient principalement des informations publiques. Toutefois, cette position ne minimise pas les risques potentiels de leur exploitation, notamment dans des contextes géopolitiques sensibles.

### Une transparence limitée

Malgré les efforts déployés, des questions restent ouvertes :
- Meta n’a pas détaillé les mesures spécifiques prises pour garantir la sécurité des autres points d’accès à son infrastructure.
- L’étendue des données déjà compromises en raison de cette faille demeure incertaine.

Cette situation rappelle également la fuite de données de Facebook en 2021, où 533 millions de comptes avaient été exposés. Parmi eux, 58 % des numéros étaient encore actifs sur WhatsApp en 2025.

## Que peuvent faire les utilisateurs pour se protéger ?

### Paramètres de confidentialité à ajuster

Les utilisateurs peuvent réduire leur exposition en adoptant les mesures suivantes :
- Limitez la **visibilité de votre photo de profil** à vos contacts uniquement.
- Configurez votre statut "À propos" de manière à ce qu'il ne soit accessible qu’à vos contacts.
- Évitez de partager des informations personnelles sensibles dans votre profil public.

### Utilisation d'outils dédiés

Des outils comme **Malwarebytes Personal Data Remover** peuvent aider à identifier et à retirer des informations personnelles exposées sur internet. En complément, il est recommandé d’effectuer des audits réguliers de vos paramètres de confidentialité sur services en ligne.

## Pourquoi cette faille est-elle importante ?

### Impacts sur la sécurité et la vie privée

Cette vulnérabilité met en lumière les risques liés aux API publiques, même lorsqu’elles sont censées être protégées par des limitations de requêtes. Elle illustre également la fragilité des infrastructures numériques face aux abus systématiques.

Outre les implications pour la vie privée des individus, cette faille soulève des préoccupations importantes :
- **Régimes autoritaires** : Les informations collectées pourraient être utilisées pour surveiller ou cibler des individus.
- **Reconnaissance faciale** : Les photos de profil exposées pourraient alimenter des bases de données utilisées par des logiciels de surveillance.
- **Exploitation commerciale ou malveillante** : Les données peuvent être revendues sur des marchés parallèles ou utilisées pour le phishing.

### La responsabilité des grandes plateformes

WhatsApp, en tant que service global utilisé par près de trois milliards de personnes, a une responsabilité majeure en matière de sécurité. Cette faille démontre que même les grandes entreprises doivent constamment améliorer leurs protections et leur transparence pour préserver les données personnelles de leurs utilisateurs.

## À retenir

Cette vulnérabilité dans l'API de WhatsApp rappelle l’importance de protéger ses données personnelles face aux abus potentiels des infrastructures numériques. Si Meta a pris des mesures correctives, cette faille souligne également la nécessité pour les utilisateurs de rester vigilants et d’adopter de bonnes pratiques en matière de confidentialité. Dans un monde de plus en plus connecté, la sécurité des données personnelles reste un enjeu crucial pour tous.

[source](https://www.malwarebytes.com/blog/news/2025/11/whatsapp-closes-loophole-that-let-researchers-collect-data-on-3-5b-accounts)