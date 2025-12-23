---
title: "Une attaque inquiétante sur WhatsApp vole messages et comptes utilisateurs"
seoTitle: "Une attaque WhatsApp inquiétante : messages et comptes volés via un malware npm"
seoDescription: "Découvrez une attaque WhatsApp utilisant un malware npm pour voler des messages et comptes. Conseils pour rester protégé."
datePublished: Tue Dec 23 2025 21:21:37 GMT+0000 (Coordinated Universal Time)
cuid: cmjj3baiv000102l1ay55f3oc
slug: attaque-whatsapp-malware-npm-vol-comptes
canonical: https://www.techradar.com/pro/security/worrying-whatsapp-attack-can-steal-messages-and-even-accounts-heres-how-to-stay-safe-from-poisoned-attack

---

# Une attaque inquiétante sur WhatsApp vole messages et comptes utilisateurs

## TL;DR

- Un package npm appelé "lotusbail" a permis de compromettre des comptes WhatsApp et de voler des données sensibles telles que messages, contacts et médias.
- Ce malware interceptait les communications et conservait un accès persistant aux comptes via l’appairage des appareils.
- Plus de 56 000 téléchargements ont été rapportés avant sa suppression de la plateforme.
- Les développeurs doivent redoubler de vigilance lors du téléchargement et de l’intégration de dépendances externes.

## Fonctionnement du malware

### Code dissimulé et interception des données

"Lotusbail" se présentait comme une version légitime du projet **WhiskeySockets Baileys**, bien connu des développeurs travaillant avec WhatsApp. Cependant, ce package contenait un wrapper malveillant conçu pour intercepter toutes les communications entre l'utilisateur et l'application WhatsApp. 

Grâce à cette dissimulation, le malware permettait aux attaquants de capter les informations sensibles telles que :
- Les identifiants et mécanismes d’authentification.
- Les messages échangés sur WhatsApp.
- Les contacts enregistrés ainsi que les fichiers multimédias partagés par les utilisateurs.

### Appairage persistant et contrôle des comptes

L’un des aspects les plus inquiétants de l’attaque était sa capacité à associer un appareil contrôlé par l’attaquant au compte de la victime via la fonctionnalité d’appairage de WhatsApp. Même après la suppression de "lotusbail" par l’utilisateur, cet accès malveillant restait actif, obligeant la victime à agir manuellement pour révoquer le lien en passant par les paramètres de gestion des appareils.

### Une attaque de grande ampleur

Le package "lotusbail" est resté actif sur le registre npm pendant environ six mois. Pendant cette période, il a été téléchargé plus de 56 000 fois, affectant un grand nombre de développeurs et, potentiellement, leurs utilisateurs finaux. Ce cas met en lumière la vulnérabilité des chaînes d’approvisionnement logicielle, notamment dans l’écosystème des plateformes de packages open-source comme npm.

## Précautions pour les développeurs

Face à des attaques ciblant l’intégration de dépendances, les développeurs doivent adopter des pratiques de sécurité rigoureuses pour protéger leurs projets et leurs utilisateurs. Voici quelques recommandations :

1. **Scruter la provenance des packages** : Téléchargez uniquement des bibliothèques depuis des sources officielles et vérifiez toujours la légitimité des auteurs et des dépôts. Les fourchettes (forks) de projets renommés peuvent dissimuler des intentions malveillantes.
   
2. **Configurer une surveillance proactive** : Dans le cadre de votre utilisation de WhatsApp, vérifiez régulièrement si des appareils non autorisés sont liés à vos comptes. Révoquez immédiatement tout accès suspect.

3. **Comprendre les attaques sur les chaînes d'approvisionnement** : Familiarisez-vous avec les techniques comme le typosquatting et l’exploitation de forks compromis, qui ciblent souvent les écosystèmes de dépendances populaires.

L’importance de sensibiliser les équipes de développement à ces risques ne peut être sous-estimée. Il est également recommandé d’incorporer des outils d’analyse automatisés pour détecter les anomalies dans les packages avant leur intégration.

## Les dangers des forks npm malveillants

npm, l’un des registres les plus utilisés pour les bibliothèques JavaScript, est malheureusement un terrain propice pour les acteurs malveillants. Ces derniers exploitent des tactiques variées, parmi lesquelles :

- **Typosquatting** : Créer des noms de packages ressemblant à des projets connus pour tromper les développeurs.
- **Injection malveillante dans des forks** : Modifier un projet populaire pour y insérer du code nocif et le publier comme un fork légitime.

En raison de sa large adoption dans l’industrie du développement web et backend, npm constitue une cible privilégiée, ce qui soulève des préoccupations majeures pour la sécurité et la fiabilité des logiciels construits sur cette plateforme.

## À retenir

Les packages open-source facilitent le développement, mais ils comportent aussi leur part de risques, notamment lorsqu’ils sont malveillants. L’attaque via le malware "lotusbail" montre qu’une vigilance accrue est indispensable. L’intégration de dépendances non vérifiées peut entraîner des conséquences graves, allant du vol de données utilisateurs à l'usurpation de comptes sensibles.

La sécurité des chaînes d’approvisionnement logicielle doit être une priorité. En renforçant les contrôles sur les sources des dépendances et en surveillant régulièrement les activités suspectes, développeurs et entreprises peuvent réduire leur exposition à des risques inattendus liés à l’utilisation de solutions open-source.

[source](https://www.techradar.com/pro/security/worrying-whatsapp-attack-can-steal-messages-and-even-accounts-heres-how-to-stay-safe-from-poisoned-attack)