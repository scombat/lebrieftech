---
title: "Cette vulnérabilité WebUI permet l'exécution de code à distance : comment rester protégé"
seoTitle: "Vulnérabilité WebUI: Prévenez l'exécution de code à distance avec la mise à jour v0.6.35"
seoDescription: "Découvrez la faille de sécurité WebUI (CVE-2025-64496) permettant l'exécution de code à distance. Installez la mise à jour v0.6.35 pour sécuriser vos systèmes."
datePublished: Tue Jan 06 2026 19:21:55 GMT+0000 (Coordinated Universal Time)
cuid: cmk2z7a7v000002jt2gnjfd1e
slug: webui-vulnerability-remote-code-execution
canonical: https://www.techradar.com/pro/security/this-webui-vulnerability-allows-remote-code-execution-heres-how-to-stay-safe

---

# Cette vulnérabilité WebUI permet l'exécution de code à distance : comment rester protégé

## TL;DR

- Une faille critique (CVE-2025-64496) dans WebUI permet l'exécution de code à distance via une injection JavaScript dans la fonctionnalité "Direct Connection".
- Les utilisateurs doivent mettre à jour vers la version corrigée v0.6.35 pour sécuriser leur système.
- Les versions affectées incluent toutes celles antérieures à v0.6.35.
- La vulnérabilité permet aux attaquants de voler des jetons d'authentification, de prendre le contrôle de comptes et d'exécuter des commandes malveillantes en backend.
- Limitez les connexions directes à des services fiables et surveillez les permissions pour réduire les risques.

## Contexte et détails de la vulnérabilité

Open WebUI est une interface web destinée à faciliter l'interaction avec des modèles linguistiques AI hébergés localement ou à distance. Sa popularité repose sur sa flexibilité et ses capacités variées. Cependant, une faille critique récemment découverte dans l'une de ses fonctionnalités met en danger les utilisateurs qui se connectent directement à des modèles distants.

La vulnérabilité, identifiée comme CVE-2025-64496, a été révélée en octobre 2025 par Vitaly Simonovich, un expert en sécurité chez Cato CTRL. Elle réside dans la manière dont la fonctionnalité "Direct Connection" de WebUI traite les données. En exploitant une faille d'injection de code JavaScript via des événements Server-Sent Event (SSE), les attaquants peuvent exécuter du code malveillant directement dans le navigateur de la victime.

### Impacts potentiels

L'exploitation de cette vulnérabilité peut avoir de graves conséquences pour les utilisateurs concernés. Les principales répercussions incluent :

- **Vol de jetons d'authentification** : Les attaquants pourraient s'emparer des informations de session des utilisateurs, permettant l'accès non autorisé.
- **Prise de contrôle des comptes utilisateur** : En compromettant les sessions, les attaquants pourraient modifier les paramètres du compte ou voler des données sensibles.
- **Exécution de code malveillant** sur le système de l'utilisateur grâce aux API backend, mettant le système en danger.

### Facteurs de risque

Plusieurs facteurs peuvent exacerber le risque d'exploitation de cette vulnérabilité :

- Les connexions directes sont désactivées par défaut dans WebUI. Cependant, certains utilisateurs activent manuellement cette fonctionnalité, augmentant leur exposition à des modèles non fiables.
- L'ajout de liens ou d'URLs vers des modèles malveillants, que ce soit volontaire ou dû à une attaque par ingénierie sociale, est une source majeure de danger.
- Les paramètres de permissions des outils dans l'interface WebUI peuvent ajouter des failles supplémentaires si configurés de manière trop permissive.

### Versions concernées

Toutes les versions de WebUI antérieures à v0.6.35 sont vulnérables (y compris la v0.6.34). La mise à jour v0.6.35 inclut des protections supplémentaires, notamment des fonctionnalités de middleware qui empêchent l'exploitation des événements SSE.

## Ce que vous devez surveiller pour éviter les risques

Cette vulnérabilité met en lumière un problème sous-jacent dans la sécurité des interfaces AI : l'échec à établir des limites claires entre les modèles externes (pouvant être compromis) et les systèmes utilisateurs. Pour minimiser les risques, il est impératif de surveiller attentivement :

- Les connexions directes avec des serveurs ou modèles AI externes, qui doivent être limités à des sources fiables et vérifiées.
- Les permissions accordées via **workspace.tools** : seules les personnes de confiance et ayant réellement besoin d'accéder à ces outils doivent y avoir accès.
- La création d'outils suspects dans l'interface. Toute modification inattendue ou activité inhabituelle devrait être investiguée.

## Les étapes pour rester protégé

Voici les actions clés à engager immédiatement pour renforcer la sécurité de votre système et limiter l'impact de cette faille :

1. **Mettez à jour WebUI vers la version corrigée v0.6.35 ou supérieure**. Cette version intègre des protections nécessaires contre les injections de code malveillant.
2. **Révisez vos connexions externes** : assurez-vous que les modèles linguistiques utilisés proviennent de sources sûres et évaluées. Suspendez toute connexion douteuse.
3. **Désactivez les connexions directes si elles ne sont pas nécessaires**. Privilégiez les configurations par défaut qui désactivent cette fonctionnalité.
4. **Réévaluez les niveaux de permission pour chaque utilisateur** : certaines permissions peuvent offrir un accès inutile ou surdimensionné aux outils, créant des failles exploitables.
5. **Surveillez activement votre infrastructure WebUI** pour détecter toute activité anormale ou malveillante.

En adoptant ces mesures, vous pouvez réduire considérablement les risques d'exploitation.

## Conclusion sur la sécurité WebUI

La découverte de la vulnérabilité CVE-2025-64496 dans WebUI constitue un rappel essentiel sur les dangers liés à une gestion insuffisante de la sécurité des outils AI. Bien que cette faille soit grave, elle met également en évidence l'importance de garantir des limites de confiance rigoureuses dans les connexions avec des modèles tiers.

En installant la dernière mise à jour corrective v0.6.35 et en suivant les recommandations ci-dessus, les utilisateurs peuvent diminuer leur exposition et renforcer la posture sécuritaire de leurs systèmes. Cette vigilance est d'autant plus cruciale à mesure que la dépendance aux outils AI s'amplifie dans le paysage technologique actuel.

[source](https://www.techradar.com/pro/security/this-webui-vulnerability-allows-remote-code-execution-heres-how-to-stay-safe)