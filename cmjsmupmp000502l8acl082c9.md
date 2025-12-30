---
title: "Créer un outil CLI pour scanner les TODO en Rust et le distribuer via Homebrew"
seoTitle: "Créer un outil CLI avec Rust : scanner les TODO et le distribuer via Homebrew"
seoDescription: "Découvrez comment créer un outil CLI rapide en Rust pour scanner les TODO dans vos projets et le distribuer facilement via Homebrew."
datePublished: Tue Dec 30 2025 13:38:31 GMT+0000 (Coordinated Universal Time)
cuid: cmjsmupmp000502l8acl082c9
slug: creer-cli-todo-scanner-homebrew
canonical: https://dev.to/idieod/i-made-a-cli-tool-to-search-todos-and-distributed-on-homebrew-4a87

---

# Créer un outil CLI pour scanner les TODO en Rust et le distribuer via Homebrew

## TL;DR

- Développez un outil CLI en Rust pour scanner automatiquement les commentaires TODO dans vos fichiers de code.
- TodoScanner est léger, rapide, et compatible avec de nombreuses extensions de fichiers.
- Distribuez votre outil facilement en utilisant Homebrew pour le rendre accessible à la communauté.
- Cette solution optimise la gestion des tâches en attente dans vos projets logiciels.

## Pourquoi créer un outil pour scanner les TODO ?

Les commentaires TODO sont très courants dans le développement logiciel : ils permettent aux développeurs de noter des tâches ou des améliorations à réaliser ultérieurement. Cependant, dans des bases de code importantes ou collaboratives, ces commentaires peuvent se perdre dans la masse, rendant difficile leur suivi ou leur résolution.

Un outil en ligne de commande, spécialement conçu pour scanner ces annotations, offre une solution efficace pour identifier rapidement les sections à améliorer. Il permet de mieux gérer les tâches en attente et évite que des éléments critiques restent ignorés. En le développant en Rust, vous bénéficiez d'un temps d'exécution rapide et d'une exécution fiable, même sur des bases de code volumineuses.

## Fonctionnalités de l'outil TodoScanner

TodoScanner est conçu pour être un outil minimaliste mais puissant, avec les caractéristiques suivantes :

### Compatibilité avec de nombreux formats de fichiers  
L'outil prend en charge des extensions de fichiers courantes telles que :
- `.rs` (Rust)
- `.js` (JavaScript)
- `.py` (Python)
- `.java` (Java)
- `.html` (HTML)
- Et bien plus encore.

### Recherche rapide et ciblée  
L'algorithme de TodoScanner permet de rechercher des commentaires contenant des mots-clés spécifiques tels que `TODO`, `FIXME`, ou `NOTE`. Cela garantit une analyse précise et rapide, même sur des projets avec des milliers de fichiers.

### Options de filtrage  
Vous pouvez personnaliser les recherches via des arguments CLI (pour ignorer certains fichiers, limiter la profondeur de recherche, ou spécifier des extensions cibles).

### Interface utilisateur intuitive  
Le CLI a été développé avec une syntaxe claire et minimaliste pour faciliter son adoption par les développeurs de toute expérience.

## Comment installer et utiliser TodoScanner

### Installation avec Homebrew  
Distribuer TodoScanner via Homebrew rend son installation simple et accessible. Voici les étapes nécessaires :
1. Ajoutez le dépôt à votre configuration Homebrew :
    ```
    brew tap I-Dieod/tap
    ```
2. Installez l'outil avec la commande suivante :
    ```
    brew install tds
    ```

Une fois installé, l'outil est prêt à être utilisé directement dans votre terminal.

### Utilisation de l'outil  
Pour scanner les fichiers d'un projet, exécutez simplement :
```
tds <répertoire_du_projet>
```
Par exemple :
```
tds ./mon_projet
```
Cette commande affichera une liste de commentaires annotés dans tous les fichiers compatibles du dossier cible.

Vous pouvez également personnaliser la recherche en ajoutant des options :
- Exclure des dossiers spécifiques :
    ```
    tds ./mon_projet --exclude node_modules
    ```
- Cibler certains types de fichiers :
    ```
    tds ./mon_projet --extensions rs,js
    ```

## Distribuer un outil Rust via Homebrew

Homebrew est une solution populaire pour la distribution d'outils sur macOS et Linux. Voici les étapes principales pour rendre votre outil Rust disponible via Homebrew :

1. **Compiler votre projet Rust**  
   Utilisez Cargo pour compiler l'outil en un binaire. Exemple :
   ```
   cargo build --release
   ```

2. **Créer un dépôt sur GitHub**  
   Publiez le binaire généré dans les "Releases" de votre dépôt GitHub. Cela permet à Homebrew de récupérer automatiquement la dernière version distribuée.

3. **Configurer une formule Homebrew**  
   Créez un script Ruby pour définir la formule Homebrew. Voici un exemple :
   ```ruby
   class Tds < Formula
     desc "Un scanner CLI Rust pour les TODO"
     homepage "https://github.com/I-Dieod/tds"
     url "https://github.com/I-Dieod/tds/releases/download/v1.0.0/tds-v1.0.0.tar.gz"
     sha256 "votre_hash"
     license "MIT"

     def install
       bin.install "tds"
     end

     test do
       system "#{bin}/tds", "--version"
     end
   end
   ```
   Publiez ce fichier sur votre dépôt dédié comme `I-Dieod/homebrew-tap`.

4. **Tester et documenter**  
   Vérifiez que l'installation fonctionne correctement avec la commande `brew install tds`. Ajoutez une documentation détaillée dans votre dépôt pour guider les utilisateurs sur l'installation et l'utilisation.

## Conclusion et réflexions

Créer et distribuer un outil comme TodoScanner permet de combiner une meilleure gestion des tâches dans la base de code, un gain de productivité pour les développeurs et une mise à disposition accessible via des plateformes de distribution comme Homebrew. En exploitant les performances de Rust et en adoptant une philosophie open source, ce projet est une solution utile et évolutive pour la communauté technique. Les contributions et retours d'expérience sur GitHub sont essentiels pour améliorer encore l'outil et élargir ses fonctionnalités.

Si vous êtes passionné par le développement logiciel ou que vous cherchez à simplifier vos workflows, développer un outil CLI en Rust et le partager avec Homebrew est une excellente initiative.

[source](https://dev.to/idieod/i-made-a-cli-tool-to-search-todos-and-distributed-on-homebrew-4a87)