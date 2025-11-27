---
title: "Les fichiers Blender corrompus propagent le malware StealC"
seoTitle: "Les fichiers Blender corrompus propagent le malware StealC: vigilance requise"
seoDescription: "Des fichiers modèles Blender corrompus sur CGTrader exploitent la fonctionnalité Auto Run pour propager le malware voleur StealC. Apprenez à vous protéger."
datePublished: Thu Nov 27 2025 20:36:19 GMT+0000 (Coordinated Universal Time)
cuid: cmihw8vng000002jl7g4z0z3y
slug: fichiers-blender-corrompus-propagent-malware-stealc
canonical: https://www.techradar.com/pro/security/malicious-blender-model-files-deliver-stealc-infostealing-malware

---

# Les fichiers Blender corrompus propagent le malware StealC

## TL;DR

- Des fichiers `.blend` corrompus exploitent la fonctionnalité Auto Run de Blender pour propager le malware StealC.
- StealC cible les navigateurs, les wallets de cryptomonnaie, les applications de messagerie et les clients VPN.
- Les fichiers malveillants sont partagés via la plateforme CGTrader.
- Une infrastructure utilisant des domaines Cloudflare Workers est employée pour masquer les actions malveillantes.
- Il est essentiel de désactiver Auto Run dans Blender et d’éviter les fichiers provenant de sources douteuses.

## Qu'est-ce que le malware StealC ?

StealC est un malware voleur d'informations bien connu dans l'univers de la cybersécurité. Il se distingue par sa capacité à exfiltrer un large éventail de données personnelles et sensibles. Conçu pour fonctionner de manière discrète, il cible un nombre impressionnant de plateformes et d'applications utilisées au quotidien :

- **Navigateurs web** : vol de données de connexion, cookies et historiques de navigation sur plus de 20 navigateurs.
- **Cryptomonnaies** : collecte les informations de plus de 100 extensions de wallets de cryptomonnaies et pénètre également une quinzaine d'applications de wallets autonomes.
- **Applications de messagerie et VPN** : il extrait des données sensibles de la plupart des applications de messagerie instantanée et des clients VPN.

L'étendue des cibles montre le danger que représente StealC, en particulier pour les utilisateurs qui s'appuient massivement sur les services numériques pour gérer leurs finances ou autres données personnelles.

## Comment les hackers exploitent Blender

### La méthode d'infiltration via CGTrader

Blender, logiciel populaire pour la création 3D, prend actuellement la place centrale dans une campagne d'attaques menée par des hackers russes. En diffusant des fichiers `.blend` corrompus sur CGTrader, une plateforme très connue pour l'échange de modèles 3D, les cybercriminels parviennent à infiltrer leurs victimes sans éveiller immédiatement de soupçons.

Ces fichiers contiennent des scripts Python malveillants cachés. Une fois que l'utilisateur ouvre un fichier `.blend` infecté, ces scripts utilisent les fonctionnalités de Blender pour télécharger un fichier malveillant (souvent un fichier ZIP) depuis une infrastructure basée sur Cloudflare Workers. Ce fichier contient le malware StealC.

### L'exploitation de la fonctionnalité Auto Run

Le point d'entrée principal de l'attaque réside dans la fonctionnalité Auto Run de Blender. Cette option, activée par défaut, permet aux fichiers `.blend` d'exécuter automatiquement des scripts Python lorsqu'ils sont ouverts. Si des scripts personnalisés sont souvent utiles pour des animations complexes ou des améliorations d'interface utilisateur, Auto Run ouvre également une porte potentielle aux malwares intégrés directement dans de tels fichiers.

Les fichiers malveillants sont conçus de manière à tirer parti de ce fonctionnement : les utilisateurs n’ont même pas besoin de donner leur accord ou d’exécuter intentionnellement des scripts pour que le malware entre en action. Cela fait d'Auto Run une faille critique dans ce contexte.

### Une évasion via Cloudflare Workers

Pour rendre leur opération encore plus discrète, les hackers utilisent l’infrastructure Cloudflare Workers. Cela leur permet de télécharger les scripts malveillants depuis des adresses qui semblent légitimes, déjouant potentiellement les protections de sécurité classiques comme les pare-feux réseau ou les systèmes de détection d’intrusion.

## Mesures pour se protéger des fichiers corrompus

Cette attaque révèle des failles importantes dans l'utilisation sécurisée de Blender. Heureusement, il est possible de réduire considérablement les risques en adoptant les pratiques suivantes :

1. **Désactiver la fonctionnalité Auto Run dans Blender** :  
   Rendez-vous dans les paramètres de Blender (accessible via "Préférences") et désactivez l'exécution automatique des scripts via l’option Auto Run.

2. **Être critique sur la provenance des fichiers `.blend` téléchargés** :  
   Évitez de récupérer des fichiers de modèles 3D provenant de plateformes, de sites web ou de sources en ligne peu fiables ou non vérifiées.

3. **Installer et maintenir un logiciel antivirus fiable** :  
   Utilisez une solution de protection performante pouvant détecter et empêcher automatiquement l’exécution de fichiers malveillants.

4. **Rester informé sur les vulnérabilités connues** :  
   Assurez-vous de suivre les recommandations de sécurité des développeurs de Blender, ainsi que les rapports sur les cybermenaces publiés par des organisations reconnues.

Ces mesures simples, mais essentielles, permettent de réduire le risque d’exposition à ce type d’attaques et de protéger vos données sensibles.

## Ce qu'il faut retenir sur l'attaque via Blender

L’exploitation de Blender dans cette campagne illustre une fois de plus à quel point les plateformes open source, malgré leurs atouts indéniables, peuvent devenir la cible des cybercriminels. En intégrant des scripts malveillants dans des fichiers apparemment anodins, les hackers parviennent à contourner les mesures de sécurité traditionnelles et à accéder à des données critiques.

La meilleure défense face à ce type de menace est de rester alerte et informé. Désactiver les fonctionnalités superflues comme Auto Run, télécharger uniquement des fichiers de sources fiables et maintenir un environnement sécurisé grâce à des outils de sécurité à jour sont autant de pratiques indispensables pour travailler en toute confiance avec Blender et d’autres logiciels similaires.

[source](https://www.techradar.com/pro/security/malicious-blender-model-files-deliver-stealc-infostealing-malware)