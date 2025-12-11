---
title: "Attention à la faille WinRAR CVE-2025-6218 exploitée activement"
seoTitle: "Faille critique CVE-2025-6218 dans WinRAR exploitée activement"
seoDescription: "Une faille critique dans WinRAR (CVE-2025-6218), exploitée par des groupes APT, nécessite une mise à jour urgente pour éviter des attaques ciblées."
datePublished: Thu Dec 11 2025 13:33:42 GMT+0000 (Coordinated Universal Time)
cuid: cmj1hbbvj000702js2qey7f0h
slug: faille-critique-cve-2025-6218-winrar-exploitee-activement
canonical: https://thehackernews.com/2025/12/warning-winrar-vulnerability-cve-2025.html

---

# Attention à la faille WinRAR CVE-2025-6218 exploitée activement

## TL;DR

- **Vulnérabilité CVE-2025-6218** : faille critique de type path traversal avec un score CVSS de 7.8 permettant l'exécution de code malveillant.
- **Acteurs malveillants concernés** : GOFFEE, Bitter, Gamaredon exploitent activement cette vulnérabilité.
- **Problème ciblé** : systèmes Windows utilisant des versions de WinRAR antérieures à la 7.12.
- **Impact** : ouverture de fichiers piégés pouvant compromettre le système.
- **Solution** : Mettre à jour WinRAR avant le 30 décembre 2025 pour prévenir les attaques.

## Contexte de la vulnérabilité

WinRAR, un logiciel largement utilisé pour l'archivage et la compression de fichiers, est affecté par une faille critique identifiée comme CVE-2025-6218. Cette vulnérabilité repose sur une traversée de chemin (path traversal) permettant à des attaquants de manipuler le système de fichiers du logiciel et d'exécuter du code malveillant. 

Bien que cette faille ait été corrigée en juin 2025 avec la version 7.12, un grand nombre d’utilisateurs continuent de fonctionner avec des versions antérieures, augmentant le risque d’exploitation. Les systèmes Unix et Android ne sont pas touchés par cette vulnérabilité, mais les systèmes Windows sont directement exposés.

## Exploitations actives

Plusieurs groupes APT exploitent activement la vulnérabilité CVE-2025-6218 dans le cadre de campagnes de cyberattaques ciblées. Voici un aperçu des principaux groupes impliqués et leurs méthodes :

### Campagne GOFFEE

Le groupe GOFFEE combine cette vulnérabilité avec la faille CVE-2025-8088 pour maximiser l’impact de ses attaques, ciblant principalement les organisations russes. La méthode d’exploitation repose sur l’envoi d’archives RAR malveillantes via des campagnes de phishing. Les fichiers infectés sont conçus pour compromettre le système dès leur ouverture.

### Campagne Bitter

Orientés en Asie du Sud, les acteurs malveillants du groupe Bitter exploitent la vulnérabilité en utilisant des fichiers RAR modifiés contenant une charge utile trojan. Ce dernier, écrit en C#, exécute des connexions à des serveurs de commande et de contrôle (C2), permettant le déploiement ou l’extraction de données.

### Campagne Gamaredon

Originaire de Russie, Gamaredon cible les infrastructures gouvernementales et militaires ukrainiennes. Ce groupe utilise des malwares tels que le wiper destructeur GamaWiper, visant à espionner ou à anéantir les systèmes infectés.

## Détails techniques

La vulnérabilité CVE-2025-6218 présente plusieurs caractéristiques importantes :

- **Score CVSS** : 7.8, indiquant un niveau de danger élevé.
- **Type d'attaque** : path traversal, permettant de placer des fichiers dans des répertoires sensibles tels que le dossier Démarrage de Windows.
- **Conditions requises pour l'exploitation** : interaction de l'utilisateur, en ouvrant un fichier ou une archive malveillante.
- **Impact** : exécution de code malveillant au prochain démarrage du système compromise.

La gravité de cette faille réside dans la capacité de l’attaquant à implanter des fichiers dans des emplacements stratégiques, facilitant ainsi les attaques au redémarrage des systèmes affectés.

## Mesures de protection

Les agences fédérales américaines, sous la supervision de la CISA, se sont vues imposer des actions correctives immédiates pour lutter contre cette vulnérabilité. Voici les mesures recommandées :

- **Mettre à jour vers WinRAR 7.12** : cette mise à jour corrige la faille et réduit significativement les risques.
- **Formation des équipes** : sensibiliser les collaborateurs à reconnaître et éviter les tentatives de phishing, qui sont souvent le point d’entrée des exploitations malveillantes.
- **Surveillance proactive** : instaurer des mécanismes pour détecter les signes d’une attaque en analysant les indicateurs de compromission.

## Recommandations finales

Pour prévenir au mieux les attaques exploitant CVE-2025-6218, voici les points clés à retenir :

- **Urgence de la mise à jour** : Les versions antérieures à 7.12 de WinRAR sont directement ciblées par des exploits actifs. Une mise à jour immédiate est indispensable.
- **Attention accrue aux fichiers RAR** : tout fichier reçu, notamment dans un contexte professionnel, doit être vérifié avec soin.
- **Renforcement des politiques internes de cybersécurité** : investir dans la sensibilisation des équipes et la surveillance continue des systèmes est crucial pour prévenir des campagnes APT de grande envergure.

En conclusion, la vulnérabilité CVE-2025-6218 représente un risque sérieux lié aux systèmes Windows, particulièrement face à des acteurs malveillants sophistiqués. Appliquer la mise à jour et adopter des pratiques préventives reste la meilleure approche pour limiter les impacts.

[source](https://thehackernews.com/2025/12/warning-winrar-vulnerability-cve-2025.html)