---
title: "La sécurité n'est pas une fonctionnalité, c'est une fondation"
seoTitle: "Comprendre pourquoi la sécurité est la base du développement logiciel"
seoDescription: "Découvrez comment Rust et Hyperlane permettent une sécurité intégrée dès le départ grâce à des pratiques „secure-by-default“ et des outils modernes."
datePublished: Sat Nov 29 2025 04:06:14 GMT+0000 (Coordinated Universal Time)
cuid: cmijrrcct000002l58cl1g4bp
slug: securite-comme-fondation-developpement
canonical: https://dev.to/member_8455d9df/security-is-not-a-feature-its-a-foundation-13g9

---

# La sécurité n'est pas une fonctionnalité, c'est une fondation

## TL;DR

- Considérer la sécurité comme un aspect fondamental du développement logiciel est indispensable pour prévenir les failles coûteuses.
- Les vulnérabilités telles que les injections SQL et le XSS restent très répandues dans les applications modernes.
- Rust et Hyperlane se distinguent par leurs principes de programmation sécurisée par défaut, limitant les erreurs humaines.
- Adopter une solide base technique et des outils modernes réduit significativement les risques de sécurité.

## Contexte et pertinence

Il y a une décennie, un incident majeur dans le développement d’un système de trading en ligne a mis en lumière l’importance cruciale de la sécurité informatique. Une simple injection SQL a permis à un hacker de voler une base de données contenant des informations sensibles sur les utilisateurs. La conséquence de cette brèche fut désastreuse : des pertes financières importantes pour l’entreprise, accompagnées d’une chute de sa réputation.

Cet exemple illustre parfaitement pourquoi la sécurité ne peut pas être considérée comme une option ou une addition post-développement. Celle-ci doit être un pilier fondamental dès la conception d’un logiciel. Grâce à des technologies de pointe comme Rust et l’environnement Hyperlane, il est désormais possible de programmer en suivant des principes « secure-by-default ». Ces avancées permettent de contrer les erreurs classiques qui ont coûté cher dans le passé et d'établir une base solide pour garantir la sécurité des systèmes.

## Erreurs courantes en développement logiciel

### 1. Injections SQL

Les injections SQL restent l'une des failles les plus connues et les plus exploitables. Cette vulnérabilité se produit lorsque les données utilisateur sont interprétées comme des commandes SQL, souvent en raison d’une concaténation de chaînes de caractères dans les requêtes. Cela donne aux attaquants la possibilité de manipuler les bases de données, voler des informations ou contourner les mécanismes de sécurité.

Prenons un exemple classique :

```sql
SELECT * FROM users WHERE username = 'John' AND password = 'mypassword';
```

Si une application n’utilise pas de protection adéquate et accepte des entrées malveillantes telle que :  
`' OR '1'='1`, la requête devient :

```sql
SELECT * FROM users WHERE username = '' OR '1'='1';
```

Cela permet à un attaquant de contourner une authentification et d’accéder à la base de données.

### 2. Cross-Site Scripting (XSS)

Le XSS se produit lorsque du contenu dynamique d’une application web inclut du code JavaScript malveillant. Ce script peut être injecté dans une page web et exécuté sur les navigateurs des utilisateurs qui consultent cette page. Cela donne la possibilité aux acteurs malveillants de voler des cookies de session, de falsifier des requêtes ou même d’altérer le comportement du site.

Sur des services exposés à des entrées utilisateur non vérifiées, comme des champs de commentaires ou des formulaires, le XSS est un danger récurrent.

### 3. Cross-Site Request Forgery (CSRF)

Les attaques CSRF manipulent les interactions utilisateur de manière sournoise, en effectuant des requêtes HTTP sur leur appareil à leur insu, souvent après leur authentification sur une autre plateforme. Ces actions indésirables peuvent aller jusqu’à effectuer des transactions frauduleuses ou modifier des paramètres critiques.

Ces attaques exploitent souvent les failles des systèmes qui n’ont pas mis en place une protection appropriée, comme des jetons CSRF ou des verifications systématiques des requêtes.

## Solutions modernes pour une sécurité par défaut

Les technologies récentes, telles que le langage Rust et le framework Hyperlane, offrent des moyens de construire des applications sécurisées dès leur conception. Intégrer ces solutions peut garantir une meilleure maîtrise des risques et des vulnérabilités.

### Protection contre les injections SQL avec `sqlx`

Rust propose l'utilisation de `sqlx`, un puissant ORM qui aide les développeurs à éviter les injections SQL. Parmi ses fonctionnalités clés :

- Utilisation de requêtes paramétrées, empêchant l’exécution de données utilisateur comme commandes.
- Validation de la syntaxe SQL lors de la compilation, réduisant les erreurs fréquentes.
- Sécurisation implicite du modèle de données grâce à une gestion stricte des types et des accès.

### Prévention efficace du XSS

Pour minimiser les risques de XSS, Rust dispose de moteurs de templates sécurisés comme **Tera** et **Askama**. Ces outils effectuent automatiquement un escaping des contenus HTML, empêchant l’injection malveillante. Les développeurs doivent toutefois éviter les désactivations inutiles de ces mécanismes de sécurité.

### Défense contre la CSRF

Les attaques CSRF peuvent être efficacement contrecarrées grâce à des pratiques et technologies modernes :

- Mise en place de jetons uniques après authentification.
- Validation systématique des jetons pour chaque opération critique.
- Utilisation des headers HTTP: le protocole `Strict-Transport-Security` peut empêcher des exploits de type man-in-the-middle (MITM).

### Sécurité renforcée de la mémoire

Rust se distingue particulièrement par son approche innovante de la gestion de mémoire : 

- En interdisant les débordements de mémoire et les références nulles, il élimine des failles classiques.
- Sa conception évite une large gamme de bugs exploitables liés à la mémoire.

Ce design garantit que les développeurs codent sans compromettre la sécurité des données manipulées.

## À surveiller / Risques

Malgré les avancées et les bénéfices des technologies modernes, aucune solution n’est totalement infaillible. Les développeurs restent responsables de la logique métier et doivent continuellement surveiller les nouveaux vecteurs d’attaques. Il est impératif de rester attentifs aux mises à jour des outils et aux bonnes pratiques en matière de sécurité.

## À retenir

La sécurité doit être la pierre angulaire du développement logiciel, intégrée dès les premiers stades du projet. Les langages robustes comme Rust et les environnements tels qu’Hyperlane apportent des solutions innovantes pour minimiser les risques. Ces outils permettent une programmation sécurisée par défaut, offrant aux développeurs un filet de sécurité tout en améliorant la qualité de leurs logiciels. Cependant, la vigilance humaine reste indispensable, car aucun outil ne peut garantir une protection absolue contre les menaces évolutives.

--- 

## Source
[Lien vers l'article original](https://dev.to/member_8455d9df/security-is-not-a-feature-its-a-foundation-13g9)

[source](https://dev.to/member_8455d9df/security-is-not-a-feature-its-a-foundation-13g9)