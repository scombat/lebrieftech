---
title: "Tor adopte l'algorithme CGO pour une sécurité accrue"
seoTitle: "Tor renforce sa sécurité avec l'algorithme d'encryption CGO"
seoDescription: "Tor adopte l'algorithme innovant CGO pour remplacer le vieillissant tor1, augmentant ainsi la confidentialité et bloquant les attaques modernes."
datePublished: Sun Nov 30 2025 21:51:22 GMT+0000 (Coordinated Universal Time)
cuid: cmim98ykw000202l7glsudesl
slug: tor-renforce-securite-algorithme-encryption-cgo
canonical: https://www.techradar.com/pro/security/tor-adds-another-layer-to-the-onion-with-a-new-relay-encryption-algorithm-boosting-resilience-and-security-across-the-board

---

# Tor adopte l'algorithme CGO pour une sécurité accrue

## TL;DR

- Tor remplace l'algorithme tor1 par **Counter Galois Onion (CGO)** pour améliorer la sécurité de son réseau.
- CGO intègre un cryptage par blocs larges, un chaînage des tags et une mise à jour des clés après chaque cellule.
- Le nouvel algorithme bloque des attaques modernes comme les tagging attacks, qui visaient les utilisateurs du réseau.
- Les mises à jour renforcent la protection des données sans impact notable sur la performance du réseau.

## Importance de l'encryption remplacée

Le réseau Tor est une référence en matière de protection de la vie privée et de l'anonymat numérique. Depuis sa création, Tor s'appuie sur des mécanismes d'encryption avancés afin de sécuriser les communications transitant par ses multiples relais. Cependant, à mesure que les méthodes d'attaque évoluent, les solutions existantes peuvent devenir obsolètes. L'algorithme **tor1**, utilisé depuis des années, s'est révélé insuffisant face aux avancées technologiques des attaquants.

### Limites du système tor1

Le système tor1 présentait plusieurs failles majeures exploitables par les cybercriminels :

1. **Cryptage AES-CTR sans authentification robuste** : Cette approche permettait aux attaquants contrôlant certains relais de manipuler les données afin d'identifier des utilisateurs par des techniques comme les tagging attacks.
2. **Réutilisation des clés AES** dans les circuits : Ce comportement compromettait la confidentialité des données en facilitant la récupération des informations par des algorithmes d'attaque.
3. **Authentification insuffisante avec SHA-1 et un digeste de seulement 4 octets** : Cette faiblesse augmentait les probabilités de falsification des données et de fausses authentifications.

Ces failles représentaient un risque significatif pour les utilisateurs, rendant impérative une mise à jour du système. Dans un contexte où les menaces liées à la confidentialité numérique ne cessent de croître, une solution robuste et innovante était nécessaire pour maintenir la réputation de Tor comme outil de protection de la vie privée.

## Progrès et innovations du système CGO

Pour répondre à ces défis, Tor a développé le **Counter Galois Onion (CGO)**, un nouveau système d'encryption basé sur des avancées technologiques comme la permutation pseudorandom **UIV+**. CGO est conçu pour surmonter les limitations de tor1 tout en répondant aux normes de sécurité les plus exigeantes. Voici quelques-unes des principales améliorations introduites par cet algorithme :

### Un cryptage par blocs larges et chaînage des tags

CGO intègre un **cryptage par blocs larges**, ce qui empêche le déchiffrage des cellules altérées ou interceptées. Grâce au **chaînage des tags et des nonces encryptés**, toute tentative de falsification ou d'interception des données est immédiatement détectée et bloquée. Les interceptions prédictibles, jusque-là une menace sérieuse, deviennent impossibles.

### Mise à jour des clés après chaque cellule

Une des principales innovations de CGO est la mise à jour des clés d'encryption après chaque cellule transitant sur le réseau. Ce changement radical améliore la sécurité, car même en cas de compromis d'une clé, les données précédentes et futures restent protégées. Ce mécanisme va bien au-delà des pratiques utilisées dans les systèmes classiques.

### Authentificateur modernisé

Tor abandonne la technologie **SHA-1** vieillissante en faveur d'un authentificateur plus robuste basé sur un digeste de 16 octets. Ce choix réduit significativement la probabilité de falsifications et renforce considérablement la sécurité des circuits et des relais.

## Mise en œuvre progressive et déploiement

L'intégration de l'algorithme **Counter Galois Onion** se fait dans une approach progressive. Pour le moment, CGO est encore en phase expérimentale, mais son intégration a déjà commencé :

- Le déploiement est en cours pour les clients **C Tor** ainsi que ceux basés sur **Rust** comme **Arti client**.
- À terme, CGO sera inclus dans les services onion, ce qui permettra d'améliorer les négociations de données et de renforcer les performances globales du réseau Tor.
- Les utilisateurs du **Tor Browser** bénéficieront automatiquement de cette mise à jour dès qu'elle sera mise en œuvre, sans action spécifique nécessaire.

Cependant, aucune échéance définitive n'a encore été annoncée pour l'adoption générale de CGO comme système d'encryption par défaut.

## Points à surveiller pour l'avenir

Si l'algorithme CGO introduit des avancées significatives, certains éléments nécessitent une attention particulière pour garantir une intégration optimale :

1. **Performances sous charge élevée** : L'impact du cryptage par blocs larges et de la mise à jour répétée des clés sur la vitesse du réseau devra être rigoureusement évalué pour éviter un ralentissement notable.
2. **Compatibilité avec les systèmes existants** : Assurer une migration harmonieuse pour les utilisateurs disposant de configurations ou de matériels plus anciens est essentiel pour éviter toute perturbation majeure.
3. **Résilience face aux nouveaux types d'attaques** : Les tests en conditions réelles devront confirmer que CGO est efficace contre une variété de menaces émergentes.

En maintenant une approche proactive de la cybersécurité, Tor renforce sa mission de protéger les données et les communications de ses utilisateurs, tout en anticipant les défis à venir.

## Conclusion

Le remplacement de l'algorithme **tor1** par le **Counter Galois Onion (CGO)** marque une étape importante pour le réseau Tor dans le domaine de la sécurité. En adoptant des technologies d'encryptage par blocs larges, de chaînage des tags encryptés et de mise à jour fréquente des clés, Tor démontre son engagement à répondre aux exigences de sécurité modernes. Bien que des défis subsistent, notamment en matière de performances, ces évolutions affirment le rôle central de Tor dans la protection de la confidentialité et des libertés en ligne.

Les utilisateurs du **Tor Browser** sont déjà en bonne voie pour profiter de ces innovations de sécurité, sans nécessiter de modifications. En surveillant les avancées et ajustements nécessaires, l'équipe derrière Tor montre clairement sa détermination à relever les défis des cybermenaces actuelles et futures.

[source](https://www.techradar.com/pro/security/tor-adds-another-layer-to-the-onion-with-a-new-relay-encryption-algorithm-boosting-resilience-and-security-across-the-board)