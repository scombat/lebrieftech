---
title: "Corrigez la faille SonicOS qui permet de planter les pare-feu"
seoTitle: "Corrigez la faille SonicOS qui permet de planter les pare-feu"
seoDescription: "Une faille critique dans SonicOS SSLVPN expose les pare-feu Gen7/Gen8 au risque de DoS. Mettez à jour vos systèmes immédiatement."
datePublished: Fri Nov 21 2025 16:22:16 GMT+0000 (Coordinated Universal Time)
cuid: cmi92j2mw000202le0wux9g3q
slug: faille-sonicos-pare-feu
canonical: https://www.techradar.com/pro/security/sonicwall-tells-customers-to-patch-sonicos-flaw-allowing-hackers-to-crash-firewalls

---

```markdown
# Corrigez la faille SonicOS qui permet de planter les pare-feu

## TL;DR

- Une vulnérabilité critique (CVE-2025-40601) a été découverte dans le service SonicOS SSLVPN, exposant les pare-feu Gen7 et Gen8 à des attaques par déni de service (DoS).
- Bien qu'aucune attaque exploitant cette faille n'ait été signalée, SonicWall recommande de désactiver ou restreindre l'accès à SSLVPN jusqu'à l'application du correctif.
- Deux autres failles (CVE-2025-40604 et CVE-2025-40605) affectant les dispositifs de sécurité des e-mails ont également été corrigées.
- Il est impératif d'installer immédiatement les mises à jour publiées pour sécuriser vos systèmes.

## Qu'est-ce que la vulnérabilité SonicOS SSLVPN ?

SonicWall, acteur majeur en cybersécurité réseau, a récemment mis en lumière une vulnérabilité critique qui touche son service SonicOS SSLVPN. Identifiée sous l'ID **CVE-2025-40601**, cette faille repose sur un **débordement de pile** dans le composant SonicOS SSLVPN. Ce défaut, noté 7,5 sur 10 dans le cadre de l'évaluation CVSS, peut entraîner un crash des pare-feu des générations 7 et 8 (Gen7/Gen8) lorsqu'il est exploité. 

Le risque principal réside dans la possibilité pour des attaquants de provoquer une indisponibilité totale du service en initiant une attaque par déni de service (DoS). Les modèles antérieurs (Gen6, SMA 100, SMA 1000) ne sont pas concernés par cette vulnérabilité.

SonicWall souligne l'importance cruciale de corriger rapidement cette faille pour éviter tout impact sur l'intégrité et la disponibilité des systèmes affectés.

## Comment corriger la faille SonicOS ?

Pour protéger vos systèmes, SonicWall recommande une approche proactive et immédiate. Voici les étapes à suivre :

1. **Installer la mise à jour corrective** : SonicWall a publié un correctif pour combler cette vulnérabilité. Il est impératif de l'appliquer sur tous les dispositifs concernés (Gen7 et Gen8).
2. **Désactiver le service SSLVPN** : Si le correctif ne peut pas être déployé immédiatement, désactivez temporairement le service SSLVPN pour réduire la surface d'attaque.
3. **Limiter les accès** : Restreignez les connexions SSLVPN uniquement aux utilisateurs de confiance et dans la mesure du possible, implémentez un filtrage IP pour minimiser les risques.
4. **Planifier une vérification des correctifs** : Assurez-vous que toutes les mises à jour de sécurité ont été correctement appliquées sur l'ensemble de vos environnements réseau.

Si vos dispositifs ne sont pas encore protégés, sachez que plus la correction tarde, plus le risque de compromission augmente, d'autant que les détails de la faille sont désormais publics.

## Impact potentiel sur les pare-feu des entreprises

La vulnérabilité CVE-2025-40601 représente une menace sérieuse pour la stabilité des infrastructures réseau. Les entreprises utilisant les pare-feu Gen7 et Gen8 de SonicWall risquent notamment :

- **Des interruptions de service** : Une attaque DoS réussie entraînerait un arrêt complet des pare-feu, impactant directement la connectivité réseau et les opérations critiques.
- **Des pertes financières** : La durée des interruptions pourrait causer des pénalités liées au non-respect des SLA (accords sur les niveaux de service) ainsi que des pertes d'opportunités commerciales.
- **Une atteinte à l'image de marque** : Les entreprises affectées pourraient perdre la confiance de leurs clients, en particulier si une exploitation publique venait à toucher de grandes organisations.

Bien qu'aucune exploitation active n'ait été reportée à ce jour, il est légitime de s’attendre à ce que des preuves de concept ou des scripts malveillants fassent rapidement surface, augmentant le risque d’attaques ciblées.

## Autres vulnérabilités corrigées par SonicWall

En parallèle de la faille CVE-2025-40601, SonicWall a également publié des correctifs pour deux vulnérabilités critiques affectant ses dispositifs de sécurité des courriels (solutions Email Security) :

- **CVE-2025-40604** : Cette faille permet l'exécution de code arbitraire sur les dispositifs, offrant aux attaquants une prise de contrôle complète des appareils.
- **CVE-2025-40605** : Une autre vulnérabilité permettant un accès non autorisé à des données sensibles stockées sur les dispositifs Email Security.

Ces deux vulnérabilités impactent notamment les modèles de la série ES (comme le Appliance ES 5000, 5050, etc.). Les correctifs correspondants ont également été mis à disposition par SonicWall, et leur application immédiate est fortement recommandée pour éviter des risques d'intrusion ou de vol de données.

## À retenir

- La faille SonicOS SSLVPN (CVE-2025-40601) expose les pare-feu Gen7 et Gen8 au risque d’attaques DoS et nécessite une réponse immédiate.
- Des correctifs ont été publiés et doivent être appliqués sans délai pour sécuriser vos systèmes.
- En parallèle, deux autres vulnérabilités critiques ont été corrigées sur les dispositifs Email Security de SonicWall.
- Adoptez des mesures temporaires comme la désactivation ou la limitation du service SSLVPN si vous ne pouvez pas corriger immédiatement vos systèmes.

Le maintien des infrastructures réseau en sécurité passe par une vigilance accrue et des mises à jour régulières. Face à une menace en constante évolution, l'application rapide des correctifs est essentielle pour protéger vos environnements critiques.
```

[source](https://www.techradar.com/pro/security/sonicwall-tells-customers-to-patch-sonicos-flaw-allowing-hackers-to-crash-firewalls)