---
title: "Mise à jour finale : Fin du support pour le noyau Linux 5.4"
seoTitle: "Mise à jour finale du noyau Linux 5.4 : fin de support et risques de sécurité"
seoDescription: "Le noyau Linux 5.4 est désormais en fin de vie. Découvrez pourquoi cette version ne doit plus être utilisée et les alternatives disponibles."
datePublished: Wed Dec 03 2025 14:25:13 GMT+0000 (Coordinated Universal Time)
cuid: cmiq3mr6u000602ij3qos2wkx
slug: mise-a-jour-finale-noyau-linux-5-4
canonical: https://lwn.net/Articles/1049059/

---

# Mise à jour finale : Fin du support pour le noyau Linux 5.4

## TL;DR

- La version 5.4.302 est la dernière mise à jour du noyau Linux 5.4.
- Ce noyau est officiellement marqué comme "fin de vie" (EOL).
- 1539 vulnérabilités (CVE) non corrigées exposent ces systèmes à des risques majeurs de sécurité.
- Greg Kroah-Hartman encourage les utilisateurs à migrer vers des versions maintenues du noyau Linux.
- Les alternatives incluent des versions LTS ou des services professionnels de maintenance.

## Introduction à la mise à jour finale

Le noyau Linux est une pièce maîtresse des systèmes d'exploitation modernes, utilisée dans des contextes variés, allant des serveurs aux infrastructures embarquées. Le 3 décembre 2025, la version 5.4.302 du noyau Linux a été annoncée comme étant la dernière mise à jour de cette branche, marquant officiellement la fin de son support. 

Greg Kroah-Hartman, mainteneur principal du noyau stable, a souligné que cette version ne devrait plus être utilisée. Elle compte actuellement 1539 vulnérabilités non corrigées (CVE) et continuera à être une cible potentielle au fur et à mesure que de nouvelles failles seront découvertes.

L'arrêt du support pour le noyau 5.4 représente un moment critique pour les administrateurs système et les ingénieurs. Utilisée dans plusieurs distributions à support à long terme, elle exige désormais une migration urgente vers des versions plus sûres et activement maintenues.

## Les risques de sécurité liés au noyau 5.4

### Vulnérabilités non corrigées

La version 5.4.302 du noyau comporte un nombre significatif de failles de sécurité qui ne seront pas corrigées. Greg Kroah-Hartman a partagé une liste détaillée des CVE non corrigées, accessible via [ce lien](https://lwn.net/ml/all/2025120358-skating-outage-7c61@gregkh/). Ces 1539 vulnérabilités impliquent des risques élevés :

- **Exploitation des systèmes** : Les failles ouvertes peuvent être activement exploitées par des attaquants.
- **Propagation de logiciels malveillants** : Les systèmes vulnérables sont particulièrement exposés aux infections.
- **Compromission des données** : L'absence de patch augmente les risques pour les environnements sensibles.

### Augmentation des risques avec le temps

Il est important de noter que le nombre de vulnérabilités continuera d'augmenter, accentuant les menaces. Les systèmes utilisant ce noyau deviennent des cibles particulièrement attractives pour des cyberattaques, surtout dans des secteurs critiques comme les infrastructures cloud, les environnements industriels ou les services financiers.

### Citation notable

Greg Kroah-Hartman a déclaré :  
*"Il ne devrait être utilisé par personne, plus jamais."*  
Cette mise en garde souligne l'urgence de migrer vers une version plus récente.

## Alternatives et migrations recommandées

Les utilisateurs du noyau Linux 5.4 doivent envisager sans délai des solutions de remplacement. Voici quelques options clés :

### Versions LTS et noyaux activement maintenus

Les versions Long Term Support (LTS) du noyau Linux sont conçues pour offrir une maintenance sur plusieurs années. Elles constituent le choix privilégié pour les systèmes nécessitant des mises à jour régulières sans modifications trop fréquentes :

- **Exemple** : Migrer d'une distribution utilisant le noyau 5.4 (Ubuntu 18.04) vers une version plus récente comme Ubuntu 20.04 ou 22.04, équipées d'un noyau maintenu.
- **Avantages** : Corrections de sécurité, nouvelles fonctionnalités, performances accrues.

### Support professionnel

Dans les cas où une migration immédiate est difficile, certains fournisseurs proposent des services de maintenance de sécurité pour les noyaux marqués comme finis. Ces solutions permettent de prolonger le support mais peuvent être coûteuses et limitées en termes de réactivité face à de nouvelles vulnérabilités.

### Audit des environnements et mises à niveau matériels

Pour les systèmes embarqués ou les infrastructures physiques, il peut être nécessaire d'évaluer la compatibilité matérielle avec les nouvelles versions du noyau. Les ingénieurs sont encouragés à adopter des bonnes pratiques comme le suivi des annonces officielles de fin de vie et la réalisation régulière d'audits des dépendances logicielles.

#### Exemple concret

1. **Audit de compatibilité** : Identifier les périphériques ou logiciels qui peuvent poser problème avec une version de noyau plus récente.
2. **Planification** : Mettre en place un calendrier de migration pour minimiser les interruptions.
3. **Tests en environnement pilote** : Tester une version LTS dans un environnement isolé avant le déploiement.

## Conclusion

La publication du noyau Linux 5.4.302 marque la fin officielle de la branche 5.4, avec des implications majeures pour la sécurité et la stabilité des systèmes qui reposent sur cette version. Les utilisateurs sont fortement incités à adopter des versions maintenues ou à explorer des alternatives comme le soutien professionnel en cas de dépendances critiques. 

En agissant rapidement, les organisations peuvent réduire leur exposition aux risques sécuritaires tout en assurant la continuité et l'efficacité de leurs systèmes informatiques.

[source](https://lwn.net/Articles/1049059/)