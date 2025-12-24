---
title: "Renforcer la sécurité de la chaîne d'approvisionnement : Se préparer à la prochaine campagne de malware"
seoTitle: "Sécurité de la chaîne d'approvisionnement : préparez-vous aux campagnes de malware"
seoDescription: "Découvrez comment renforcer la sécurité des chaînes d'approvisionnement open source face aux campagnes comme Shai-Hulud grâce aux outils GitHub et npm."
datePublished: Wed Dec 24 2025 00:07:45 GMT+0000 (Coordinated Universal Time)
cuid: cmjj98xke000002jpekwobqsh
slug: securite-chaine-approvisionnement-campagnes-malware
canonical: https://github.blog/security/supply-chain-security/strengthening-supply-chain-security-preparing-for-the-next-malware-campaign/

---

# Renforcer la sécurité de la chaîne d'approvisionnement : Se préparer à la prochaine campagne de malware

## TL;DR

- Les chaînes d'approvisionnement open source sont vulnérables aux campagnes de malware sophistiquées comme Shai-Hulud.
- Ces attaques exploitent souvent des scripts malveillants et des comptes mainteneurs compromis pour collecter des secrets sensibles et perturber les workflows.
- GitHub et npm renforcent leurs mesures de sécurité avec l'authentification multifactorielle (MFA), l'adoption de l'OIDC et des politiques de publication plus strictes.
- Mainteneurs et utilisateurs doivent mettre en œuvre des pratiques de sécurité robustes : MFA, gestion des jetons et audits réguliers.

## Contexte et pertinence

Les logiciels open source sont devenus des bases essentielles de l'écosystème technologique mondial. Ils alimentent les applications modernes, mais cette omniprésence s'accompagne de menaces croissantes de compromission, notamment par des attaques ciblant les chaînes d'approvisionnement.

Une campagne récente de malware connue sous le nom de **Shai-Hulud** a mis en lumière la vulnérabilité de ces chaînes. Cette attaque a révélé des failles critiques liées à la compromission de comptes mainteneurs, à l'injection de scripts malveillants dans des processus d'installation automatisés, à l'extraction de secrets sensibles à partir des systèmes CI/CD, et à l'évolution rapide des techniques d'attaque pour déjouer les mesures de défense.

Face à ces défis croissants, GitHub et npm ont réagi en instaurant des mesures significatives visant à sécuriser les processus de publication, tandis que les mainteneurs et utilisateurs jouent un rôle fondamental dans cette lutte contre les menaces.

## Résumé de la campagne Shai-Hulud

### Première vague

La première vague de la campagne Shai-Hulud a ciblé directement des comptes mainteneurs compromis, introduisant des scripts malveillants dans les packages open source. Ces scripts étaient activés lors des installations des packages et servaient à exfiltrer des secrets critiques depuis les environnements CI/CD.

### Deuxième vague : Shai-Hulud 2.0

La seconde vague a montré une sophistication accrue du malware. Elle a inclus des tactiques de ciblage interconnecté pour exposer les credentials de multiples utilisateurs, ainsi que la mise en place de runners auto-hébergés permettant l'exécution de commandes à distance. Les attaquants ont également ajouté des payloads destructifs spécifiquement conçus pour l'escalade de privilèges.

Les stratégies employées comprenaient notamment :
- L'obfuscation des scripts malveillants utilisés lors de l'installation.
- La compromission des espaces de noms de confiance.
- La publication d'artefacts malveillants dans les workflows de développement.

Ces techniques montrent à quel point les menaces contre les chaînes d'approvisionnement open source sont sophistiquées et dynamiques.

## Initiatives de sécurité chez npm

Face à ces risques, GitHub et npm ont renforcé les mesures de protection pour minimiser les impacts des campagnes malware sur l'écosystème open source.

### Adoption massive de l'OIDC

GitHub a initié une migration vers OpenID Connect (OIDC) pour des milliers de packages npm. L'objectif est d'améliorer les processus de publication en remplaçant les mécanismes d'authentification statiques par des méthodes plus sécurisées. L'OIDC permet de réduire significativement les risques liés aux jetons volés ou compromis.

### Publication étagée avec validation MFA

Pour chaque mise à jour d'un package, une validation via une authentification multifactorielle (MFA) est désormais requise avant publication. Cela renforce les barrières contre les accès non autorisés.

### Extensibilité vers d'autres plateformes CI/CD

Ces initiatives ne se limitent pas à GitHub Actions ou GitLab. GitHub élargit le support de ses outils de sécurité vers des plateformes tierces pour garantir une couverture sécuritaire complète autour des processus CI/CD.

Ces mesures visent à bloquer les scripts malveillants aux points critiques des pipelines de développement, notamment les phases de publication et d'installation.

## Conseils pour les utilisateurs et mainteneurs

Les utilisateurs et mainteneurs doivent jouer un rôle actif dans la sécurisation des chaînes d'approvisionnement. Voici des recommandations concrètes pour renforcer la sécurité :

### Pour tous les utilisateurs

- **Activer une MFA robuste** pour protéger les comptes sur les plateformes telles que GitHub et npm. Privilégiez les méthodes de MFA résistantes au phishing (ex. : gestionnaires de clés).
- Définir une période d'expiration pour les tokens, associée à des politiques organisationnelles strictes.
- Effectuer des audits réguliers des autorisations pour identifier et révoquer les jetons et permissions inutilisés.
- Travailler dans des environnements isolés, tels que des conteneurs ou des machines virtuelles, pour réduire les risques.

### Pour les mainteneurs

- **Protéger les branches critiques** en activant des mécanismes de contrôle pour bloquer les commits non autorisés ou suspects.
- Remplacer tous les jetons statiques par des **méthodes de publication sécurisée basées sur OIDC**.
- Scanner fréquemment le code pour détecter et résoudre les failles de sécurité.
- Garantir la légitimité des artefacts publiés grâce à des attestations vérifiables.
- En cas de suspicions ou de compromission avérée, contacter immédiatement le [support GitHub](https://support.github.com/).

## Pour aller plus loin

Pour approfondir le sujet et renforcer vos propres pratiques de sécurité, voici des ressources utiles :

- [Plan de sécurisation de npm](https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/) : Les détails des initiatives de GitHub et npm pour protéger les chaînes d'approvisionnement.
- [Principes de sécurité pour npm (Open Source Security Foundation)](https://github.com/ossf/package-manager-best-practices/blob/main/published/npm.md#readme) : Recommandations et bonnes pratiques pour les mainteneurs.
- [Revue des dépendances](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review) : Outils pour analyser et sécuriser vos dépendances.

## Conclusion

Les campagnes de malware comme Shai-Hulud démontrent à quel point il est stratégique de renforcer la sécurité des chaînes d'approvisionnement dans l'open source. En réponse, GitHub et npm ont accéléré leurs efforts pour instaurer des pratiques de publication sécurisées et des mesures préventives. Cependant, protéger cet écosystème reste une responsabilité partagée : mainteneurs et utilisateurs doivent adopter des pratiques de sécurité rigoureuses, telles que la mise en place de MFA, l'audit des accès inutilisés et la sécurisation des pipelines de développement. Ces actions collectives sont essentielles pour parer aux menaces évolutives et garantir l'avenir du logiciel open source.

[source](https://github.blog/security/supply-chain-security/strengthening-supply-chain-security-preparing-for-the-next-malware-campaign/)