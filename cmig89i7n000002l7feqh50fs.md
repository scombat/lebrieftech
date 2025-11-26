---
title: "Ransomware : les PME ciblées lors des fusions-acquisitions"
seoTitle: "Ransomware : les PME ciblées lors des fusions-acquisitions"
seoDescription: "Les ransomwares ciblent les PME durant les fusions-acquisitions, exploitant des failles de sécurité comme celles des appareils SonicWall SSL VPN."
datePublished: Wed Nov 26 2025 16:37:11 GMT+0000 (Coordinated Universal Time)
cuid: cmig89i7n000002l7feqh50fs
slug: ransomware-pme-cibles-fusions-acquisitions
canonical: https://www.techradar.com/pro/security/ransomware-hackers-attack-smbs-being-acquired-to-try-and-gain-access-to-multiple-companies

---

```markdown
# Ransomware : les PME ciblées lors des fusions-acquisitions

## TL;DR
- Les entreprises en processus de fusion-acquisition héritent parfois de matériels compromis par des ransomware.
- Le ransomware Akira exploite les appareils SonicWall SSL VPN non patchés pour faciliter les déplacements latéraux et le cryptage des données.
- Une vulnérabilité critique (CVE-2025-40601) affectant SonicWall Gen7 et Gen8 a été corrigée, mais reste activement exploitée.

## Les méthodes des hackers : une menace croissante
Les cybercriminels innovent constamment pour contourner les protections et cibler des failles inattendues afin de maximiser leurs profits. Les processus de fusion-acquisition se sont particulièrement démarqués comme une opportunité lucrative pour les attaquants, en raison de l’intégration souvent précipitée d’actifs informatiques compromis. 

Un rapport récent de ReliaQuest montre que le ransomware Akira est régulièrement employé pour infiltrer des entreprises via des systèmes vulnérables qu'elles ont acquis. Des appareils réseau tels que les SonicWall SSL VPN, lorsqu'ils ne sont pas à jour, offrent une porte d’entrée idéale aux hackers.

L’approche des cyberattaquants, révélée entre juin et octobre 2025, montre que la faute revient principalement à l’incapacité des entreprises à détecter des vulnérabilités dans les actifs absorbés. Une fois introduits via ces dispositifs, les opérateurs malveillants mènent des déplacements latéraux pour atteindre les systèmes critiques, où ils chiffrent les données, exigeant des rançons importantes.

## Focus sur la vulnérabilité CVE-2025-40601
Parmi les vecteurs principaux des attaques décrites, une vulnérabilité critique intitulée **CVE-2025-40601** a été identifiée dans les appliances SonicWall SSL VPN de génération 7 et 8. Cette faille permet aux attaquants non authentifiés situés à distance de provoquer un débordement de la mémoire tampon, entraînant un déni de service ou une prise de contrôle.

### Appareils concernés
- Gen7 et Gen8 SonicWall Firewalls sont touchés.
- Les modèles plus anciens de la série Gen6 ainsi que les SMA 1000 et SMA 100 séries ne sont pas concernés.

### Correctif et état actuel
Bien que SonicWall ait publié un correctif visant à résoudre cette vulnérabilité, des entreprises continuent d’être victimes de ransomware, démontrant une exploitation active par des groupes malveillants, dont celui à l’origine d’Akira. Malgré l’adoption de solutions de sécurité comme l’authentification multifactorielle, des attaques ciblées persistent sur les actifs compromis.

## Mesures de sécurité à adopter
Face à l’augmentation des cyberattaques, notamment via des appareils hérités non sécurisés, les entreprises doivent prioriser les audits de sécurité et maintenir des pratiques rigoureuses pour protéger leur réseau.

### Étapes recommandées
1. **Audit des systèmes acquis** : Lors d’une fusion-acquisition, il est crucial d’effectuer une évaluation complète des dispositifs, systèmes et logiciels intégrés. Les audits doivent inclure des tests de pénétration approfondis pour détecter tout compromis potentiel.
2. **Gestion des correctifs** : Assurez-vous que tous les appareils réseau, tels que les VPN SonicWall, disposent de correctifs à jour pour prévenir l’exploitation des vulnérabilités connues.
3. **Approche collaborative** : Mettre en place une collaboration entre les équipes commerciales et informatiques afin d’identifier et réduire les risques cybersécuritaires liés aux acquisitions, dès les phases initiales.

### Outils et solutions conseillés
Les outils modernes de cybersécurité spécialisés dans le monitoring des infrastructures acquises peuvent grandement aider à identifier les vulnérabilités rapidement. Des solutions tels que les systèmes de détection et prévention des intrusions (IDS/IPS) ou les plateformes de gestion de risques doivent être intégrées dans toute stratégie post-acquisition.

## Pourquoi les fusions-acquisitions sont vulnérables
Les processus de fusion-acquisition comportent de nombreuses contraintes qui favorisent les risques cybernétiques :
- **Intégration rapide** : Dans la précipitation, les entreprises peuvent incorporer des actifs sans vérifier leur état sécuritaire.
- **Complexité des systèmes hérités** : Les infrastructures acquises peuvent inclure des technologies anciennes ou mal entretenues, susceptibles d’abriter des failles critiques.
- **Manque de coordination** : Les différences entre les équipes IT des sociétés fusionnées peuvent entraîner des oublis ou retards dans l'application des bonnes pratiques en matière de sécurité.

Ces facteurs combinés créent des environnements propices à l’exfiltration ou au cryptage de données par des ransomwares.

## À retenir
Les PME engagées dans des fusions-acquisitions sont devenues des cibles privilégiées des ransomwares comme Akira, qui exploitent systématiquement des failles dans les actifs hérités tels que les appareils SonicWall SSL VPN. Une vigilance particulière est requise à chaque étape du processus d’intégration pour prévenir ces menaces coûteuses.

```


[source](https://www.techradar.com/pro/security/ransomware-hackers-attack-smbs-being-acquired-to-try-and-gain-access-to-multiple-companies)