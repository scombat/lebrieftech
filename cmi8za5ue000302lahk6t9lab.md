---
title: "Mises à jour critiques de sécurité pour les distributions Linux"
seoTitle: "Mises à jour de sécurité Linux : AlmaLinux, Debian, Ubuntu et autres"
seoDescription: "Découvrez les mises à jour de sécurité critiques publiées par AlmaLinux, Debian, Red Hat, SUSE, Ubuntu et autres distributions GNU/Linux ce vendredi."
datePublished: Fri Nov 21 2025 14:51:22 GMT+0000 (Coordinated Universal Time)
cuid: cmi8za5ue000302lahk6t9lab
slug: mises-a-jour-securite-linux-vendredi
canonical: https://lwn.net/Articles/1047386/

---

# Mises à jour critiques de sécurité pour les distributions Linux

## TL;DR

- Plusieurs correctifs de sécurité critiques ont été publiés ce vendredi pour des distributions Linux majeures.
- AlmaLinux a mis à jour "delve" et "golang". Debian a corrigé "webkit2gtk".
- Oracle a diffusé des correctifs pour "expat" et "thunderbird", tandis que Red Hat a sécurisé son noyau pour EL9 et EL10.
- SUSE, Slackware et Ubuntu ont respectivement ciblé des paquets comme "chromium", "openvpn" et "imagemagick".

## Les mises à jour essentielles des distributions Linux

Les mises à jour de sécurité publiées ce vendredi soulignent l'importance de maintenir vos systèmes Linux à jour. Ces correctifs sont essentiels non seulement pour répondre à des failles de sécurité, mais aussi pour garantir la stabilité de vos infrastructures logicielles.

Voici un aperçu rapide des distributions et des paquets mis à jour :

- **AlmaLinux** (version 9) : delve, golang  
- **Debian** (LTS) : webkit2gtk  
- **Oracle Linux** (OL8) : expat, thunderbird  
- **Red Hat** (EL9, EL10) : kernel  
- **Slackware** : openvpn  
- **SUSE** : chromium, grub2, kernel  
- **Ubuntu** : imagemagick, cups-filters, libcupsfilters  

Ces correctifs touchent un large éventail de composants critiques, allant des bibliothèques système aux services réseau.

## Pourquoi ces mises à jour sont importantes pour votre système

Les failles de sécurité couvertes par ces mises à jour peuvent être exploitées pour compromettre des systèmes. Que vous soyez un administrateur système ou un développeur, appliquer ces correctifs est une obligation pour prévenir les attaques.

Les entreprises et les infrastructures critiques qui utilisent ces distributions Linux ont beaucoup à perdre si ces vulnérabilités sont exploitées : vols de données, interruptions de service, voire compromission totale de systèmes.

Il est crucial de noter que certaines mises à jour peuvent avoir des impacts sur des configurations complexes. Leur application doit donc être planifiée avec des tests en amont pour éviter toute incompatibilité.

## Détails des correctifs par distribution

### AlmaLinux
- **Advisory ID** : ALSA‑2025:21815  
- **Version concernée** : AlmaLinux 9  
- **Paquets corrigés** : delve, golang  
- **Date de publication** : 20 novembre 2025  

### Debian
- **Advisory ID** : DLA‑4375‑1  
- **Version concernée** : Distribution LTS de Debian  
- **Paquet corrigé** : webkit2gtk  
- **Date de publication** : 20 novembre 2025  

### Oracle
- **Advisory ID** : ELSA‑2025‑21776, ELSA‑2025‑21881  
- **Version concernée** : Oracle Linux 8 (OL8)  
- **Paquets corrigés** : expat, thunderbird  
- **Dates de publication** : 20–21 novembre 2025  

### Red Hat
- **Advisory ID** : RHSA‑2025:20095‑01, RHSA‑2025:20518‑01  
- **Versions concernées** : Red Hat Enterprise Linux 9 et 10  
- **Paquet corrigé** : noyau  
- **Date de publication** : 21 novembre 2025  

### Slackware
- **Advisory ID** : SSA:2025‑323‑01  
- **Paquet corrigé** : openvpn  
- **Date de publication** : 19 novembre 2025  

### SUSE
- **Advisory ID** : openSUSE‑SU‑2025:0434‑1, SUSE‑SU‑2025:4152‑1  
- **Paquets corrigés** : chromium, grub2, kernel  
- **Dates de publication** : 20–21 novembre 2025  

### Ubuntu
- **Advisory ID** : USN‑7878‑1, USN‑7876‑1, USN‑7877‑1  
- **Versions concernées** : 14.04, 16.04, 18.04, 20.04, 22.04, 24.04, 25.10  
- **Paquets corrigés** : cups‑filters, imagemagick, libcupsfilters  
- **Date de publication** : 20 novembre 2025  

Ces distributions ont ciblé des logiciels essentiels pour le fonctionnement quotidien des serveurs et des postes de travail. Par exemple, "imagemagick" est fréquemment utilisé pour le traitement des images, tandis que "thunderbird" est plébiscité pour la communication via email.

## Risques d'une application tardive ou négligée

Ne pas appliquer rapidement ces correctifs peut exposer vos systèmes à des attaques graves. Les cybermenaces actuelles exploitent de plus en plus rapidement les vulnérabilités découvertes. Les administrateurs systèmes doivent donc être réactifs pour protéger leurs infrastructures.

Cependant, une mise à jour précipitée sans vérification préalable peut également entraîner des dysfonctionnements dans des environnements complexes. Tester les correctifs dans un environnement de staging avant leur déploiement en production est une mesure recommandée pour prévenir des interruptions.

Enfin, pour garder une infrastructure saine et résiliente face aux attaques potentielles, il est important d'inclure la gestion des mises à jour de sécurité dans un processus continu de maintenance.

---

En conclusion, ces mises à jour illustrent l'effort concerté de l'écosystème Linux pour renforcer la sécurité de ses utilisateurs. Qu'il s'agisse de correctifs affectant des paquets critiques ou de failles du noyau, leur déploiement rapide est essentiel pour garantir le bon fonctionnement de vos systèmes. Aucun correctif ne doit être négligé : la sécurité de vos infrastructures en dépend.

[source](https://lwn.net/Articles/1047386/)