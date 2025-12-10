---
title: "Faille critique « React2Shell » exploitée par des hackers nord-coréens"
seoTitle: "Faille critique « React2Shell » exploitée par des hackers nord-coréens"
seoDescription: "Découvrez comment la vulnérabilité React2Shell et le malware EtherRAT sont exploités par des hackers nord-coréens et comment s'en protéger."
datePublished: Wed Dec 10 2025 20:23:12 GMT+0000 (Coordinated Universal Time)
cuid: cmj0gi3hs000p02l88co424ug
slug: react2shell-faille-exploitee-hackers-nord-coreens
canonical: https://www.techradar.com/pro/security/maximum-severity-react2shell-flaw-exploited-by-north-korean-hackers-in-malware-attacks

---

# Faille critique « React2Shell » exploitée par des hackers nord-coréens

## TL;DR

- La vulnérabilité React2Shell (CVE-2025-55182) permet une exécution de code à distance sur les React Server Components avant toute authentification.
- Les hackers nord-coréens ont conçu EtherRAT, un malware sophistiqué exploitant cette faille avec persistance Linux et contrôle via Ethereum.
- Des mesures de correction existent via des mises à jour des versions de React affectées.
- La faille a également été mise à profit par des groupes chinois, signalant une intensification des attaques contre React et Next.js.

## Contexte et pertinence de la faille React2Shell

React est une bibliothèque JavaScript majeure, adoptée par des millions de développeurs pour construire des interfaces web performantes. Une vulnérabilité critique, surnommée **React2Shell** (identifiée sous la référence CVE-2025-55182), a été découverte dans plusieurs versions des React Server Components.

Cette faille, avec un score CVSS maximal de 10/10, permet à un attaquant d’exécuter du code à distance sans nécessiter de processus d’authentification. Son potentiel destructeur réside dans la possibilité de compromettre des infrastructures basées sur React, en exploitant des fonctionnalités associées aux paquets suivants :

- `react-server-dom-webpack`
- `react-server-dom-parcel`
- `react-server-dom-turbopack`

Les versions affectées comprennent notamment :

- **19.0**
- **19.1.0**
- **19.1.1**
- **19.2.0**

À la suite de la divulgation de cette faille, des groupes de menaces chinois comme Earth Lamia et Jackpot Panda ont été parmi les premiers à l’utiliser activement. Récemment, des rapports de sécurité ont mis en lumière l’implication de hackers nord-coréens, qui ont développé des outils complexes pour cibler cette vulnérabilité.

## Comprendre la vulnérabilité et ses implications

### Nature et mécanisme de React2Shell

React2Shell représente une menace significative pour les développeurs frontend et les équipes responsables des serveurs web. La faille permet l'accès non autorisé à des environnements exécutant des versions vulnérables de React Server Components. 

Pour se protéger, il est impératif de corriger les versions concernées en effectuant une mise à jour vers :

- **19.0.1**
- **19.1.2**
- **19.2.1**

Une vigilance proactive est essentielle, particulièrement dans les organisations utilisant les technologies Next.js ou des environnements complexes exploitant ces bibliothèques.

## Exploitation par des hackers nord-coréens

### EtherRAT : un malware sophistiqué

Les hackers nord-coréens ont conçu un malware nommé **EtherRAT** pour exploiter React2Shell. Ce malware se distingue par des fonctionnalités uniques :

- **Contrôle via des contrats intelligents Ethereum** : Une méthode qui garantit une interaction masquée et non détectable au sein de la blockchain publique.
- **Persistance avancée sous Linux** : EtherRAT utilise jusqu'à cinq mécanismes pour s’assurer d’une présence continue sur les systèmes compromis.
- **Téléchargement automatique de Node.js** : Le malware récupère discrètement le runtime sur `nodejs.org`, ce qui facilite son exécution sur des serveurs compromis.

### Comparaison avec des campagnes similaires

Cette approche des hackers nord-coréens rappelle la stratégie connue sous le nom de **Contagious Interview**, une opération où des outils de cyberespionnage avaient été déployés sous couvert de faux entretiens d’embauche. Ces tactiques ciblent des acteurs stratégiques, notamment dans les domaines technologiques et scientifiques.

## Prévenir les attaques liées à React2Shell

### Mesures de sécurité essentielles

Pour mitiger les risques associés à React2Shell et EtherRAT, voici quelques mesures pratiques :

1. **Mettre à jour React** : Assurez-vous que votre environnement React est conforme aux versions corrigées susceptibles de fermer cette vulnérabilité critique.
2. **Renforcer les systèmes Linux** : Évitez les ouvertures inutiles dans les systèmes qui peuvent permettre des mécanismes de persistance malveillants.
3. **Surveiller le réseau** : Implémentez des outils de monitoring avancés pour détecter des comportements suspects associés à EtherRAT et autres malwares.
4. **Rester informé des tactiques APT** : Les groupes de menaces avancés comme ceux liés à l’État nord-coréen innovent constamment. La veille stratégique est cruciale pour anticiper leurs attaques.

### Évolutions à surveiller

La sophistication des malwares utilisant des technologies comme les contrats intelligents Ethereum pourrait marquer un tournant critique dans la manière dont les cyberattaques sont conçues. Les architectures basées sur React et Next.js doivent être protégées en amont contre les menaces croissantes pesant sur des frameworks largement utilisés.

## À retenir

La faille **React2Shell** représente un grave risque pour les développeurs et administrateurs travaillant avec React Server Components. En suivant les recommandations de mise à jour et en restant vigilants face aux tactiques employées par des groupes tels que ceux liés à l'État nord-coréen, il est possible de réduire considérablement l’impact de ce type de cybermenace.

[source](https://www.techradar.com/pro/security/maximum-severity-react2shell-flaw-exploited-by-north-korean-hackers-in-malware-attacks)