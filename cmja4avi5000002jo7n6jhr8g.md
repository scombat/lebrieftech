---
title: "Failles critiques dans les produits Fortinet : systèmes compromis par des vulnérabilités"
seoTitle: "Failles critiques dans les produits Fortinet exposant les systèmes à des attaques"
seoDescription: "Des failles critiques dans les produits Fortinet permettent aux hackers de compromettre des systèmes via des vulnérabilités SAML. Mises à jour recommandées."
datePublished: Wed Dec 17 2025 14:39:22 GMT+0000 (Coordinated Universal Time)
cuid: cmja4avi5000002jo7n6jhr8g
slug: failles-critiques-produits-fortinet
canonical: https://www.techradar.com/pro/security/fortinet-products-hit-by-further-security-flaws-giving-hackers-access-to-systems-and-more

---

# Failles critiques dans les produits Fortinet : systèmes compromis par des vulnérabilités

## TL;DR

- Deux vulnérabilités critiques (CVE‑2025‑59718 & CVE‑2025‑59719) mettent en péril la sécurité des produits Fortinet, permettant de contourner l'authentification SAML (Single Sign-On).
- Les attaques débutées le 12 décembre exploitent ces failles pour exfiltrer des fichiers sensibles (schémas réseau et mots de passe).
- Fortinet recommande de désactiver les connexions FortiCloud et de mettre à jour les appareils touchés.
- Les produits affectés incluent FortiOS, FortiProxy, FortiSwitchManager et FortiWeb.  

## Quelles sont les failles détectées ?

Deux vulnérabilités critiques ont été identifiées dans les produits Fortinet, affectant la validation cryptographique des messages SAML utilisés pour l'authentification Single Sign-On (SSO). Ces failles, référencées comme **CVE‑2025‑59718** et **CVE‑2025‑59719**, permettent à des attaquants de contourner les mesures d'authentification. Leur gravité est démontrée par un score CVSS de 9.8/10, ce qui les classe parmi les vulnérabilités hautement critiques.

### CVE‑2025‑59718

Cette faille impacte plusieurs produits Fortinet, notamment FortiOS, FortiProxy et FortiSwitchManager. Elle est due à une validation inadéquate des signatures cryptographiques des messages SAML, permettant à des acteurs malveillants d'exploiter la faiblesse dans le processus d'authentification.

#### Versions concernées :
- **FortiOS** : 7.6.0 à 7.6.3, 7.4.0 à 7.4.8, 7.2.0 à 7.2.1, 7.0.0 à 7.0.17
- **FortiProxy** : 7.6.0 à 7.6.3, 7.4.0 à 7.4.10, 7.2.0 à 7.2.14, 7.0.0 à 7.0.21
- **FortiSwitchManager** : 7.2.0 à 7.2.6, 7.0.0 à 7.0.5

### CVE‑2025‑59719

Cette deuxième faille cible principalement FortiWeb. Elle repose sur une déficience similaire liée à la validation cryptographique des messages SAML, ouvrant la porte à des attaques sur des systèmes critiques.

#### Versions concernées :
- FortiWeb 8.0.0  
- FortiWeb 7.6.0 à 7.5.4  
- FortiWeb 7.4.0 à 7.4.9  

## Produits Fortinet concernés

Les vulnérabilités détectées affectent plusieurs produits clés largement déployés dans les infrastructures réseau critiques. Voici les principales gammes touchées :
- **FortiOS** : système d'exploitation principal utilisé dans les pare-feux Fortinet.  
- **FortiProxy** : solution de proxy réseau destiné à gérer le trafic web et les mécanismes de sécurité.  
- **FortiSwitchManager** : plateforme de gestion des switches Fortinet.  
- **FortiWeb** : solution dédiée à la protection des applications web contre les attaques.  

Ces produits sont souvent utilisés dans des environnements critiques, notamment dans les grandes entreprises et les administrations. Leur compromission pourrait donc entraîner des impacts majeurs sur la sécurité globale des réseaux concernés.

## Impact des attaques en cours

Les chercheurs en cybersécurité de **Arctic Wolf** ont rapporté une exploitation active de ces failles depuis le **12 décembre**. Les cybercriminels ciblent spécifiquement les fichiers de configuration système des appareils Fortinet. Voici les informations sensibles potentiellement exfiltrées :
- Schémas détaillés des réseaux internes.
- Informations sur les dispositifs accessibles depuis Internet.
- Règles de pare-feu définissant les zones de confiance.
- Mots de passe hashés, qui peuvent être déchiffrés pour un accès ultérieur.

En accédant à ces données, des attaquants peuvent :
1. Reconstruire les schémas réseau pour identifier les segments vulnérables.
2. Planifier des intrusions ciblées sur les équipements exposés.
3. Exploiter les mots de passe pour compromettre davantage le système.

L'exploitation active souligne la nécessité d'une réponse rapide afin de limiter l'impact de ces attaques.

## Recommandations de sécurité

Fortinet a publié des recommandations claires pour atténuer les risques associés à ces vulnérabilités. Les principales mesures à prendre incluent :

1. **Désactiver les connexions FortiCloud** : Les fonctionnalités cloud peuvent élargir la surface d'attaque en exposant les appareils connectés.
2. **Mettre à jour les équipements touchés** : Des correctifs sont disponibles pour chaque produit corrigé, visant à renforcer les mécanismes de validation des signatures cryptographiques.

### Correctifs disponibles par produit :
- **FortiOS** : 7.6.4+, 7.4.9+, 7.2.12+, 7.0.18+
- **FortiProxy** : 7.6.4+, 7.4.11+, 7.2.15+, 7.0.22+
- **FortiSwitchManager** : 7.2.7+, 7.0.6+
- **FortiWeb** : 8.0.1+, 7.6.5+, 7.4.10+

Les équipes techniques doivent prioriser ces mises à jour en tenant compte des versions affectées présentes dans leur infrastructure. Il est également conseillé d'effectuer un audit interne afin d'évaluer toute compromission potentielle.

## À retenir

- Ces deux failles critiques exploitent des faiblesses du mécanisme SAML, avec un impact potentiel sur la sécurité globale des systèmes Fortinet.
- L'exploitation active rend d'autant plus urgente l'application des correctifs et la mise hors service temporaire des connexions FortiCloud.
- La mise à jour des appareils et une surveillance accrue sont les axes prioritaires pour minimiser les risques et protéger les infrastructures critiques.

Ces vulnérabilités soulignent l'importance de maintenir des processus de gestion des correctifs rigoureux pour prévenir des intrusions dans des systèmes stratégiques.

[source](https://www.techradar.com/pro/security/fortinet-products-hit-by-further-security-flaws-giving-hackers-access-to-systems-and-more)