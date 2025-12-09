---
title: "Matrix vs Signal Protocol : Pourquoi Guardyn a choisi de ne pas fédérer"
seoTitle: "Matrix vs Signal Protocol : Comprendre les choix architecturaux de Guardyn pour ne pas fédérer"
seoDescription: "Découverte des raisons pour lesquelles Guardyn, une plateforme axée sur la confidentialité, a choisi des architectures OpenMLS et non Matrix. Sécurité et efficacité au cœur."
datePublished: Tue Dec 09 2025 07:52:10 GMT+0000 (Coordinated Universal Time)
cuid: cmiya8eck000302kz0fym8htt
slug: matrix-vs-signal-protocol-pourquoi-nous-ne-federons-pas
canonical: https://dev.to/anrysys/matrix-vs-signal-protocol-why-we-chose-not-to-federate-1pak

---

# Matrix vs Signal Protocol : Pourquoi Guardyn a choisi de ne pas fédérer

## TL;DR

- Matrix offre une solution fédérée efficace, mais ses compromis de sécurité et de performance ne convenaient pas aux besoins de Guardyn.
- Guardyn a préféré OpenMLS pour sa cryptographie avancée et ses garanties de sécurité adaptées à un environnement contrôlé.
- La fédération, bien que puissante, ajoute une complexité et des risques difficilement gérables dans des systèmes hautement sécurisés.
- Matrix reste pertinent pour certains contextes, mais ses limitations doivent être considérées avant de l'adopter.

## Les compromis à considérer

Lorsqu'il s'agit de concevoir une plateforme de communication sécurisée, le choix de l'architecture joue un rôle essentiel. Matrix, tout comme le protocole Signal, est souvent plébiscité pour sa capacité à gérer une communication sécurisée et fédérée. Toutefois, cette fédération s'accompagne de compromis.

### Fédération et sécurité cryptographique

La fédération, qui permet à plusieurs serveurs de communiquer entre eux et d'échanger des données, repose sur une architecture distribuée. Si cette approche garantit une grande flexibilité, elle expose également à des risques :

1. **Points d’entrée supplémentaires** : Plus il y a de serveurs dans un réseau fédéré, plus la surface d'attaque potentielle augmente.
2. **Complexité de gestion des clés** : Chaque serveur doit manipuler et échanger des informations cryptographiques, ce qui rend le système plus vulnérable aux erreurs ou aux attaques.
3. **Impact sur la performance** : L'interopérabilité entre serveurs peut entraîner des ralentissements et exiger des ressources supplémentaires.

Matrix utilise le protocole Megolm pour la gestion des communications chiffrées. Bien que robuste, ce protocole présente certains biais qui peuvent affecter profondément les besoins spécifiques d’une plateforme comme Guardyn.

## L'architecture de cryptage de Guardyn

Pour répondre à ses exigences de sécurité et de simplicité, Guardyn a opté pour OpenMLS au lieu de Megolm. Cette décision repose sur des caractéristiques techniques clés.

### OpenMLS : Une cryptographie basée sur l’arbre

OpenMLS (Messaging Layer Security) est un protocole conçu pour des communications sécurisées dans des groupes. Il repose sur une méthode cryptographique dite "basée sur l’arbre". Contrairement à Megolm, OpenMLS garantit :

- **Rotation rapide des clés** : Chaque message ou intervention dans le groupe entraîne une mise à jour des clés cryptographiques, rendant les attaques plus difficiles.
- **Évolutivité** : L’utilisation d’une structure en arbre assure une gestion efficace de la communication dans des groupes de taille variable.
- **Réduction de la complexité** : OpenMLS est conçu pour des environnements contrôlés et évite les problématiques liées à la fédération.

Guardyn, en choisissant une architecture centrée sur OpenMLS, peut ainsi offrir un niveau de sécurité supérieur tout en maîtrisant totalement son système.

## Pourquoi OpenMLS est meilleur que Megolm

Megolm, utilisé par Matrix, est un protocole performant pour des communications de groupe. Cependant, ses caractéristiques présentent des limites :

- **Maintien asynchrone des clés** : Megolm utilise des clés fixes pour les sessions, ce qui peut entraîner des vulnérabilités en cas de captation prolongée par un attaquant.
- **Compatibilité fédérée** : La structure fédérée de Matrix complique la gestion des communications sécurisées entre serveurs.
- **Scalabilité limitée** : La gestion des sessions devient problématique lorsque le nombre d'utilisateurs ou de serveurs augmente.

OpenMLS, de son côté, se concentre exclusivement sur des environnements non fédérés, avec une cryptographie capable de répondre aux besoins d’une plateforme comme Guardyn.

## Les avantages de ne pas fédérer avec Matrix

Le choix de ne pas fédérer avec Matrix va bien au-delà d’un simple débat architectural. Il répond à des besoins précis :

1. **Contrôle total** : Une architecture non fédérée comme celle de Guardyn garantit une maîtrise complète des communications et de la sécurité.
2. **Réduction des risques** : En évitant les échanges entre serveurs externes, il devient plus simple d’identifier et de corriger les failles.
3. **Performance accrue** : Guardyn peut optimiser ses communications sans avoir à prendre en compte les contraintes d’interopérabilité.

La fédération, bien qu’utile, est souvent grevée par une complexité qui peut entraîner des ralentissements dans des environnements exigeants.

## Quand Matrix est le bon choix

Matrix demeure une solution séduisante dans certains contextes :

- **Interopérabilité** : Pour des petites équipes ou des entreprises souhaitant connecter plusieurs serveurs, Matrix fédéré peut s'avérer très pratique.
- **Communications ouvertes** : Si la sécurité stricte n’est pas une priorité et que l’objectif est plutôt de connecter des communautés multiples, Matrix est une solution idéale.
- **Applications grand public** : Les outils de messagerie décentralisée accessibles à large échelle bénéficient grandement des avantages de Matrix.

## Quand éviter Matrix

Cependant, Matrix montre ses limites dans des cas spécifiques :

- **Environnements hautement sécurisés** : Dans des secteurs comme la défense, les soins de santé ou la finance, la fédération peut devenir un obstacle majeur.
- **Scalabilité stricte des communications de groupe** : Des groupes volumineux nécessitant des mises à jour rapides et une gestion efficace des clés trouveront plus d’avantages dans OpenMLS.
  
En conclusion, le choix d'un protocole comme Matrix ou OpenMLS dépend entièrement des objectifs de sécurité et de performance d’une organisation. Pour Guardyn, OpenMLS était clairement le meilleur choix.

[source](https://dev.to/anrysys/matrix-vs-signal-protocol-why-we-chose-not-to-federate-1pak)