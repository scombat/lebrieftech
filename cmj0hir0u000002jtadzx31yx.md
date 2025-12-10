---
title: "Modernisation de la validation des certificats HTTPS"
seoTitle: "Modernisation de la validation des certificats HTTPS : Fin des méthodes obsolètes"
seoDescription: "Découvrez comment l'industrie des certificats HTTPS élimine les anciennes méthodes de validation des domaines, renforçant ainsi la sécurité du web."
datePublished: Wed Dec 10 2025 20:51:42 GMT+0000 (Coordinated Universal Time)
cuid: cmj0hir0u000002jtadzx31yx
slug: modernisation-validation-certificats-https-methodes-obsoletes
canonical: http://security.googleblog.com/2025/12/https-certificate-industry-phasing-out.html

---

# Modernisation de la validation des certificats HTTPS

## TL;DR

- 11 méthodes de validation des domaines désuètes pour les certificats HTTPS seront supprimées d'ici 2028.  
- Ces méthodes anciennes, comme les mails ou les recherches WHOIS, sont vulnérables aux attaques.  
- Les nouvelles pratiques reposent sur des techniques automatisées et cryptographiquement sécurisées, comme le protocole ACME.  
- Ce changement vise à simplifier la gestion des certificats tout en renforçant la sûreté des connexions web.  

## Pourquoi moderniser les validations de domaines ?

La validation des domaines garantit que les certificats HTTPS, indispensables pour sécuriser les communications sur internet, sont délivrés uniquement au propriétaire légitime d’un site. Cette étape critique permet de prévenir les attaques malveillantes, comme la prise de contrôle de domaines à des fins frauduleuses.

Historiquement, certaines des méthodes de validation reposaient sur des approches indirectes telles que les courriers électroniques, les recherches WHOIS ou les vérifications téléphoniques. Bien que fonctionnelles à leur époque, ces méthodes se sont révélées vulnérables à plusieurs types d’abus. Les progrès technologiques et les attaques de plus en plus sophistiquées ont mis en avant leurs limites.

Google, via son programme Chrome Root, fait évoluer les standards en abandonnant ces méthodes anciennes au profit d'infrastructures modernisées et automatisées, plaçant la sécurité au cœur des pratiques de validation des certificats.

## Les méthodes obsolètes remplacées

### Quelles étaient ces anciennes pratiques ?

Les anciennes méthodes de Domain Control Validation (DCV) reposaient principalement sur des techniques indirectes pour prouver la possession d’un domaine. Voici les principaux exemples :  
- **Emails et recherches WHOIS** : validation via l’envoi d’emails aux contacts listés sur WHOIS ou CAA.  
- **Appels téléphoniques** : vérifications basées sur des numéros de téléphone associés à un domaine.  
- **Recherches inversées** : vérifications liées aux adresses IP ou aux données associées à un domaine.  

Ces techniques, bien qu’utiles à leur époque, sont aujourd’hui dépassées. Elles présentent des vulnérabilités exploitables par des acteurs malveillants (phishing, man-in-the-middle, falsification de données).

### Quelles sont les alternatives modernes ?

Les approches modernes privilégient l’automatisation et les mécanismes cryptographiques. Parmi elles, le protocole **ACME** ([RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555)) s'impose comme la norme :  
- **Automatisation** : ACME permet une communication directe entre l'autorité de certification (CA) et le serveur, réduisant la surcharge manuelle et les erreurs humaines.  
- **Défi-réponse (Challenge-Response)** : Ces mécanismes impliquent que le propriétaire d'un domaine effectue des actions spécifiques pour prouver sa possession, comme la configuration d’un enregistrement DNS ou l’hébergement d’un fichier à une URL précise.  

Ces alternatives permettent une vérification rapide, fiable et sécurisée, minimisant les risques d’usurpation.

## Impact global sur la sécurité du web

L’abandon des méthodes vulnérables et l’adoption de standards modernisés renforceront la sécurité globale des connexions basées sur HTTPS. Ces changements permettent de réduire les risques liés aux protocoles faibles et sécurisent le processus de délivrance des certificats.

### Une meilleure gestion des certificats

Les nouvelles méthodes offrent une efficacité accrue dans la gestion du cycle de vie des certificats :
- **Renouvellement simplifié** grâce à l’automatisation.  
- **Moindre risque de fraude** : les acteurs non légitimes auront plus de difficultés à obtenir des certificats valides.  
- **Sécurité renforcée** : en s’appuyant sur des standards cryptographiques, la validation devient plus robuste face aux attaques.  

### Une confiance accrue dans l’écosystème HTTPS

Les utilisateurs finaux bénéficieront directement de ces évolutions, grâce à des connexions plus sûres et à une réduction des risques liés aux certificats compromis. Pour les entreprises, c’est l’assurance d’un web plus fiable, essentiel pour les interactions en ligne.

## Quelles actions pour les professionnels ?

La transition vers ces nouvelles normes ne se fera pas instantanément. Elle nécessite une préparation technologique de la part des professionnels, notamment les équipes de DevOps, SecOps et administrateurs système.

### Étapes clés à suivre

1. **Audit des systèmes en place** : Évaluer les pratiques existantes pour identifier les dépendances aux méthodes obsolètes.  
2. **Migration vers des outils conformes** : Mettre en place des solutions comme l’ACME pour automatiser la validation de domaine et la gestion des certificats.  
3. **Formation et sensibilisation** : S’assurer que les équipes techniques sont préparées à gérer ces changements avec les compétences requises.  
4. **Surveillance proactive** : Mettre en place une veille sur les mises à jour des exigences TLS et s'assurer de la conformité avant mars 2028.  

### Délais et suivi 

Bien que le processus soit en cours, l’objectif final est fixé à mars 2028, offrant un délai raisonnable aux entreprises pour s’adapter. Cependant, une transition proactive peut éviter les risques associés aux délais serrés ou aux non-conformités.

## À surveiller

- Les évolutions des [exigences de base TLS](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) définies par le CA/Browser Forum.  
- Les impacts potentiels pour les entreprises qui dépendent encore de pratiques anciennes.  
- L’implémentation croissante des protocoles ACME et leur adoption au sein des outils de gestion DNS modernes.

## À retenir

La modernisation des pratiques de validation des certificats HTTPS marque une étape significative pour renforcer la sécurité de l’internet. En éliminant les méthodes obsolètes, jugées vulnérables, et en adoptant des standards automatisés, l’industrie des certificats promet un écosystème plus sûr, fiable et adaptatif. Pour les professionnels techniques, ces évolutions impliquent une adaptation stratégique et technologique, essentielle pour rester conforme et profiter des avantages d’un web sécurisé.

Sources :
- [Google Online Security Blog](http://security.googleblog.com/2025/12/https-certificate-industry-phasing-out.html)

[source](http://security.googleblog.com/2025/12/https-certificate-industry-phasing-out.html)