---
title: "Comment une faille sur Mintlify a impacté Discord et d'autres entreprises"
seoTitle: "Comprendre une attaque supply-chain affectant Discord et Mintlify"
seoDescription: "Analyse approfondie d'une attaque sur la chaîne d'approvisionnement, affectant Discord, X et Vercel via une faille XSS sur Mintlify."
datePublished: Thu Dec 18 2025 21:38:58 GMT+0000 (Coordinated Universal Time)
cuid: cmjbyqc7y000202ky777ibpo2
slug: attaque-supply-chain-discord-mintlify
canonical: https://gist.github.com/hackermondev/5e2cdc32849405fff6b46957747a2d28

---

# Comment une faille sur Mintlify a impacté Discord et d'autres entreprises

## TL;DR

- Une vulnérabilité XSS dans Mintlify, découverte par un jeune chercheur en sécurité, a permis l'injection de scripts malveillants via des fichiers SVG.
- Discord, X (anciennement Twitter), Vercel et d'autres entreprises ont été touchés.
- Les correctifs ont été rapidement déployés pour combler la faille.
- Cette attaque illustre les risques critiques liés à la chaîne d'approvisionnement logicielle.

## Qu'est-ce qu'une attaque supply-chain ?

Une attaque sur la chaîne d'approvisionnement, ou attaque "supply-chain", cible les maillons essentiels impliqués dans le développement ou la distribution d'un produit logiciel. Ces attaques exploitent les vulnérabilités des services, outils ou bibliothèques utilisés par plusieurs entreprises, mettant en péril des systèmes interconnectés.

Dans un tel contexte, les plateformes communes, comme celles utilisées pour l'hébergement ou la gestion de documentations et de contenus, deviennent des cibles stratégiques. Frapper un maillon de la chaîne revient parfois à compromettre des dizaines, voire des centaines d'acteurs dépendants de celui-ci.

L'incident de sécurité sur Mintlify, une plateforme de documentation basée sur l'IA, illustre bien ces risques systémiques.

## La faille critique chez Mintlify

Mintlify est une solution populaire permettant aux entreprises de créer facilement des documentations dynamiques et adaptées grâce à l'intelligence artificielle. Elle est utilisée par des organisations de renom, telles que Discord, X, et Vercel.

En novembre 2025, "Daniel", un chercheur en sécurité âgé de 16 ans connu sous le pseudonyme hackermondev, a découvert une vulnérabilité critique dans la plateforme Mintlify. Cette faille impliquait l'exécution non autorisée de scripts malveillants via des fichiers SVG. Les fichiers SVG, au-delà de leur rôle initial de format vectoriel, peuvent intégrer du code JavaScript. Si ce code est exécuté sans contrôle strict, il devient possible de mener des attaques XSS (Cross-Site Scripting).

### Détails techniques de la vulnérabilité

La faille concernait deux principaux points d'entrée dans la plateforme Mintlify :
1. **L'endpoint `/_mintlify/markdown/`** : Ce point d'accès ne vérifiait pas correctement l'origine, bien qu'il ne permette pas directement l'exécution de scripts malveillants.
2. **L'endpoint `/_mintlify/static/`** : Ce point d'accès, en revanche, autorisait l'accès à des fichiers hébergés sur n'importe quel sous-domaine Mintlify.

En exploitant la permissivité du second endpoint, Daniel a découvert qu'il pouvait insérer un fichier SVG malveillant contenant des scripts JavaScript. Une fois le fichier chargé depuis un sous-domaine spécifique de Mintlify et ouvert, le code JavaScript était exécuté, créant ainsi une faille critique sur les plateformes affectées.

## Les entreprises touchées

La vulnérabilité a impacté plusieurs entreprises majeures, notamment :

- **Discord** : Ayant récemment migré ses documentations vers Mintlify, Discord a été l'une des premières victimes de cette attaque. Cette migration a été effectuée le 7 novembre 2025. Peu de temps après, la faille a été exploitée.
- **X (anciennement Twitter)** : En tant qu’utilisateur de la plateforme Mintlify pour sa documentation technique, X a également été exposé.
- **Vercel et Cursor** : Ces deux entreprises, dépendant de Mintlify pour leurs documentations, ont également été potentiellement vulnérables.

Les risques associés à l'attaque incluaient :
- Le vol d'identifiants sensibles.
- Des accès non autorisés aux comptes des utilisateurs et des ingénieurs.
- La compromission potentielle de services ou outils tiers.

## Conséquences de cette attaque

Un aspect clé mis en lumière par cet incident est l'impact très large que peut avoir une faille de sécurité au sein d'une chaîne d'approvisionnement logicielle. Les entreprises hébergeant leurs documentations sur Mintlify ont été effectivement exposées à des risques critiques, mettant en danger des données sensibles de leurs utilisateurs.

Ces failles présentent un risque particulièrement préoccupant : elles permettent à des acteurs malveillants de s'insérer dans les rouages complexes des écosystèmes numériques, compromettant plusieurs entités via une vulnérabilité centrale. Dans un monde où les plateformes mutualisées sont omniprésentes, le niveau de sécurité d'un seul fournisseur peut affecter des milliers d'utilisateurs finaux.

## Réactions des acteurs impliqués

### Discord

Quand Discord a appris l'existence de cette faille le 7 novembre 2025, l'entreprise a immédiatement pris des mesures pour limiter les dommages. Elle a fermé sa documentation alimentée par Mintlify pendant environ deux heures afin d'en analyser les risques et d'appliquer les correctifs nécessaires. Par la suite, elle a fait le choix de revenir à son ancienne solution interne de documentation.

### Mintlify

La plateforme Mintlify s'est montrée réactive face à cette faille. Alertée directement par les chercheurs en sécurité via Slack, elle a rapidement collaboré avec eux. Mintlify a déployé des patchs pour corriger la vulnérabilité et invalider les vecteurs actifs d'attaque.

### Résultats de la collaboration

Grâce à cette coopération proactive entre Mintlify et les chercheurs, y compris hackermondev et son collègue xyzeva, plusieurs vecteurs critiques de l'attaque ont été identifiés et corrigés rapidement. Les efforts des chercheurs ont été récompensés grâce à des programmes de bug bounty : ils ont reçu un total d'environ 11 000 $ pour leurs signalements. Discord, Mintlify et d'autres entreprises touchées ont contribué à cette récompense.

## Leçons à tirer de cette attaque

Cette affaire souligne les dangers des compromis dans une chaîne d'approvisionnement logicielle. Les leçons principales de cet incident incluent :

1. **Audits de sécurité renforcés** : Les plateformes qui centralisent des services pour plusieurs entreprises doivent être soumises à des audits de sécurité rigoureux pour identifier les vulnérabilités potentielles avant leur exploitation.
2. **Responsabilité collective** : Les entreprises qui choisissent d'utiliser des outils tiers doivent établir des processus pour surveiller activement les failles, en collaboration étroite avec les fournisseurs.
3. **Communication rapide** : La réactivité des entreprises touchées, comme Discord et Mintlify, montre l'importance d'une communication efficace en cas de crise, permettant de mitiger rapidement les risques.
4. **Bug bounty et recherche éthique** : Encourager la recherche proactive et rémunérer les chercheurs en sécurité permet de détecter et corriger les failles avant qu'elles ne soient exploitées à grande échelle.

L'incident Mintlify est une piqûre de rappel pour les développeurs et ingénieurs : bien que les solutions tierces offrent souvent des avantages en termes de coûts et rapidité de mise en œuvre, elles doivent être adoptées avec une attention soutenue vis-à-vis de leur sécurité.

[source](https://gist.github.com/hackermondev/5e2cdc32849405fff6b46957747a2d28)