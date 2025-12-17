---
title: "Analyse approfondie : Une campagne d'hameçonnage via PDF de bons de commande"
seoTitle: "Campagne d'hameçonnage PDF : analyse et conseils de sécurité"
seoDescription: "Analyse d'une attaque d'hameçonnage via PDF de bons de commande. Découvrez les techniques des attaquants et les mesures pour vous protéger."
datePublished: Wed Dec 17 2025 14:09:48 GMT+0000 (Coordinated Universal Time)
cuid: cmja38uq0000202lb96sb7sdd
slug: campagne-hameconnage-pdf-analyse-conseils
canonical: https://www.malwarebytes.com/blog/threat-intel/2025/12/inside-a-purchase-order-pdf-phishing-campaign

---

# Analyse approfondie : Une campagne d'hameçonnage via PDF de bons de commande

## TL;DR

- Des cybercriminels ont utilisé un fichier PDF malveillant se faisant passer pour un bon de commande légitime.
- Ce fichier contenait un lien vers une fausse page de connexion préremplie avec l'adresse e-mail de la cible.
- Les identifiants volés, ainsi que des données techniques et géographiques, étaient relayés à un bot Telegram.
- Les attaquants ont exploité des services d'hébergement réputés comme IONOS Cloud pour augmenter leur crédibilité et contourner les détections.
- Une vigilance accrue et l'utilisation d'outils de sécurité renforcée sont nécessaires pour se prémunir contre ce type de menace.

## Contexte de l'attaque

L'hameçonnage par le biais de documents PDF est une tactique qui gagne en sophistication à mesure que les cybercriminels affinent leurs techniques. Dans cette campagne particulière, les attaquants ont distribué un fichier nommé **"NEW Purchase Order # 52177236.pdf"**, présenté comme un bon de commande classique, mais en réalité conçu pour tromper ses destinataires et subtiliser leurs informations sensibles.

Un client de Malwarebytes a signalé le fichier après qu'il ait été détecté comme malveillant par leurs outils de protection. Bien qu'il paraisse anodin, ce PDF contenait un bouton conduisant à une page de connexion frauduleuse. L'objectif des attaquants était clair : voler des identifiants professionnels et exploiter des systèmes corporatifs en compromettant la sécurité des utilisateurs.

## Méthodes des cybercriminels détaillées

### Étapes principales de l'attaque

1. **Diffusion du fichier PDF** : La campagne commence par l'envoi d'e-mails aux victimes, accompagnés d'un fichier PDF intitulé comme un bon de commande légitime. À première vue, rien ne semble suspect.
   
2. **Lien malveillant intégré** : Le PDF contient un bouton incitant l'utilisateur à "consulter" le bon de commande. En réalité, ce bouton redirige vers un **visualiseur PDF** au moyen d'une URL abondamment longue.

3. **Page de connexion frauduleuse** : L'utilisateur arrive sur une page de connexion factice, où son e-mail, probablement prélevé au préalable par les attaquants, est déjà renseigné. Les informations demandées incluent les identifiants, mais aussi des données secondaires comme :
   - Les caractéristiques du navigateur et du système d'exploitation,
   - Les cookies,
   - La taille d'écran,
   - Les données de géolocalisation.

4. **Collecte et transfert des données** : Une fois les informations saisies, elles sont transmises à un bot Telegram sous contrôle des cybercriminels. Cette méthode permet une collecte rapide et opérationnelle des données sensibles.

### Hébergement et techniques d'évasion

Pour amplifier leur crédibilité et contourner les mécanismes de détection, les attaquants se sont appuyés sur le sous-domaine `ionoscloud.com`, un service hébergé réputé. L'analyse de Malwarebytes a révélé l'utilisation de multiples fichiers PDF malveillants associés à ce domaine.

Les pages d'hameçonnage étaient construites grâce à des modèles automatisés, utilisant un JavaScript obfusqué pour compliquer leur analyse. Une fois le code déchiffré, il est apparu que les attaquants faisaient également appel à des services d'API comme **ipapi**, leur permettant d'enrichir les données volées par des informations géographiques précises.

## Recommandations essentielles pour éviter le phishing

Face à la recrudescence et l'évolution des attaques de phishing, voici quelques pratiques essentielles à adopter :

- **Analysez les pièces jointes** : Ne faites confiance à aucun fichier PDF sans vérifier son origine. Assurez-vous de l'authenticité de l'expéditeur avant ouverture.
- **Examiner les liens intégrés** : Passez votre curseur sur les boutons ou les liens dans les PDF pour inspecter leur URL avant tout clic.
- **Priorisez les domaines légitimes** : Soyez attentif à la structure des adresses web. Les fautes ou anomalies dans l'URL peuvent souvent être révélatrices.
- **Installez des solutions anti-malware** : Des outils comme Malwarebytes offrent une protection en temps réel contre les menaces malveillantes.
- **Filtrer les e-mails entrants** : Les organisations peuvent implémenter des filtres avancés pour identifier et bloquer les e-mails contenant des éléments suspects.

### Une astuce complémentaire :

Testez des outils comme **Malwarebytes Scam Guard**. Ce logiciel compare des captures d'écran pour identifier visuellement les tentatives de phishing, ajoutant une couche innovante de détection.

## Résumé de l'analyse technique

Cette analyse souligne la persistance des cybercriminels à exploiter des formats et des services légitimes pour mener leurs attaques. Le fichier PDF malveillant se fait passer pour un document courant, rendant la tromperie plus crédible. La complexité des scripts et l'utilisation de plateformes réputées comme IONOS Cloud ajoutent une dimension supplémentaire à l'évasion des outils de sécurité.

Les informations volées – allant des identifiants aux données techniques et géographiques – montrent clairement l'étendue des cibles et la sophistication des méthodes. Les liens vers Telegram permettent aux attaquants de gérer efficacement leurs opérations.

## Conclusion sur la sécurité numérique

Les campagnes d'hameçonnage utilisant des fichiers PDF illustrent l'ingéniosité croissante des cybercriminels en matière de tromperie. La frontière entre légitimité et malveillance devient de plus en plus fine, rendant indispensable une vigilance accrue de la part des utilisateurs et des entreprises.

La clé pour contrer ces attaques réside dans la sensibilisation, l'adoption de mesures de sécurité robustes et l'investissement dans des solutions de protection modernes. Chaque utilisateur est un maillon de la chaîne de sécurité. En adoptant des pratiques réfléchies et en se dotant des bons outils, il est possible de réduire significativement les risques et de protéger efficacement les données sensibles.

[source](https://www.malwarebytes.com/blog/threat-intel/2025/12/inside-a-purchase-order-pdf-phishing-campaign)