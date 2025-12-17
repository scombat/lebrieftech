---
title: "Des systèmes AWS ciblés par une attaque de cryptominage exploitant des identifiants IAM détournés"
seoTitle: "Protégez vos identifiants IAM AWS contre le cryptominage"
seoDescription: "Une attaque ciblant AWS a exploité des identifiants IAM détournés pour miner de la cryptomonnaie. Découvrez les bonnes pratiques de sécurité."
datePublished: Wed Dec 17 2025 17:25:02 GMT+0000 (Coordinated Universal Time)
cuid: cmjaa7xov000o02l19wsyedla
slug: systemes-aws-ciblees-par-attaque-de-cryptominage
canonical: https://www.techradar.com/pro/security/aws-systems-targeted-by-crypto-mining-scam-using-hijacked-iam-credentials

---

# Des systèmes AWS ciblés par une attaque de cryptominage exploitant des identifiants IAM détournés

## TL;DR
- Une campagne de cryptominage a exploité des identifiants IAM AWS compromis pour déployer des ressources cloud à grande échelle.
- Les attaquants ont lancé des instances EC2 optimisées GPU et des conteneurs malveillants via ECS Fargate.
- AWS recommande notamment l'utilisation de l'authentification multi-facteurs (MFA) et des permissions minimales pour renforcer la sécurité.
- La gestion sécurisée des identifiants IAM est désormais incontournable pour les entreprises opérant sur le cloud.

## Contexte et pertinence

En décembre 2025, Amazon Web Services (AWS) a confirmé avoir identifié une campagne de cryptojacking exploitant des identifiants IAM (Identity and Access Management) compromis. Bien que rapidement neutralisée, cette attaque met en lumière la manière dont des infrastructures malveillantes peuvent être implantées avec une vitesse et une ampleur inquiétantes.

Dans cette attaque, les systèmes AWS eux-mêmes n’ont pas été directement compromis. Les auteurs ont plutôt profité de mauvaises pratiques de gestion des permissions et des identifiants par les clients AWS. Cette réalité souligne l’importance cruciale de renforcer la sécurité IAM pour minimiser les risques liés aux services cloud.

## Détails de l'attaque

L’attaque a été détectée en novembre 2025 via le service AWS GuardDuty. Plusieurs comptes AWS présentant des comportements inhabituels ont permis aux ingénieurs de découvrir l’exploitation de clés IAM volées. Ces identifiants donnaient aux attaquants un accès étendu aux ressources AWS, leur permettant de :

- Lancer des groupes EC2 auto-scaling consommant massivement les GPU.
- Déployer des conteneurs malveillants via Amazon ECS Fargate.
- Créer de nouveaux utilisateurs IAM avec des droits élevés.
- Activer la protection contre l’arrêt des instances pour prolonger l’exploitation.

### Déroulement technique : tactiques des attaquants

#### AWS ECS et Docker Hub
Les attaquants ont injecté des images contaminées hébergées sur Docker Hub. Ces conteneurs, déployés via le service ECS Fargate, exécutaient des mineurs de cryptomonnaie de manière transparente.  

#### AWS EC2 et GPU
Les ressources GPU haute puissance ont été activement ciblées via des modèles de lancement optimisés au sein d'instances EC2. Ces instances étaient configurées pour maximiser le rendement du cryptominage.

#### Lambda et IAM
Outre l’utilisation classique des ressources, les attaquants ont aussi déployé des fonctions Lambda accessibles publiquement, ouvrant la voie à des attaques futures et multipliant les points d'entrée potentiels.

Tous ces déploiements étaient réalisés en quelques minutes, démontrant une précision et une efficacité remarquable dans l’exploitation de comptes AWS compromis.

## Recommandations de sécurité pour les identifiants IAM

Suite à cet incident, AWS a rappelé les meilleures pratiques pour sécuriser les identifiants IAM et atténuer les risques :

1. **Adopter des identifiants temporaires**  
   Les clés d’accès temporaires limitent les possibilités d’exploitation prolongée par des attaquants.
   
2. **Activer l’authentification multi-facteurs (MFA)**  
   L'utilisation de MFA (Multi-Factor Authentication) complexifie significativement les tentatives de détournement.

3. **Appliquer le principe du moindre privilège**  
   Les permissions doivent être réduites au strict nécessaire pour les rôles et utilisateurs. Cela limite la portée d'une compromission.

4. **Auditer régulièrement les comptes et les autorisations**  
   La détection proactive des anomalies et des configurations excessivement permissives est essentielle.

Ces mesures, combinées à un monitoring continu des activités sur les comptes, permettent de renforcer considérablement la sécurité des environnements AWS.

## Risques pour les entreprises

Cette attaque met en lumière les risques liés à une gestion approximative des identifiants IAM. Les entreprises doivent prendre conscience de plusieurs impacts potentiels :

- **Impact financier** : L’exploitation non autorisée des ressources cloud, telles que les instances EC2 ou ECS, peut entraîner des coûts significatifs.
- **Exposition accrue** : Une mauvaise gestion des permissions IAM expose l’entreprise à des attaques répétées et à des scénarios d’exploitation multiples.
- **Perte de confiance** : Pour les entreprises reposant sur l’infrastructure AWS, une perception de faiblesse peut nuire à leur réputation auprès des partenaires et clients.

La sécurisation des identifiants IAM n’est pas une option, mais une nécessité au sein des environnements cloud. L’absence de règles strictes en matière d’accès peut rapidement devenir un point d’entrée pour des campagnes malveillantes.

## À retenir

Le cryptojacking ciblant les systèmes AWS est un exemple frappant des dangers du cloud mal sécurisé. La gestion des identifiants IAM est une pierre angulaire de toute stratégie de défense. En résumé :

- Adoptez le MFA sur tous les comptes et niveaux d’accès.
- Privilégiez les permissions minimales strictes.
- Surveillez en permanence les activités inhabituelles sur votre infrastructure.

Les entreprises doivent se saisir de ces exemples pour renforcer la cyberrésilience de leurs systèmes cloud face aux menaces actuelles et futures.

[source](https://www.techradar.com/pro/security/aws-systems-targeted-by-crypto-mining-scam-using-hijacked-iam-credentials)