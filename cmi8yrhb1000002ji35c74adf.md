---
title: "Les données clients Salesforce exposées par l’incident Gainsight"
seoTitle: "Incident Gainsight : des données Salesforce exposées"
seoDescription: "Salesforce confirme un incident avec Gainsight ayant compromis des données sensibles de clients. Découvrez les enjeux de cet événement et sa gestion."
datePublished: Fri Nov 21 2025 14:36:50 GMT+0000 (Coordinated Universal Time)
cuid: cmi8yrhb1000002ji35c74adf
slug: incident-gainsight-donnees-salesforce-exposees
canonical: https://www.techradar.com/pro/security/salesforce-says-customer-data-may-be-exposed-in-gainsight-incident-unusual-activity-being-probed

---

# Les données clients Salesforce exposées par l’incident Gainsight

## TL;DR

- Les applications développées par Gainsight ont permis un accès non autorisé aux données de certains utilisateurs Salesforce.  
- Un précédent piratage de Salesloft en août 2025 a conduit au vol de tokens OAuth, désormais exploités dans cet incident.  
- Le groupe ShinyHunters revendique l’attaque et pointe une exploitation de secrets volés.  
- Les données compromises incluent noms, emails, numéros de téléphone, informations de licence et contenu des dossiers de support.  
- Salesforce a révoqué les tokens associés et suspendu les applications concernées pour limiter les dommages.  

## Contexte de l’incident Gainsight

L’interconnexion croissante entre applications et services tiers représente à la fois un atout technologique et une faille potentielle en termes de sécurité. Cet incident implique Gainsight, une entreprise spécialisée dans les solutions "Customer Success" qui développe des outils fortement intégrés à Salesforce via l’utilisation d’API.  

En août 2025, un incident de sécurité chez Salesloft a permis le vol de tokens OAuth. Ces jetons d’autorisation donnent un accès programmatique aux données interconnectées, et leur compromission a ouvert la voie à une autre attaque. Cette fois, Gainsight est au cœur de l’intrusion, causant une possible exposition de données sensibles appartenant aux clients Salesforce.  

Ce cas reflète une chaîne de vulnérabilités, où la compromission initiale d’un acteur conduit à des conséquences en cascade au sein d’autres systèmes dépendants.  

## Détails techniques de l’attaque

### Déroulement de l’intrusion
Salesforce a découvert une activité suspecte dans des applications publiées par Gainsight et connectées à sa plateforme via des API OAuth. Ces applications offrent des automatismes pour faciliter la gestion des relations clients après la vente. Cependant, elles ont également servi de canal pour une attaque ciblée.  

Suite à leur enquête, Salesforce a confirmé que certains clients avaient subi des accès non autorisés à leurs données sensibles. Apparemment, les assaillants auraient utilisé des secrets volés lors du piratage précédent de Salesloft pour s’infiltrer dans les services proposés par Gainsight.  

### Données compromises
L’attaque a débouché sur le vol de plusieurs types d’informations, notamment :  
- **Données de contact** : noms, adresses email et numéros de téléphone.  
- **Détails de licence** : informations sur les contrats d’utilisation.  
- **Informations géographiques** : régions et emplacements des utilisateurs.  
- **Données liées au support** : contenu des tickets et dossiers d’assistance client.  

Ces informations, bien que variées, peuvent être stratégiquement utilisées dans des cyberattaques ciblées, notamment via du phishing ou du spear phishing contre les clients concernés.  

### Le rôle du groupe ShinyHunters
Le groupe ShinyHunters a revendiqué l’attaque, confirmant qu’il a exploité les tokens OAuth compromis précédemment. Connu pour orchestrer des attaques d’envergure contre des entreprises technologiques, ShinyHunters illustre ici comment des failles de sécurité récurrentes dans des systèmes tiers peuvent être enchaînées pour causer des incidents majeurs à très large échelle.  

## Conséquences pour les clients Salesforce

Les entreprises affectées par cette brèche doivent non seulement gérer l’impact direct des données volées, mais également composer avec les dommages indirects comme la perte de confiance des clients.  

L’exposition de données sensibles a plusieurs implications :  
- **Atteinte à la réputation** : Les partenaires commerciaux et utilisateurs finaux pourraient devenir réticents envers les solutions hébergées par des tiers, augmentant potentiellement les pertes financières.  
- **Exploitation des données compromises** : Les informations volées, telles que les adresses e-mail et les numéros de téléphone, sont souvent utilisées dans le cadre de cyberattaques ultérieures, notamment des campagnes de phishing sophistiquées.  
- **Conformité réglementaire** : Les entreprises impactées pourraient être contraintes de déclarer l’incident auprès des autorités compétentes, avec des risques de sanctions si les protocoles de protection des données ne respectaient pas les réglementations en vigueur, telles que le RGPD.  

## Réactions de Salesforce et mesures préventives

Salesforce n’a pas tardé à réagir dès que l’intrusion a été détectée :  
- Tous les tokens OAuth actifs associés à Gainsight ont été immédiatement révoqués.  
- Les applications problématiques ont été temporairement supprimées de leur marketplace, l’AppExchange.  
- Les clients potentiellement affectés ont été informés de la situation et des mesures de mitigation.  

Malgré cette réponse rapide, Salesforce a confirmé qu’aucune faille interne à sa plateforme n’est à l’origine de l’incident. En d’autres termes, le problème provient exclusivement des connexions tierces activées par l’intégration de Gainsight.  

Par ailleurs, Salesforce rappelle l'importance d'établir des processus de sécurité robustes autour de l'usage des tokens OAuth et de surveiller activement les activités inhabituelles dans leurs intégrations externes.  

## Pourquoi cet incident est crucial pour la sécurité des données ?

Cet événement met en lumière plusieurs points critiques pour la sécurité des systèmes interconnectés :  

1. **Vulnérabilités systémiques des connexions tierces** : L’incident Gainsight montre à quel point une faille dans un service peut se propager et affecter tous les systèmes qui en dépendent. Un seul maillon faible suffit à compromettre l’intégrité de toute une chaîne technologique.  

2. **Importance des tokens OAuth** : L’affaire illustre les risques associés aux autorisations OAuth. Ces jetons accordent des privilèges très élevés pour interagir avec les systèmes sensibles, et leur compromission peut être dévastatrice. Un audit rigoureux et des paramètres d’expiration serrés sont cruciaux pour réduire les risques.  

3. **Sensibilisation des entreprises** : Les entreprises doivent comprendre les implications de leurs relations avec des fournisseurs tiers et veiller à l’intégration sécurisée de leurs services, au-delà de la simple confiance accordée à ces partenaires.  

4. **Réactivité en cas d’incident** : Bien qu’initialement déstabilisant, l’exemple de Salesforce montre comment une réponse rapide, accompagnée d’une communication ouverte, peut limiter les dégâts.

En lieu et place des connexions non surveillées, un effort collectif vers une adoption plus massive des bonnes pratiques en gestion des accès pourrait réduire l’ampleur de ce type de menaces dans le futur.  

---

> **FAQ :**  
> **Qu’est-ce que Salesforce a révélé concernant cet incident ?**  
> Salesforce a révélé que des applications de Gainsight auraient permis un accès non autorisé aux données de clients, potentiellement liées au piratage de Salesloft.  
>  
> **Quel est le rôle du groupe ShinyHunters dans cet incident ?**  
> ShinyHunters aurait exploité des tokens OAuth compromis lors du précédent piratage de Salesloft pour infiltrer des applications Gainsight.

[source](https://www.techradar.com/pro/security/salesforce-says-customer-data-may-be-exposed-in-gainsight-incident-unusual-activity-being-probed)