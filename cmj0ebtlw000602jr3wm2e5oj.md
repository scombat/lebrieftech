---
title: "Microsoft publie 56 correctifs de sécurité, incluant une faille zero-day"
seoTitle: "Microsoft corrige 56 failles critiques, y compris une faille zero-day"
seoDescription: "Microsoft publie des correctifs pour 56 vulnérabilités, dont une faille zero-day critique. Appliquez ces mises à jour pour renforcer la sécurité de votre système."
datePublished: Wed Dec 10 2025 19:22:20 GMT+0000 (Coordinated Universal Time)
cuid: cmj0ebtlw000602jr3wm2e5oj
slug: microsoft-corrige-56-failles-critiques-et-une-faille-zero-day
canonical: https://www.techradar.com/pro/security/microsoft-issues-patches-for-56-security-flaws-all-important-severity-or-above

---

# Microsoft publie 56 correctifs de sécurité, incluant une faille zero-day

## TL;DR

- Microsoft corrige **56 failles de sécurité** dans son écosystème, toutes de gravité « importante » ou supérieure.  
- Une vulnérabilité **zero-day activement exploitée**, identifiée sous le code CVE-2025-62221, est particulièrement préoccupante.  
- Les correctifs couvrent les failles liées à **GitHub Copilot**, **PowerShell** et **File Explorer**.  
- Des améliorations notables incluent des ajustements à l'interface de Copilot et des avertissements supplémentaires sur PowerShell 5.1.  

## Contexte des correctifs de Microsoft

Le Patch Tuesday de décembre 2025 marque une avancée importante dans la stratégie de sécurité de Microsoft. Au total, 56 vulnérabilités ont été corrigées, toutes considérées comme critiques ou importantes par l'entreprise. Ces failles touchent certains composants clés parmi les produits les plus utilisés, tels que Windows, GitHub Copilot et PowerShell.

La menace croissante des cyberattaques exige une réponse rapide et proactive. La mise à jour de décembre illustre parfaitement ces efforts, en abordant tant des problèmes critiques, tels que les failles zero-day, que des améliorations générales visant à renforcer la sécurité globale des systèmes.

Parmi les ajustements notables, on retrouve des modifications apportées à l'interface utilisateur de GitHub Copilot afin de la rendre moins vulnérable, ainsi que des protections supplémentaires intégrées à PowerShell.

## Failles critiques corrigées

### CVE-2025-62221 : Une vulnérabilité zero-day activement exploitée

Le correctif phare de cette mise à jour est sans doute celui concernant CVE-2025-62221. Identifiée comme une faille de type "use-after-free", elle affecte le Windows Cloud Files Mini Filter Driver. Cette vulnérabilité permet une élévation de privilèges locaux et présente un score CVSS de 7.8.

Ce zero-day est activement exploité, renforçant l'urgence d'appliquer le correctif. Selon Kev Breen, chercheur en sécurité chez Immersive Labs, les attaques ciblant ce composant étaient une préoccupation récurrente. La correction apportée est donc essentielle pour préserver les environnements Windows des exploitations malveillantes en cours.

### CVE-2025-64671 : Une faille d'exécution de code dans GitHub Copilot

Les développeurs utilisant GitHub Copilot pour JetBrains doivent particulièrement surveiller cette vulnérabilité. CVE-2025-64671, avec une gravité de 8.4 (CVSS), exploite une injection de commandes malveillantes via Cross Prompt Injection. Bien que nécessitant un déclenchement local, la possibilité pour un attaquant d'exécuter du code malveillant depuis l’environnement de développement rend cette faille particulièrement dangereuse pour les projets de développement.

### CVE-2025-54100 : Vulnérabilité dans PowerShell Invoke-WebRequest

CVE-2025-54100, notée 7.8, touche PowerShell 5.1 et permet l'exécution de commandes arbitraires par des utilisateurs ayant accès en local. Les utilisateurs se reposant sur PowerShell dans leurs flux de travail automatisés doivent appliquer rapidement ce patch afin d'éviter que cette faille ne soit exploitée pour des actions malicieuses.

## Améliorations supplémentaires

En plus de corriger les failles critiques, Microsoft a déployé diverses améliorations visant à renforcer l'expérience utilisateur et la sécurité au sein de ses outils :

- **Interface utilisateur de GitHub Copilot** : ajustements pour améliorer la résilience contre des attaques potentielles.  
- **File Explorer** : plusieurs bugs corrigés pour éliminer des points de vulnérabilité qui pouvaient compromettre la stabilité du système.  
- **PowerShell 5.1** : introduction de nouveaux avertissements d’exécution visant à limiter les risques liés aux scripts malveillants ou à l’exécution de commandes non sécurisées.  

Ces ajustements, bien qu’indirectement liés à des vulnérabilités spécifiques, contribuent globalement à renforcer la fiabilité des outils critiques.

## Recommandations pour renforcer la sécurité

Les entreprises et les utilisateurs individuels doivent adopter une posture proactive face à ces mises à jour :

- **Appliquez ces correctifs dès que possible** pour limiter les risques liés aux vulnérabilités activement exploitées, notamment la faille zero-day CVE-2025-62221.  
- **Surveillez les nouvelles vulnérabilités** susceptibles de survenir au sein des systèmes Microsoft et des outils tiers comme GitHub Copilot.  
- **Revoyez vos pratiques de sécurité** en ce qui concerne les scripts et applications externes, notamment ceux utilisant des outils comme PowerShell.  
- **Restez à jour sur les recommandations de Microsoft**, qui continue de mettre en œuvre des solutions rapides et efficaces face aux nouvelles menaces.

En appliquant ces recommandations, les responsables IT peuvent minimiser les risques liés aux failles de sécurité et garantir la protection de leurs systèmes informatiques.

## À retenir

Microsoft poursuit ses efforts pour sécuriser son vaste écosystème de produits. Les correctifs de décembre 2025 démontrent l’importance d’une gestion rigoureuse des vulnérabilités, notamment dans un contexte de menace croissante dû aux exploits actifs. Il est essentiel pour les utilisateurs, qu'ils soient individuels ou en entreprise, de prioriser ces mises à jour afin de maintenir des environnements numériques sécurisés et fiables.

[source](https://www.techradar.com/pro/security/microsoft-issues-patches-for-56-security-flaws-all-important-severity-or-above)