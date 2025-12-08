---
title: "Vulnérabilité critique de Sneeit Framework : Sécurisez votre site WordPress"
seoTitle: "Faille RCE critique de Sneeit Framework : Protégez votre site WordPress maintenant"
seoDescription: "Une vulnérabilité dans Sneeit Framework permet aux hackers d'ajouter des administrateurs. Découvrez comment mettre à jour et sécuriser votre site WordPress."
datePublished: Mon Dec 08 2025 17:53:33 GMT+0000 (Coordinated Universal Time)
cuid: cmixg9xt7000102kz7nc5edb9
slug: faille-rce-sneeit-framework-securiser-wordpress
canonical: https://www.techradar.com/pro/security/sneeit-wordpress-rce-flaw-allows-hackers-to-add-themselves-as-admin-heres-how-to-stay-safe

---

# Vulnérabilité critique de Sneeit Framework : Sécurisez votre site WordPress

## TL;DR

- Une faille critique (CVE-2025-6389) dans le plugin WordPress Sneeit Framework (≤ v8.3) permet à des attaquants de créer des comptes administrateurs non autorisés.
- Les attaques ont commencé dès la divulgation publique de la vulnérabilité, avec plus de 131 000 tentatives bloquées en une journée.
- Pour sécuriser votre site, mettez à jour vers la version 8.4, surveillez les activités suspectes comme les nouveaux comptes administrateurs ou les fichiers modifiés.
- Maintenez votre WordPress, vos plugins et vos thèmes toujours à jour.

## Contexte de la vulnérabilité

Le plugin Sneeit Framework est un outil populaire utilisé sur les sites WordPress pour gérer des thèmes et des fonctionnalités avancées. Cependant, une vulnérabilité critique de type **remote code execution (RCE)** a été identifiée dans ce plugin jusqu’à la version **8.3 incluse**. Cette faille, enregistrée sous la référence **CVE-2025-6389**, est considérée extrêmement dangereuse avec une note de sévérité de 9,8/10 selon l’échelle CVSS.

La découverte a été faite par des analystes de sécurité de **WordFence**, qui ont mis en évidence les risques majeurs pour un grand nombre de sites utilisant cette extension. En exploitant cette vulnérabilité, des attaquants peuvent prendre le contrôle total des sites cibles, ce qui nécessite une réaction rapide et appropriée de la part des administrateurs WordPress.

## Impact de la faille sur WordPress

Les conséquences potentielles de cette vulnérabilité sont graves et variées :

- **Création de comptes administrateurs fictifs** : Les hackers peuvent s’ajouter en tant qu’administrateurs non autorisés.
- **Contrôle du site compromis** : Une fois les privilèges obtenus, ils peuvent modifier le contenu, installer des outils malveillants et analyser le trafic.
- **Injection de plugins malveillants** : Cela peut inclure des backdoors et des outils destinés à exfiltrer des données.
- **Redirection vers des sites malveillants** : Les visiteurs peuvent être redirigés vers des pages de phishing ou infectées.
- **Installation d’outils de collecte** : Les attaquants peuvent installer des scripts pour voler des informations sensibles sur les utilisateurs et les administrateurs.

La faille représente une menace directe pour la sécurité et l’intégrité des sites WordPress touchés. Les administrateurs doivent agir rapidement pour minimiser les dommages.

## Chronologie des attaques

Les attaques exploitant cette vulnérabilité ont commencé **immédiatement après sa divulgation publique**. Les détails sont édifiants :

- **Jour 1 :** WordFence a enregistré et bloqué **131 000 tentatives** en seulement 24 heures.
- **Attaques en cours :** Le rythme actuel est estimé à **15 000 exploitations par jour**.
- **Cibles visées :** Des milliers de sites utilisant encore les versions obsolètes du plugin Sneeit Framework.

Ces chiffres illustrent l’importance cruciale de prendre des mesures immédiates pour protéger votre site, d’autant que ces attaques sont automatisées et à grande échelle.

## Recommandations pour protéger votre site

Pour éviter que votre site ne soit compromis, voici les principales étapes à suivre :

1. **Mettez à jour vers Sneeit Framework 8.4** : Cette version corrige la faille critique et doit être installée rapidement.
2. **Maintenez WordPress et ses extensions à jour** : Les mises à jour fréquentes corrigent les vulnérabilités identifiées et assurent une sécurité optimale.
3. **Surveillez les indicateurs de compromission** : Les signes d'une attaque en cours incluent :
   - Apparition de nouveaux comptes administrateurs non reconnus.
   - Présence de fichiers suspects tels que `xL.php` ou `Canonical.php`.
   - Changements non autorisés dans des fichiers critiques comme `.htaccess`.
   - Fichiers inhabituels dans les logs, par exemple `finderdata.txt`.
   - Demandes AJAX inhabituelles provenant d’adresses IP spécifiques.

4. **Nettoyez votre site** : Supprimez les fichiers, thèmes ou plugins inutilisés pour réduire les surfaces d’attaque.
5. **Surveillez l’activité de vos outils de sécurité** : Utilisez des extensions comme WordFence pour recevoir des alertes et renforcer les défenses de votre site.

## Conclusions et mesures préventives

Cette vulnérabilité critique est un rappel important de l’importance de maintenir votre CMS WordPress, vos plugins et vos thèmes constamment à jour. Une vigilance active est essentielle, même après avoir appliqué les correctifs nécessaires, car les menaces évoluent rapidement.

Les administrateurs doivent également investir dans la surveillance proactive de leurs sites à l’aide de solutions comme WordFence et programmer des audits réguliers. Enfin, restez informé des vulnérabilités signalées pour tous vos outils tiers et appliquez les correctifs dès leur disponibilité.

En prenant ces mesures concrètes dès aujourd’hui, vous protégez non seulement votre site, mais également vos données, votre réputation et celles de vos utilisateurs.

[source](https://www.techradar.com/pro/security/sneeit-wordpress-rce-flaw-allows-hackers-to-add-themselves-as-admin-heres-how-to-stay-safe)