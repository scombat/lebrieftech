---
title: "Trois vulnérabilités critiques corrigées par SAP : ce que nous savons"
seoTitle: "Trois vulnérabilités critiques corrigées par SAP : tout ce qu'il faut savoir"
seoDescription: "SAP corrige trois failles critiques dans sa mise à jour de décembre 2025, incluant des risques d'exécution de code à distance et des problématiques de sécurité majeures."
datePublished: Wed Dec 10 2025 14:38:29 GMT+0000 (Coordinated Universal Time)
cuid: cmj046sbh000302ld1gtrdp5v
slug: trois-vulnerabilites-critiques-corrigees-par-sap-decembre-2025
canonical: https://www.techradar.com/pro/security/three-critical-vulnerabilities-patched-by-sap-heres-what-we-know

---

# Trois vulnérabilités critiques corrigées par SAP : ce que nous savons

## TL;DR

- **CVE‑2025‑42880** : Une vulnérabilité critique dans SAP Solution Manager permettant une injection de code et un compromis total du système (gravité : 9.9).
- **CVE‑2025‑55754** : Une faille Apache Tomcat dans SAP Commerce Cloud permettant l'exécution de code à distance dans certaines configurations (gravité : 9.6).
- **CVE‑2025‑42928** : Une faille de désérialisation dans SAP jConnect permettant aux utilisateurs privilégiés de mener des attaques ciblées (gravité : 9.1).

## Contexte et importance des correctifs

SAP, géant des logiciels d'entreprise, est souvent la cible de cyberattaques en raison de son importance stratégique et de sa présence dans de nombreux secteurs. La mise à jour de décembre 2025 vient renforcer la sécurité de ses produits, corrigeant 14 vulnérabilités, dont trois particulièrement graves. Ces failles critiques mettent en danger la confidentialité, l'intégrité et la disponibilité des infrastructures utilisant SAP Solution Manager, SAP Commerce Cloud et SAP jConnect.

La correction de ces vulnérabilités témoigne de la complexité croissante des défis de cybersécurité auxquels les entreprises doivent faire face, surtout pour les environnements utilisant des technologies intégrantes comme celles de SAP.

## Détails des vulnérabilités

### CVE‑2025‑42880 : Injection de code critique

Cette vulnérabilité concerne SAP Solution Manager (version ST 720). Elle résulte d'un manque de validation des entrées dans un module fonctionnel accessible à distance. Les attaquants authentifiés peuvent exploiter cette lacune pour injecter du code malveillant et prendre ainsi un contrôle total du système.

Son impact est considérable, car elle compromet les trois piliers de la sécurité informatique : la confidentialité, l'intégrité et la disponibilité. Les entreprises utilisant cette technologie doivent appliquer la mise à jour de manière urgente pour éviter des compromis catastrophiques.

### CVE‑2025‑55754 : Vulnérabilité Apache Tomcat dans SAP Commerce Cloud

La seconde faille critique liée au composant Apache Tomcat touche SAP Commerce Cloud. L'origine du problème est la neutralisation de séquences de contrôle dans les systèmes Windows prenant en charge les séquences ANSI. Dans de telles configurations, un attaquant pourrait insérer du code malveillant dans les logs pour manipuler l'environnement administratif.

Bien qu'aucun exploit actif n'ait été identifié jusqu'à présent, cette vulnérabilité doit être surveillée attentivement par les administrateurs système, en particulier ceux utilisant SAP Commerce Cloud.

### CVE‑2025‑42928 : Problème de désérialisation dans SAP jConnect

Le troisième point critique affecte jConnect, un composant utilisé pour connecter SAP aux bases de données. La faille repose sur une opération de désérialisation non sécurisée, autorisant des utilisateurs hautement privilégiés à exécuter du code arbitraire. Même si cette vulnérabilité nécessite un accès élevé au système, elle ouvre la porte à des attaques particulièrement dangereuses dans les environnements concernés.

Les utilisateurs de jConnect doivent immédiatement appliquer les correctifs pour limiter ces risques et renforcer leur posture de sécurité.

## Articles pour approfondir

Pour en savoir plus sur ces failles et leur contexte, consultez les articles suivants :

- [Comment se protéger après la correction des failles SAP](https://www.bleepingcomputer.com/news/security/sap-fixes-three-critical-vulnerabilities-across-multiple-products/)
- [Failles critiques dans SAP NetWeaver](https://www.techradar.com/pro/security/sap-netweaver-critical-bug)
- [Danger d'une faille similaire dans Adobe AEM](https://www.techradar.com/pro/security/adobe-aem-exploited)

Ces ressources offrent des perspectives supplémentaires sur les attaques visant des technologies phares.

## Recommandations pour les entreprises

Les entreprises utilisant SAP Solution Manager, SAP Commerce Cloud ou SAP jConnect doivent prendre les mesures suivantes :

1. Appliquez les correctifs fournis par SAP sans attendre, car ils corrigent des failles ayant un impact sévère sur vos systèmes.
2. Surveillez votre infrastructure pour repérer tout signe de compromission ou d'activité inhabituelle.
3. Consultez régulièrement les notes de sécurité SAP pour rester informé des futures vulnérabilités et des solutions proposées.
4. Renforcez les contrôles d'accès pour limiter les risques liés aux utilisateurs privilégiés, particulièrement dans les systèmes touchés par des problèmes de désérialisation.

## À retenir sur les correctifs SAP

La mise à jour de décembre 2025 de SAP marque un rappel poignant de l'importance cruciale des correctifs de sécurité dans les environnements complexes. Les trois vulnérabilités critiques corrigées soulignent la manière dont des failles techniques peuvent conduire à des impacts graves sur les systèmes d'entreprise. Maintenir une veille active sur les mises à jour et implémenter rapidement les correctifs sont des stratégies incontournables pour réduire les risques liés à la cybersécurité dans des solutions comme celles de SAP.

[source](https://www.techradar.com/pro/security/three-critical-vulnerabilities-patched-by-sap-heres-what-we-know)