---
title: "Docker Model Runner intègre vLLM : des performances d’inférence optimisées"
seoTitle: "Docker Model Runner : intégration de vLLM pour une inférence AI ultra-rapide"
seoDescription: "Découvrez comment Docker Model Runner s’associe à vLLM pour offrir des capacités d’inférence AI à haut débit tout en simplifiant les flux de travail."
datePublished: Thu Nov 20 2025 13:52:28 GMT+0000 (Coordinated Universal Time)
cuid: cmi7hqk7l000802ky6zwq3xnc
slug: docker-model-runner-integration-vllm-inference
canonical: https://www.docker.com/blog/docker-model-runner-integrates-vllm/

---

# Docker Model Runner intègre vLLM : des performances d’inférence optimisées

## Qu’est-ce que vLLM ?

vLLM est un moteur d’inférence open source conçu pour exécuter des modèles de langage à grande échelle (LLMs, pour **Large Language Models**) avec des performances et une flexibilité exceptionnelles. Contrairement à d’autres moteurs d’inférence, vLLM se distingue par son approche innovante, notamment grâce à sa technologie **PagedAttention**. Ce mécanisme optimise l’utilisation de la mémoire GPU et accélère le traitement des requêtes, rendant vLLM particulièrement adapté pour des scénarios où les vitesses d'exécution sont cruciales.

En pratique, vLLM se révèle utile pour les développeurs et ingénieurs qui ont besoin d’exploiter la puissance des modèles génératifs comme GPT ou OPT sans compromis sur les performances. En combinant son architecture optimisée avec un support des formats modernes comme **safetensors**, vLLM offre des avantages concrets tant pour les chercheurs que pour les entreprises cherchant à intégrer les LLMs dans leurs solutions.

## Pourquoi plusieurs moteurs d'inférence ?

Les moteurs d’inférence ont chacun leur propre approche pour exécuter des modèles de machine learning. La diversité de ces moteurs découle du fait que différents scénarios d’application ont des exigences qui varient fortement. Par exemple :

- Certains moteurs privilégient les performances à grande échelle, avec des tâches nécessitant une faible latence pour un grand volume de requêtes.
- D’autres sont optimisés pour des scénarios légers, sur des machines avec des ressources limitées.

Docker Model Runner, une solution qui simplifie le déploiement de modèles IA dans des conteneurs, intègre différents moteurs d’inférence pour répondre à ces besoins variés. En plus de vLLM, il prend en charge des moteurs comme **llama.cpp**, qui est particulièrement adapté à des environnements matériels modestes.

L’ajout de vLLM dans Docker Model Runner offre une complémentarité précieuse : il s’agit d’un moteur performant conçu pour gérer des tâches complexes avec des charges élevées. Les développeurs peuvent désormais choisir le moteur d’inférence correspondant le mieux à leur architecture et à leurs besoins opérationnels, tout en restant dans l’écosystème Docker.

## Comment utiliser vLLM avec Docker Model Runner

La prise en charge de vLLM dans Docker Model Runner simplifie considérablement l’intégration et l’exécution des LLMs dans des environnements conteneurisés. Voici les étapes générales pour exécuter vLLM avec Docker Model Runner :

1. **Installer Docker Model Runner** : Assurez-vous que Docker Model Runner est installé sur votre machine. Il se présente sous la forme d’une image Docker disponible sur Docker Hub.
   
2. **Choisir le modèle LLM** : Sélectionnez un modèle compatible avec vLLM, comme ceux utilisant le format **safetensors**.

3. **Configurer le fichier de configuration** : Indiquez les paramètres du moteur vLLM et le modèle LLM que vous souhaitez déployer. Voici un exemple de configuration pour un modèle en safetensors :
   
   ```json
   {
       "model": "path/to/model.safetensors",
       "engine": "vllm",
       "num_gpus": 2,
       "max_batch_size": 16
   }
   ```

4. **Exécuter le conteneur** : Lancez Docker Model Runner avec une simple commande pour déployer le modèle :
   ```bash
   docker run -it --rm -p 8080:8080 your-docker-model-runner-image
   ```

5. **Envoyer des requêtes d’inférence** : Vous pouvez désormais interagir avec l’API exposée par Docker Model Runner pour effectuer des inférences sur votre modèle.

Avec ces étapes simples, vLLM peut être utilisé pour exploiter la puissance des modèles de langage tout en bénéficiant des fonctionnalités de Docker, comme la portabilité et l’optimisation pour différents environnements.

## Formats de modèles compatibles : Safetensors vs GGUF

Docker Model Runner est désormais compatible avec plusieurs formats de modèles, dont **safetensors** et **GGUF**, chacun ayant ses cas d’usage spécifiques.

### Safetensors

Le format **safetensors** soutenu par vLLM est un format optimisé pour la rapidité et la sécurité de chargement des modèles. Contrairement à des formats comme **pickle**, safetensors garantit une meilleure isolation de la mémoire, ce qui est essentiel dans des environnements conteneurisés. Il est particulièrement apprécié pour sa capacité à éviter les failles de sécurité potentielles et sa compatibilité avec des architectures modernes.

### GGUF

**GGUF** est un format conçu pour le moteur **llama.cpp**, qui cible des scénarios où les machines disposent de ressources limitées comme les CPU. Ce format mise sur la légèreté et est souvent choisi pour exécuter des modèles dans des environnements localisés ou embarqués.

Cette prise en charge de formats multiples dans Docker Model Runner permet aux développeurs de choisir la combinaison de moteur et de format de modèle la mieux adaptée à leurs besoins, tout en restant flexible pour exploiter différents types d’infrastructures.

## Roadmap et ce qui nous attend

Docker ne cesse d’étendre les capacités de son écosystème avec Docker Model Runner. L’intégration de vLLM marque une avancée importante en matière de performances pour l’inférence IA. Cependant, l’optimisation des flux de travail pour les développeurs ne s’arrête pas là.

Voici quelques éléments qui pourraient arriver prochainement dans la roadmap de Docker Model Runner :

- **Améliorations pour les CPU** : Bien que vLLM excelle sur les GPU, un effort pourrait être porté sur l’optimisation pour les architectures CPU.
- **Support élargi des formats de modèle** : De nouveaux formats pourraient être ajoutés afin de prendre en charge encore plus de moteurs et d’incompatibilités spécifiques.
- **Interfaces simplifiées** : Docker Model Runner pourrait offrir des outils encore plus intuitifs pour configurer et monitorer l’exécution des modèles.

En continuant d'étoffer son support pour des technologies comme vLLM et des formats modernes tels que safetensors, Docker Model Runner se positionne comme une solution clé au carrefour de l’inférence AI et de la conteneurisation.

---

Avec l’intégration de vLLM, Docker fait un pas décisif vers des flux de travail optimisés pour les modèles de langage à grande échelle. Les développeurs et ingénieurs disposent désormais d’une solution robuste et flexible pour répondre à leurs besoins en matière d’inférence AI, tout en bénéficiant de la simplicité d’utilisation qu’offre l’écosystème Docker.

[source](https://www.docker.com/blog/docker-model-runner-integrates-vllm/)