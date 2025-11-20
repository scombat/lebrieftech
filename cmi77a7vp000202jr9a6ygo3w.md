---
title: "Eternidade Stealer : Un ver Python exploitant WhatsApp au Brésil"
seoTitle: "Eternidade Stealer : Analyse d'un ver Python ciblant WhatsApp au Brésil"
seoDescription: "Découvrez comment Eternidade Stealer, un cheval de Troie bancaire, utilise WhatsApp et des scripts Python pour cibler les utilisateurs brésiliens. Conseils pour se protéger."
datePublished: Thu Nov 20 2025 08:59:49 GMT+0000 (Coordinated Universal Time)
cuid: cmi77a7vp000202jr9a6ygo3w
slug: eternidade-stealer-ver-whatsapp-python-bresil
canonical: https://thehackernews.com/2025/11/python-based-whatsapp-worm-spreads.html

---

# Eternidade Stealer : Un ver Python exploitant WhatsApp au Brésil

La cybersécurité fait face à une nouvelle menace majeure au Brésil où l'application WhatsApp, omniprésente, devient l'outil de propagation d'un malware sophistiqué. Baptisé **Eternidade Stealer**, ce cheval de Troie s'appuie sur un script Python pour infecter les utilisateurs et collecter des données bancaires et des identifiants, avec une propagation facilitée par des techniques avancées de social engineering.

## Un nouveau mode de propagation des malwares

L'innovation majeure de cette campagne réside dans son utilisation stratégique de WhatsApp pour diffuser le malware. Exploitant la confiance des utilisateurs envers leurs contacts, Eternidade Stealer détourne les comptes infectés pour distribuer des pièces jointes malveillantes contenant le cheval de Troie. 

Cette méthode n'est pas sans précédent : une campagne similaire appelée **Water Saci** avait déjà utilisé WhatsApp pour propager d'autres malwares, mais sans le niveau de sophistication observé ici. Désormais, les attaquants misent sur des scripts Python et des outils comme **WPPConnect**, un projet open-source, pour automatiser entièrement ces envois. Contrairement aux attaques classiques, les groupes et comptes professionnels sont délibérément exclus, renforçant ainsi la crédibilité des messages envoyés.

Cette évolution illustre un changement important dans les modes opératoires des attaquants, passant des scripts PowerShell à des techniques plus modernes et personnalisables.

## Les étapes techniques de l'infection

### Propagation via WhatsApp

Une fois un appareil infecté, Eternidade Stealer commence par extraire les informations liées aux contacts WhatsApp de la victime, notamment les numéros de téléphone, noms et statuts. Ensuite, il envoie un message adapté, avec une pièce jointe malveillante, à ces contacts. Cette personnalisation des messages accroît les chances que les destinataires les ouvrent, contribuant ainsi à la propagation en chaîne.

L'intégration de **WPPConnect** facilite cette exploitation automatisée, permettant au malware d'utiliser l'infrastructure de WhatsApp sans nécessiter l'intervention humaine active. Cela évite également les envois vers des groupes ou des contextes professionnels, ce qui pourrait alerter prématurément les cibles.

### Installation et exécution du malware

Une étape critique intervient lors de l’installation. Le malware est diffusé sous forme d'un fichier MSI (Microsoft Installer) et adopte une approche intelligente pour limiter les infections hors de sa cible géographique principale. Si les paramètres linguistiques du système de l'utilisateur ne sont pas réglés sur "Portuguese-Brazil", l'installation est simplement abandonnée.

En cas de succès, le malware s'infiltre davantage dans le système en injectant son code dans un processus légitime, comme `svchost.exe`. Cette technique limite les chances de détection par des logiciels de sécurité.

### Fonctionnalités de vol de données

Eternidade Stealer se distingue par son ciblage précis des données sensibles. Il surveille en permanence les activités de l'utilisateur et n’agit que lorsque des applications spécifiques ou des pages pertinentes sont ouvertes, notamment :

- Des banques en ligne.
- Des plateformes de paiement.
- Des portefeuilles de cryptomonnaie comme Binance, Coinbase et MetaMask.

Cette approche ciblée réduit considérablement sa visibilité puisqu'il ne collecte pas des données en permanence, mais seulement lors de son activation contextuelle.

### Infrastructure de Command-Control (C2)

Pour maintenir son contrôle, le malware utilise une infrastructure de Command-Control (C2) ingénieuse. Les serveurs C2, définis dynamiquement, sont récupérés depuis une boîte mail utilisant le protocole IMAP, hébergée chez **terra.com.br**. Si cette approche échoue, un ensemble d'adresses C2 codées en dur sert de solution de repli.

Les attaquants disposent également d'une interface de gestion avancée qui leur permet de surveiller leurs victimes, de géolocaliser les appareils infectés, et d'exécuter des commandes à distance. Quelques exemples d'instructions incluent :

- `<|OK|>` : Collecte d'informations système.
- `<|PING|>` : Identification de la fenêtre active.
- `<|PedidoSenhas|>` : Déploiement d'un vol d'identifiants.

## Les risques et impacts de cette campagne

Bien qu'actuellement concentrée au Brésil, cette campagne suscite de grandes inquiétudes à l'international. L'utilisation de WhatsApp comme vecteur principal, combinée à la flexibilité de son infrastructure C2, ouvre la porte à une propagation rapide à d'autres régions du monde.

L'impact principal des attaques repose sur :

- Le vol d'informations bancaires et d'identifiants sensibles.
- La compromission des portefeuilles de cryptomonnaie.
- L'effet boule de neige engendré par la propagation sur les contacts WhatsApp.

L'adaptabilité de ce type de malware impose une vigilance accrue, car les techniques utilisées peuvent être rapidement répliquées ou modifiées pour attaquer d'autres cibles.

## Conseils pour se protéger contre Eternidade Stealer

1. **Soyez attentif aux activités anormales sur WhatsApp** : des messages inhabituels de la part de contacts connus doivent immédiatement éveiller votre méfiance.
2. **Bloquez les fichiers MSI par défaut** : dans un contexte d'entreprise ou personnel, configurez vos systèmes pour que les fichiers MSI nécessitent une validation manuelle avant exécution.
3. **Surveillez les indicateurs de compromission (IOCs)** : restez informé des derniers détails techniques sur Eternidade Stealer et configurez vos outils de sécurité pour détecter les comportements suspects liés à ce malware.
4. **Renforcez les formations sur le social engineering** : sensibilisez vos équipes et vos proches aux techniques utilisées pour manipuler et tromper les utilisateurs via des plateformes de messagerie.

## À retenir

Eternidade Stealer illustre la modernisation des malwares ciblant des applications populaires comme WhatsApp. En combinant social engineering, scripts Python et une infrastructure C2 innovante, il représente une menace sérieuse, en particulier dans des pays où WhatsApp est un outil de communication dominant. Protéger vos appareils et adopter des pratiques de sécurité solides reste la meilleure défense contre ce type d'attaque.

[source](https://thehackernews.com/2025/11/python-based-whatsapp-worm-spreads.html)