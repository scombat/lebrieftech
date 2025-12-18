---
title: "Cisco alerte sur une vulnérabilité zero-day exploitée par des hackers chinois"
seoTitle: "Cisco alerte sur une faille zero-day critique exploitée par des hackers chinois"
seoDescription: "Cisco signale une vulnérabilité zero-day critique dans AsyncOS exploitée par des hackers chinois. Aucune mise à jour corrective n'est encore disponible."
datePublished: Thu Dec 18 2025 13:24:46 GMT+0000 (Coordinated Universal Time)
cuid: cmjbh2se5000802jlh8781qpv
slug: cisco-faille-zero-day-hackers-chinois
canonical: https://www.techradar.com/pro/security/cisco-says-chinese-hackers-are-exploiting-its-customers-with-a-new-zero-day

---

# Cisco alerte sur une vulnérabilité zero-day exploitée par des hackers chinois

## TL;DR

- Cisco a identifié une vulnérabilité zero-day affectant son logiciel AsyncOS, exploité activement par des hackers chinois.
- La faille permet d’obtenir des privilèges root sur des systèmes où la fonctionnalité Spam Quarantine est activée.
- Aucun correctif n’est disponible ; Cisco recommande une réinitialisation complète des appareils affectés.
- Cette attaque met en lumière les risques accrus de menaces étatiques dans le domaine de la cybersécurité.

## Contexte de la vulnérabilité

Découverte le 10 décembre, cette faille critique a été confirmée par Cisco dans une annonce officielle. Elle touche le logiciel AsyncOS, utilisé dans les solutions Cisco Secure Email Gateway et Cisco Secure Email and Web Manager. 

La vulnérabilité est directement associée à la fonctionnalité **Spam Quarantine**, qui est souvent désactivée par défaut mais, une fois activée, expose les systèmes à des attaques potentiellement dévastatrices. Les conséquences de cette faille sont particulièrement préoccupantes pour des entreprises de toutes tailles, ouvrant la porte à une prise de contrôle complète des serveurs affectés.

## Impact de la faille AsyncOS

### Étendue des risques

La vulnérabilité affecte aussi bien les appliances physiques que virtuelles, mais uniquement si la fonctionnalité Spam Quarantine est activée et accessible depuis Internet. Les attaquants exploitent cette faiblesse pour exécuter des commandes avec privilèges **root**, leur donnant un contrôle total sur les systèmes affectés.

### Acteurs en cause

Bien qu’aucune revendication officielle n’ait été faite, des chercheurs en cybersécurité estiment que cette campagne pourrait être soutenue par un acteur étatique chinois. Cela souligne une tendance inquiétante dans la géopolitique de la cybersécurité, où les attaques commanditées par des États visent des infrastructures critiques.

## Recommandations de Cisco

À ce stade, Cisco n’a pas publié de correctif pour cette vulnérabilité zero-day. L’entreprise propose toutefois des mesures d’urgence pour limiter les risques :

1. **Réinitialisation complète des appareils compromis** : cette étape vise à éliminer tout moyen de persistance utilisé par les attaquants.
2. **Assistance via le TAC (Technical Assistance Center)** : Cisco recommande aux organisations touchées de solliciter l’assistance technique pour confirmer toute activité suspecte et, le cas échéant, reconstruire les configurations de leurs appareils.

Ces recommandations sont les seules actions actuellement possibles pour sécuriser les systèmes jusqu’à l’arrivée d’une mise à jour corrective.

## Implications pour la cybersécurité

### Risques pour les grandes entreprises

Les entreprises avec une infrastructure complexe et de grande envergure sont particulièrement vulnérables. Une compromission pourrait mener à des perturbations majeures des communications internes ou à des atteintes graves à la confidentialité des données.

### Menaces géopolitiques

La possibilité que des hackers étatiques chinois soient impliqués met en lumière la montée des tensions dans le domaine de la cybersécurité. Les attaques commanditées par des gouvernements perturbent à la fois les secteurs privés et publics, renforçant l’urgence d’investir dans des stratégies de défense solides et proactives.

## Points à considérer

- L’absence de correctif immédiat laisse une fenêtre ouverte aux attaquants pour exploiter cette vulnérabilité, en particulier dans les environnements où Spam Quarantine est activée.
- Les entreprises doivent impérativement évaluer leurs configurations actuelles et désactiver toute fonctionnalité inutile ou exposée en ligne.
- Cette faille souligne l’importance des audits réguliers dans le maintien d’une posture de sécurité robuste.

## À retenir

La vulnérabilité zero-day d’AsyncOS représente une menace grave et immédiate pour les organisations utilisant les solutions concernées. Avec aucun correctif disponible, le seul moyen de sécuriser les systèmes est de procéder à une réinitialisation complète. Cette attaque attribuée à des hackers chinois met en évidence les défis complexes auxquels les entreprises doivent faire face pour protéger leurs infrastructures contre des menaces étatiques croissantes.

[source](https://www.techradar.com/pro/security/cisco-says-chinese-hackers-are-exploiting-its-customers-with-a-new-zero-day)