---
title: "Une faille critique dans Windows Server exploitée pour propager des malwares"
seoTitle: "Une faille critique dans Windows Server exploitée par des hackers : tout ce qu'il faut savoir"
seoDescription: "Découvrez comment une vulnérabilité dans Windows Server Update Services est exploitée par des groupes étatiques pour propager des malwares. Solutions et détails."
datePublished: Mon Nov 24 2025 17:27:02 GMT+0000 (Coordinated Universal Time)
cuid: cmidf5wt5000002jog5arbpzp
slug: vulnerabilite-windows-server-exploitee-par-hackers
canonical: https://www.techradar.com/pro/security/windows-server-flaw-targeted-by-hackers-to-spread-malware-heres-what-we-know

---

# Une faille critique dans Windows Server exploitée pour propager des malwares

## TL;DR
- Des groupes soutenus par l'État chinois exploitent une vulnérabilité critique (CVE-2025-59287) dans WSUS pour exécuter du code à distance avec des privilèges élevés.
- Le malware utilisé, **ShadowPad**, se propage via des outils comme PowerCat, certutil, et curl.
- Les cibles incluent des secteurs stratégiques : défense, télécommunications, infrastructures critiques.
- La faille résulte d'une désérialisation non sécurisée dans WSUS, exposant les serveurs à des attaques non authentifiées.
- Il est impératif d'appliquer les correctifs de sécurité publiés par Microsoft en octobre et novembre 2025 pour protéger les systèmes.

## Contexte de la vulnérabilité

Le service Windows Server Update Services (WSUS) est un outil clé pour gérer les mises à jour de sécurité au sein des entreprises. Cependant, une vulnérabilité critique, identifiée sous le code CVE-2025-59287, a rendu ces serveurs sensibles à des attaques sophistiquées. Évaluée à 9.8/10 sur l’échelle de gravité CVSS, cette faille peut être exploitée pour obtenir un accès non authentifié avec des privilèges SYSTEM et exécuter du code à distance.

Découverte en octobre 2025, cette vulnérabilité est rapidement devenue une cible prioritaire après la publication d’un exploit proof-of-concept. Bien que Microsoft ait réagi avec des correctifs initiaux, la propagation d'outils exploitant la faille a favorisé des attaques actives documentées par des experts en cybersécurité comme AhnLab Security Intelligence Center.

## Caractéristiques de la faille CVE-2025-59287

### Nature de la vulnérabilité
La faille repose sur une désérialisation des données non fiables au sein de WSUS. Cette méthode d'attaque permet aux acteurs malveillants :
- Une exécution de code à distance (RCE) sans interaction nécessaire de l'utilisateur.
- Un accès avec des privilèges étendus (SYSTEM), garantissant un contrôle presque total du serveur ciblé.
- Une possibilité d’étendre l’attaque, en compromettant plusieurs serveurs WSUS d’un réseau.

### Facteurs aggravants
L’exposition des serveurs WSUS à cette faille pose des menaces importantes pour les grandes infrastructures. Ces serveurs, utilisés pour gérer les mises à jour vers des centaines de machines, peuvent devenir des vecteurs pour propager des malwares à grande échelle.

## Méthodes utilisées par les attaquants

### Processus d’exploitation
Les groupes de menaces soutenus par l’État chinois ont mis au point une chaîne d'attaque bien organisée :
1. **Exploitation initiale** : Accès au serveur via CVE-2025-59287.
2. **Prise de contrôle** : Utilisation de **PowerCat**, un outil de manipulation réseau, pour ouvrir un shell et exécuter des commandes malveillantes.
3. **Propagation** : Déploiement du malware **ShadowPad** à l’aide des outils systèmes tels que **certutil** et **curl**.

### Le malware ShadowPad
ShadowPad est une version avancée de **PlugX**, un ancien malware utilisé par des groupes de menace chinois. Capable d’exécuter du code via des logiciels légitimes (technique du side-loading), ShadowPad s’appuie sur des exécutables tels que **ETDCtrlHelper.exe** pour masquer ses activités et éviter la détection par les outils de sécurité.

## Impact sur les infrastructures critiques

Bien que la liste complète des victimes de ces attaques ne soit pas encore accessible, les groupes responsables semblent cibler des secteurs d’envergure et stratégiques :
- **Gouvernement** : Les agences nationales sont des cibles de choix.
- **Défense** : Accès potentiel à des données sensibles et stratégiques.
- **Infrastructures critiques** : Énergie, transport, eau potable, etc.
- **Télécommunications** : Perturbation de réseaux de communication vitaux.

Ces secteurs jouent un rôle clé dans le fonctionnement des nations et leur protection est cruciale pour garantir leur pérennité. Un serveur WSUS compromis permet non seulement la propagation de malwares mais aussi des exfiltrations de données ou des interruptions de service.

## Mesures à prendre immédiatement

1. **Appliquer les correctifs** : Assurez-vous que tous les serveurs WSUS disposent des mises à jour publiées par Microsoft en octobre et novembre 2025.
2. **Surveillance accrue des activités** : Mettez en place des outils capables de détecter des comportements suspects, tels que l’exécution abusive de **PowerCat**, **certutil**, ou **curl** sur vos serveurs.
3. **Bloquer les menaces connues** : Mettez à jour vos solutions de détection de malwares pour repérer les traces de **ShadowPad** et de ses dépendances.
4. **Connaissance des vecteurs d’attaque** : Identifiez les processus pouvant utiliser des techniques de side-loading, comme **ETDCtrlHelper.exe**, et surveillez-les étroitement.

## En conclusion

Cette récente vulnérabilité dans Windows Server Update Services est un signal d'alarme pour l’ensemble des responsables sécurité en entreprise. Les attaques contre les serveurs critiques deviennent de plus en plus fréquentes, particulièrement lorsque des acteurs soutenus par des États y voient un moyen de déstabiliser des infrastructures vitales.  

En mettant rapidement à jour vos systèmes et en surveillant les indicateurs de compromission, vous pouvez significativement réduire les risques de tomber victime de ces attaques.

[source](https://www.techradar.com/pro/security/windows-server-flaw-targeted-by-hackers-to-spread-malware-heres-what-we-know)