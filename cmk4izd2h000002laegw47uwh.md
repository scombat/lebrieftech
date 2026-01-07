---
title: "Une campagne de phishing usurpant les communications internes"
seoTitle: "Une campagne de phishing usurpant des messages internes dévoilée"
seoDescription: "Découvrez comment les pirates exploitent des serveurs email mal configurés pour tromper en imitant des communications internes et conduire des attaques BEC."
datePublished: Wed Jan 07 2026 21:23:24 GMT+0000 (Coordinated Universal Time)
cuid: cmk4izd2h000002laegw47uwh
slug: campagne-phishing-usurpation-messages-internes
canonical: https://www.techradar.com/pro/security/this-phishing-campaign-spoofs-internal-messages-heres-what-we-know

---

# Une campagne de phishing usurpant les communications internes

## TL;DR

- Les cybercriminels exploitent des serveurs email mal configurés, contournant les protocoles de sécurité comme SPF, DKIM et DMARC.
- Ces campagnes utilisent des kits tels que Tycoon2FA pour envoyer des emails de phishing imitant des communications internes.
- Les informations volées via ces attaques servent souvent à mener des campagnes de type Business Email Compromise (BEC).
- Ces attaques sont largement diffusées et visent à atteindre un grand nombre de victimes sans cibler spécifiquement.

## Qu’est-ce qu’une campagne de phishing par usurpation ?

Les campagnes de phishing sont un type d’attaque cybercriminelle où des imposteurs utilisent des communications frauduleuses pour tromper les victimes et obtenir des informations personnelles ou sensibles, comme des identifiants de connexion. Une variante particulièrement préoccupante est celle qui exploite des défauts de configuration dans les serveurs email afin de simuler des communications internes légitimes.

Ces attaques tirent parti du fait que les employés ont généralement une confiance accrue envers les messages internes, souvent perçus comme sûrs et vérifiés. En 2025, Microsoft a observé une augmentation notable de ces campagnes, attirant ainsi l’attention sur la nécessité de repenser la sécurisation des communications électroniques dans les entreprises.

## Les exploitations des protocoles de sécurité

### Les failles des protocoles SPF, DKIM et DMARC

Les entreprises s’appuient sur des mécanismes de sécurisation des emails tels que **SPF** (Sender Policy Framework), **DKIM** (DomainKeys Identified Mail) et **DMARC** (Domain-based Message Authentication, Reporting and Conformance) pour vérifier l’authenticité des expéditeurs. Ces protocoles contribuent à empêcher l’envoi d’emails frauduleux ou d’usurpation de domaine. Cependant, leur efficacité dépend fortement d’une configuration correcte.

Dans les environnements où les emails traversent plusieurs points de relais, notamment des fournisseurs tiers ou des serveurs hébergés, des erreurs de configuration sont fréquentes. Cela offre une opportunité aux attaquants de contourner ces contrôles et d’envoyer des emails semblant provenir de domaines internes fiables.

### L’usurpation convaincante des messages

En exploitant ces failles techniques, les cybercriminels parviennent à concevoir des emails qui ressemblent parfaitement à des communications internes. Des messages apparemment légitimes, qu’il s’agisse de notifications de messagerie vocale ou de documents partagés, parviennent ainsi à tromper les employés. Les victimes, en pensant répondre à un collègue ou un supérieur, se montrent moins vigilantes et sont alors amenées à partager des informations sensibles, comme leurs identifiants ou mots de passe.

## Conséquences et dangers des campagnes de phishing

Les campagnes de phishing sont de nature opportuniste et visent à maximiser le nombre de victimes. Une fois les informations d’identification compromises, elles peuvent être exploitées par les attaquants pour orchestrer des attaques secondaires. Parmi celles-ci, les attaques **Business Email Compromise (BEC)** sont particulièrement dévastatrices.

### Le BEC : un impact massif pour les entreprises

Les attaques BEC utilisent les comptes compromis pour tromper les autres employés, clients ou partenaires commerciaux. Les conséquences peuvent être désastreuses, allant de transferts financiers frauduleux à une détérioration de la réputation de l’entreprise. En ciblant directement les opérations internes, ces attaques profitent de la confiance existante pour maximiser leurs impacts financiers.

### Un modèle de campagne peu ciblée

Contrairement à des tentatives de phishing très ciblées, ces campagnes se diffusent largement, avec des emails qui imitent divers types de communications internes, comme :
- Des notifications liées au système téléphonique ou à la messagerie vocale ;
- Des invitations à consulter un **document partagé** via des plateformes courantes ;
- Des communications supposées émaner des **Ressources Humaines** ;
- Des alertes sur l’expiration ou la réinitialisation de mots de passe.

Leur objectif est de maximiser le taux de succès, quitte à sacrifier la précision dans le ciblage des victimes.

## Approche proactive pour la prévention

### Renforcer les configurations des serveurs email

La prévention passe avant tout par une gestion stricte des configurations des serveurs email. Mettre en place des protocoles comme SPF, DKIM et DMARC capable de couvrir tous les systèmes et points de relais est essentiel. Cela implique :
- La surveillance continue des configurations pour détecter les failles.
- L’utilisation d’analyses détaillées pour identifier les modifications suspectes ou non conformes.

### Sensibilisation des collaborateurs

Le facteur humain restant souvent une vulnérabilité majeure, il est indispensable de sensibiliser les employés à ces risques. Les entreprises doivent déployer des programmes réguliers de formation sur la reconnaissance des emails suspects et les bonnes pratiques en matière de sécurité.

### L’adoption d’outils avancés

Enfin, une approche proactive peut inclure le recours à des solutions technologiques avancées, telles que les systèmes d’analyse comportementale. Ces outils permettent de détecter des anomalies dans le trafic email ou des changements dans les habitudes d’envoi des communications internes.

---

Les campagnes de phishing par usurpation des communications internes rappellent l’enjeu croissant de la sécurité email dans un contexte de travail numérique omniprésent. Pour contrer ces menaces, il est crucial d’allier une approche technique robuste à une sensibilisation accrue des acteurs internes.

[source](https://www.techradar.com/pro/security/this-phishing-campaign-spoofs-internal-messages-heres-what-we-know)