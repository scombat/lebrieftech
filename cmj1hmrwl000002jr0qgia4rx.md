---
title: "Storm-0249 intensifie les attaques par ransomware et utilise ClickFix"
seoTitle: "Storm-0249 : intensification des attaques par ransomware via ClickFix et DLL Sideloading"
seoDescription: "Storm-0249 utilise des tactiques innovantes comme PowerShell sans fichier et DLL Sideloading pour des attaques de ransomware furtives et sophistiquées."
datePublished: Thu Dec 11 2025 13:42:36 GMT+0000 (Coordinated Universal Time)
cuid: cmj1hmrwl000002jr0qgia4rx
slug: storm-0249-intensification-ransomware-clickfix-dll-sideloading
canonical: https://thehackernews.com/2025/12/storm-0249-escalates-ransomware-attacks.html

---

# Storm-0249 intensifie les attaques par ransomware et utilise ClickFix

## TL;DR

- **Storm-0249** se distingue par des tactiques furtives et avancées liées aux attaques de ransomware.
- Techniques utilisées : chargement latéral de DLL, PowerShell sans fichier, et manipulation de domaines usurpés.
- Les attaques exploitent des outils légitimes comme SentinelOne pour diminuer les chances de détection.
- L'objectif : maintenir un accès persistant et préparer des systèmes compromis pour des ransomware ciblés.
- Les entreprises doivent surveiller activement les IoCs et les tactiques liées à Storm-0249 pour renforcer leur posture de défense.

## Comprendre les tactiques furtives de Storm-0249

Le groupe Storm-0249, identifié par Microsoft comme un courtier d'accès initial, est passé à une phase plus aboutie de ses activités malveillantes en collaborant avec d'autres groupes de ransomware tels que Storm-0501. Historiquement associé à des campagnes de phishing à motif fiscal, notamment visant les États-Unis, il s'est récemment concentré sur l'utilisation de malwares sophistiqués comme Latrodectus et Brute Ratel C4 (BRc4).

Ce virage stratégique marque une transition majeure, où Storm-0249 mise sur des campagnes furtives alliant techniques avancées et exploitation des processus de confiance. Ces efforts permettent de réduire les probabilités de détection tout en maximisant les dégâts potentiels.

## Implications pour les entreprises et la sécurité

Les tactiques de Storm-0249 posent des enjeux considérables pour les entreprises, principalement par leur capacité à compromettre des environnements en utilisant des techniques "Living-off-the-Land". Les processus signés, considérés comme sûrs par les mécanismes de sécurité traditionnels, deviennent des vecteurs d'attaque efficaces.

Une des particularités des attaques est la mise en œuvre de clés de chiffrement basées sur des identités système uniques, telles que **MachineGuid**. Cela signifie que les données chiffrées sont irréversiblement cryptées en l'absence d'interaction de l'attaquant. Des groupes de ransomware tels que **LockBit** et **ALPHV** ont déjà adopté ces méthodes pour intensifier leurs opérations. Les entreprises doivent donc élever leur surveillance des outils administratifs détournés et renforcer leur détection des tactiques associées.

## Techniques phares : PowerShell et DLL trojanisées

### Méthode ClickFix

Storm-0249 exploite une séquence méthodique pour compromettre ses victimes via l'ingénierie sociale :

1. Les utilisateurs sont incités à exécuter une commande malveillante en passant via le dialogue "Exécuter" de Windows.
2. Cette commande télécharge un script PowerShell depuis un domaine usurpé prenant l'apparence d'une ressource légitime (ex. sgcipl[.]com/us.microsoft.com/bdo/).
3. L'exécution du script PowerShell est réalisée sans fichier, échappant ainsi aux détections habituelles.
4. Un fichier MSI est installé avec des privilèges SYSTEM, déclenchant une chaîne d'installation malveillante.
5. Parmi les fichiers installés figure une DLL trojanisée (`SentinelAgentCore.dll`), placée dans le dossier AppData et se faisant passer pour un composant de SentinelOne.
6. La DLL falsifiée utilise le processus légitime `SentinelAgentWorker.exe` pour établir une communication cryptée avec un serveur de commande et de contrôle (C2).

### Autres tactiques remarquables

Storm-0249 ne s'arrête pas à l'utilisation de DLL trojanisées. Ses techniques incluent :

- L'extraction d'identifiants système comme **MachineGuid** via des outils légitimes tels que `reg.exe`.
- L'exécution de commandes au sein de processus signés et légitimes, reposant sur la confiance de ces programmes pour minimiser les détections.
- Le passage stratégique de campagnes de phishing généralisées à des attaques ciblées reposant sur la crédibilité des outils et processus signés.

## Que retenir de Storm-0249 ?

Storm-0249 représente une menace croissante pour la cybersécurité des entreprises. En combinant des techniques furtives avec une manipulation experte des outils de confiance, il réduit efficacement les chances de détection et maximise la portée de ses attaques. L'exploitation des identités système uniques et des processus légitimes amplifie les défis auxquels les défenseurs doivent faire face.

### Points essentiels à surveiller

- Les indicateurs de compromission (IoCs) tels que les domaines usurpés (`sgcipl[.]com`) et les DLL trojanisées sont des signaux d'alarme essentiels.
- La prolifération de fichiers MSI liés à des processus validés souligne l'importance de renforcer la surveillance des fichiers exécutables.
- L'utilisation croissante de techniques "Living-off-the-Land" pour exploiter des outils légitimes confirme l'importance d'une approche proactive en matière de sécurité.

En fin de compte, Storm-0249 illustre comment les cybercriminels évoluent pour s'adapter à l'environnement technologique moderne. Pour les entreprises, comprendre ces tactiques et surveiller activement les mouvements des groupes comme Storm-0249 sont des prérequis indispensables pour ne pas devenir une cible.

[source](https://thehackernews.com/2025/12/storm-0249-escalates-ransomware-attacks.html)