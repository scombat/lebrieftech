---
title: "PHP 8.5.0 : Les nouveautés à découvrir"
seoTitle: "PHP 8.5.0 : Nouveautés et améliorations"
seoDescription: "Découvrez les nouveautés de PHP 8.5.0, y compris l'opérateur '|>', les attributs améliorés et des fonctionnalités enrichies pour les développeurs PHP."
datePublished: Fri Nov 21 2025 16:06:23 GMT+0000 (Coordinated Universal Time)
cuid: cmi91ymu4000202juc6j6g7me
slug: php-8-5-released
canonical: https://lwn.net/Articles/1047429/

---

```markdown
# PHP 8.5.0 : Les nouveautés à découvrir

## TL;DR

- Introduction de l'opérateur `|>`, simplifiant la manipulation de données dans les chaînes d'appels.
- Nouveaux attributs de fonction, comme `#[\NoDiscard]`, améliorant la lisibilité et la fiabilité du code.
- Diverses améliorations, notamment dans la gestion des constantes et l'ajout de nouvelles fonctions utiles.

## Un nouvel opérateur révolutionnaire : '|>'

La version 8.5.0 de PHP introduit une fonctionnalité très attendue par la communauté : l'opérateur `|>`. Également connu sous le nom de "pipe", cet opérateur est largement utilisé dans d'autres langages de programmation pour simplifier les chaînes d'appels. Son objectif est de rendre le code plus lisible et fluide dans des contextes où des transformations successives de données sont nécessaires.

### Fonctionnement de l'opérateur `|>`

L'opérateur `|>` permet de transmettre le résultat d'une expression comme premier paramètre d'une autre, tout en réduisant la verbosité du code. Par exemple, dans des versions antérieures de PHP, un pipeline nécessitait une imbrication de fonctions, ce qui pouvait nuire à la lisibilité :

```php
$result = strtoupper(trim(htmlspecialchars($input)));
```

Avec l'opérateur `|>`, le même code devient beaucoup plus clair :

```php
$result = $input 
    |> htmlspecialchars($$)
    |> trim($$)
    |> strtoupper($$);
```

Dans cet exemple, la variable spéciale `$$` représente le résultat de l’expression précédente, passée automatiquement comme argument au prochain appel. Ce style de codage devient particulièrement efficace lorsqu'une chaîne complexe de transformations doit être appliquée.

### Cas d'usage

L'opérateur `|>` est idéal pour les situations où une suite de transformations doit être réalisée sur une donnée ou un résultat intermédiaire. Ce nouveau paradigme encourage un code plus lisible et fonctionnel, limitant les erreurs liées à l'imbrication excessive.

Son adoption s'inscrit dans l'objectif de PHP de moderniser le langage et d'apporter des concepts qui ont prouvé leur efficacité dans d'autres environnements comme JavaScript ou Python.

---

## Les nouveaux attributs de fonction

PHP continue à enrichir ses capacités avec l’ajout de nouveaux attributs, qui permettent de fournir des métadonnées directement dans le code. Cela améliore la lisibilité et les comportements spécifiques sans nécessiter de documentation externe ou de conventions non standardisées.

### Focus sur `#[\NoDiscard]`

Parmi ces nouveaux attributs, `#[\NoDiscard]` se distingue comme ayant un impact immédiat sur les bonnes pratiques des développeurs. Lorsqu’il est appliqué à une fonction ou une méthode, cet attribut indique que le retour de celle-ci ne doit pas être ignoré. Cela évite qu'une fonction importante (comme une validation, une transformation ou une vérification) ne soit appelée inutilement sans traitement.

Exemple d'utilisation :

```php
#[\NoDiscard]
function calculateTax(float $amount): float {
    return $amount * 0.2;
}

// Utilisation correcte
$tax = calculateTax(100.0);

// Utilisation incorrecte (le compilateur pourra émettre un avertissement)
calculateTax(100.0);
```

### Documentation et introspection simplifiée

Ces nouveaux attributs contribuent également à une meilleure auto-documentation du code. Les outils comme les analyseurs statiques, les IDE modernes et les frameworks pourront tirer parti de ces informations, rendant le développement encore plus fiable.

---

## Autres ajouts importants dans PHP 8.5

En plus de l'opérateur `|>` et des nouveaux attributs, PHP 8.5.0 apporte d'autres fonctionnalités notables destinées à améliorer la vie des développeurs.

### Améliorations sur les constantes

PHP 8.5 améliore la gestion des constantes de classe. Vous pouvez désormais définir des constantes par défaut plus simplement ou les redéfinir dans des sous-classes avec moins de contraintes. Ce changement améliore la modularité des projets complexes.

Exemple :

```php
class BaseClass {
    public const DEFAULT_LIMIT = 10;
}

class SubClass extends BaseClass {
    public const DEFAULT_LIMIT = 20;
}
```

### Nouvelles fonctions

De nouvelles fonctions utilitaires ont été intégrées dans le langage, comme celles facilitant la gestion des tableaux ou encore des chaînes de caractères. Ces ajouts sont conçus pour réduire le besoin de bibliothèques tierces ou de solutions "fait maison", tout en standardisant des fonctionnalités communes.

---

PHP 8.5.0 marque une évolution importante pour le langage et s’inscrit dans une démarche continue d’amélioration de la productivité des développeurs. Ces fonctionnalités — à la fois orientées performance et lisibilité — reflètent la volonté de PHP de rester un choix pertinent dans le paysage du développement moderne.
```

[source](https://lwn.net/Articles/1047429/)