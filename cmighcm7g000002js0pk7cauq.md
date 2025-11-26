---
title: "Kyverno 1.16 : Nouvelles avancées pour Kubernetes et intégration des politiques CEL"
seoTitle: "Découvrez Kyverno 1.16 : Nouvelles avancées pour Kubernetes"
seoDescription: "Kyverno 1.16 propose des politiques innovantes, des améliorations en observabilité et le SDK Kyverno. Optimisez la gestion avec CEL et le serveur Authz !"
datePublished: Wed Nov 26 2025 20:51:33 GMT+0000 (Coordinated Universal Time)
cuid: cmighcm7g000002js0pk7cauq
slug: kyverno-release-1-16-innovations-politiques-kubernetes
canonical: https://www.cncf.io/blog/2025/11/26/announcing-kyverno-release-1-16/

---

# Kyverno 1.16 : Nouvelles avancées pour Kubernetes et intégration des politiques CEL

## TL;DR

- Kyverno 1.16 introduit les politiques basées sur CEL pour une meilleure expressivité et validation des règles dans Kubernetes.
- Amélioration de l’observabilité avec une gestion plus granulaire des exceptions.
- Nouveau SDK Kyverno pour simplifier l’intégration et le développement des politiques.
- Lancement du serveur Authz, utile pour la validation des requêtes au niveau des services.

## Quelles sont les nouveautés de Kyverno 1.16 ?

La version 1.16 de Kyverno, un moteur de politique pour Kubernetes, marque une étape significative dans l'évolution de la gestion des politiques pour les environnements cloud-native. Kyverno 1.16 a introduit plusieurs fonctionnalités et optimisations qui rendent la définition, la gestion et l’application des politiques Kubernetes plus efficaces. Voici un aperçu des principales nouveautés :

- **Support des politiques basées sur CEL** : Kyverno intègre désormais les Common Expression Language (CEL) de Google, permettant aux utilisateurs de définir des politiques dynamiques et complexes sans avoir à écrire du code. Cela apporte une grande flexibilité pour exprimer des conditions et des validations directes, et améliore l’expérience des développeurs qui recherchent une manière plus simple et puissante de gérer leurs règles.
- **Observabilité améliorée** : La gestion des exceptions a été optimisée, offrant ainsi une meilleure traçabilité et une identification facilitée des points de friction lors de l’application des politiques.
- **Introduction du SDK Kyverno** : Le SDK simplifie le développement, les tests et l’intégration des politiques dans les workflows existants.
- **Serveur Authz** : Un composant clé pour la gestion des autorisations via une validation avancée des requêtes envoyées aux services Kubernetes.

Kyverno continue ainsi de repousser les limites en matière de sécurisation et optimisation de la gestion des environnements Kubernetes, en répondant aux besoins d'une communauté en constante évolution.

## Améliorations des politiques CEL

L'ajout de la prise en charge des politiques basées sur CEL dans Kyverno constitue une avancée stratégique majeure. Contrairement aux approches traditionnelles nécessitant l’écriture de scripts complexes ou l’utilisation de plusieurs outils externes, CEL permet de structurer les validations des politiques avec des expressions simples et puissantes, directement dans les fichiers YAML.

### Cas d'utilisation des politiques CEL

Les politiques CEL sont particulièrement utiles dans les contextes suivants :
- **Validation avancée des champs** : Par exemple, vous pouvez définir une règle pour vérifier des modèles spécifiques dans les noms de ressources.
- **Contrôles conditionnels** : L'utilisation d'opérateurs logiques avancés permet de prendre en charge des règles complexes sans ajouter de surcharge.
- **Conformité automatisée** : Maintenez les normes de votre organisation en vérifiant les étiquettes, annotations ou configurations globales sur plusieurs ressources.

Voici un exemple d'une politique basique utilisant CEL pour vérifier qu'une ressource dispose du label "environment" avec une valeur admissible :

```yaml
apiVersion: kyverno.io/v1
kind: ClusterPolicy
metadata:
  name: check-environment-label
spec:
  validationFailureAction: enforce
  rules:
  - name: validate-env-label
    match:
      resources:
        kinds:
        - Pod
    validate:
      message: "Le label 'environment' doit être défini sur 'prod' ou 'dev'."
      pattern:
        metadata:
          labels:
            environment: "prod|dev"
```

Grâce aux politiques CEL, les développeurs peuvent rapidement créer des règles qui s'intègrent naturellement dans leurs pipelines d'infrastructure, tout en maintenant une gestion robuste des politiques.

## Améliorations en observabilité et exceptions

Avec Kyverno 1.16, la gestion des exceptions et des violations dans l’application des politiques a été largement améliorée. Désormais, lorsqu'une politique échoue à valider une ressource, Kyverno fournit des informations beaucoup plus détaillées pour faciliter le diagnostic.

### Gestion affinée des exceptions

Une des principales évolutions est l'intégration de mécanismes permettant de spécifier des exceptions au niveau granulé. Par exemple, il est désormais possible d'exempter un ensemble de ressources spécifiques à certaines politiques. Cela est particulièrement utile dans les environnements complexes où certaines ressources peuvent nécessiter un traitement spécifique.

```yaml
apiVersion: kyverno.io/v1
kind: PolicyException
metadata:
  name: ignore-certain-resources
spec:
  match:
    resources:
      namespaces:
      - kube-system
  excludeRules:
  - validate-env-label
```

Avec ces changements, Kyverno simplifie la gestion des workloads Kubernetes tout en améliorant la conformité des politiques et en réduisant les risques d’erreur.

## Présentation du SDK Kyverno et serveur Authz

Kyverno 1.16 introduit un nouvel outil essentiel pour les utilisateurs avancés : le **SDK Kyverno**. Ce kit de développement logiciel est conçu pour tous ceux qui souhaitent intégrer plus efficacement Kyverno dans leurs projets ou développer des extensions personnalisées. Grâce au SDK, il devient facile de tester, déployer, ou ajuster les politiques au fur et à mesure des besoins spécifiques.

### Fonctions clés du SDK

- **Automatisation des tests de politiques** : Assurez-vous que vos configurations respectent les meilleures pratiques avant le déploiement.
- **Intégration fluide** : Utilisez le SDK pour connecter directement Kyverno à vos pipelines CI/CD.
- **Documentation et exemples** : Des bibliothèques et guides vous permettent de tirer pleinement parti des capacités offertes par Kyverno.

En complément, Kyverno 1.16 met à disposition un serveur Authz qui joue un rôle clé dans la validation des requêtes envoyées aux services Kubernetes. Cet outil ajoute une couche supplémentaire de sécurité et de contrôle. Par exemple, un administrateur peut définir des règles autorisant ou refusant des requêtes en fonction des rôles ou attributs des utilisateurs.

```yaml
apiVersion: kyverno.io/v1
kind: AuthzPolicy
metadata:
  name: validate-user-requests
spec:
  match:
    subjects:
      - users:
        - "team-lead"
    verbs:
    - get
    - list
  denyAction: reject
```

Avec ces nouveaux outils, Kyverno renforce la capacité des équipes à automatiser et gérer les autorisations complexes dans des environnements Kubernetes à grande échelle.

## Compatibilités et roadmap

Kyverno 1.16 continue d’évoluer pour couvrir un large éventail de cas d’utilisation. La version supporte pleinement Kubernetes 1.28, et s’intègre avec les principales solutions cloud-native grâce à son approche flexible.

### Roadmap à venir

Les contributions de la communauté sont toujours au centre de la stratégie de développement de Kyverno. Parmi les priorités à venir, on retrouve :
- Améliorer encore l'expérience utilisateur.
- Étendre les capacités d'intégration du SDK.
- Retravailler les performances pour des environnements Kubernetes très larges et complexes.

Ces avancées continueront de positionner Kyverno comme un acteur essentiel dans la gestion de politiques Kubernetes.

## Comment mettre à niveau vers Kyverno 1.16

Mettre à niveau vers Kyverno 1.16 est relativement simple grâce aux outils existants comme **Helm**. Voici comment procéder :

```bash
helm upgrade --install kyverno kyverno/kyverno -n kyverno --version 3.6.0
```

Assurez-vous de vérifier la compatibilité avec la version de Kubernetes que vous utilisez avant de procéder à la mise à jour. Il est recommandé de consulter la documentation officielle pour connaître les prérequis et les éventuelles étapes supplémentaires. L’équipe Kyverno propose en permanence des guides détaillés pour garantir une migration fluide vers les nouvelles versions.

En adoptant Kyverno 1.16, vous pourrez profiter des dernières avancées en matière de gestion des politiques Kubernetes. Le support des politiques CEL, les outils comme le SDK et le serveur Authz, ainsi que les améliorations d’observabilité en font une mise à niveau incontournable pour tout ingénieur ou administrateur Kubernetes.

[source](https://www.cncf.io/blog/2025/11/26/announcing-kyverno-release-1-16/)