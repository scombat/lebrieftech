---
title: "Comprendre EdgeStepper : Une menace pour la cybersécurité des mises à jour logicielles"
seoTitle: "EdgeStepper : Comment ce malware détourne les mises à jour logicielles"
seoDescription: "Découvrez EdgeStepper, un malware innovant exploitant les requêtes DNS pour détourner les mises à jour logicielles, ciblant industries critiques comme l'éducation."
datePublished: Thu Nov 20 2025 08:59:51 GMT+0000 (Coordinated Universal Time)
cuid: cmi77a9d8000102joa6pkguxa
slug: edgestepper-dns-malware-mises-a-jour-logicielles
canonical: https://thehackernews.com/2025/11/edgestepper-implant-reroutes-dns.html

---

# Comprendre EdgeStepper : Une menace pour la cybersécurité des mises à jour logicielles

## Contexte : PlushDaemon et EdgeStepper

EdgeStepper est un malware sophistiqué développé par le groupe PlushDaemon, connu pour ses activités d’espionnage cybernétique depuis plusieurs années. Ce groupe, réputé pour ses liens présumés avec des acteurs étatiques chinois, représente une menace de grande envergure à l'échelle mondiale. Son champ d'action s'étend des États-Unis à l'Asie-Pacifique, où il cible des infrastructures critiques à travers des attaques complexes.

EdgeStepper se distingue par l’utilisation des attaques dites Adversary-in-the-Middle (AitM), particulièrement centrées sur le détournement des requêtes DNS. Ce type d’attaque permet de rediriger le trafic légitime vers des serveurs malveillants contrôlés par l’attaquant. Selon le dernier rapport publié par les experts d’ESET, ce malware est écrit en Go, un langage qui facilite le développement de programmes performants et multiplateformes. Son but est clair : perturber le processus de mise à jour logicielle et y insérer un code malveillant, compromettant ainsi les systèmes infectés.

## Fonctionnement interne d’EdgeStepper

Le succès d’EdgeStepper repose sur une architecture modulaire qui lui confère flexibilité et efficacité. Les deux modules principaux, le distributeur et le module de règles, travaillent en tandem pour exécuter l’attaque.

### Modules clés

1. **Module distributeur** : Ce module cible et résout les domaines associés à des serveurs contrôlés par PlushDaemon. Il est capable de détourner les requêtes DNS à des fins malveillantes. Par exemple, une requête légitime vers un domaine de mise à jour peut être redirigée vers `test.dsc.wcsset[.]com`, un serveur sous contrôle des assaillants.

2. **Module de règles** : Avec l’utilisation d’outils comme `iptables`, ce module configure des règles de filtrage et de redirection IP, permettant de bloquer ou modifier le trafic réseau de manière ciblée.

### Chaîne d’infection

Le processus d’infection d’EdgeStepper suit une méthode bien définie :

1. Interception des requêtes DNS liées aux mises à jour logicielles.  
2. Redirection des requêtes vers un serveur malveillant, imitant les URL légitimes des éditeurs de logiciels.  
3. Téléchargement et exécution du malware **LittleDaemon**, injecté sous la forme d’un fichier DLL corrompu.  
4. Installation de charges utiles additionnelles, telles que **DaemonicLogistics** (module de gestion de charge) et **SlowStepper**, destiné à collecter et exfiltrer des données sensibles.

L’impact est particulièrement grave sur des logiciels largement utilisés en Chine comme **Sogou Pinyin**, où les attaques sont facilitées par la popularité et les permissions élevées des applications détournées.

## Campagnes et secteurs visés

Les campagnes associées à EdgeStepper montrent une exploitation systématique des failles de sécurité au sein des périphériques réseau, comme les routeurs. Les attaquants tirent parti d'identifiants faibles ou de vulnérabilités connues pour compromettre ces équipements en périphérie du réseau, posant un risque sérieux pour les entreprises ciblées.

Les secteurs visés incluent :  
- **La fabrication électronique** : Des usines utilisant des équipements contrôlés via des logiciels connectés, vulnérables aux interruptions de la chaîne de production.  
- **Les semi-conducteurs** : Une industrie critique compte tenu de la demande mondiale pour ces produits stratégiques.  
- **L’éducation** : Les infrastructures académiques sont souvent sous-protégées et représentent une cible facile.  

Une fois infiltré, un malware secondaire comme **SlowStepper** peut intensifier les dégâts en réalisant des actions telles que :  
- La collecte d’informations système.  
- Le vol de fichiers sensibles, mots de passe, et historiques de navigation.  
- L’extraction de données à partir d’applications spécifiques comme des clients de messagerie.  
- L’auto-désinstallation pour effacer toute trace de l’attaque.  

## Protéger vos réseaux contre les attaques EdgeStepper

Étant donné le niveau de sophistication de ce malware, il est crucial que les entreprises et organisations adoptent une approche préventive. Voici les mesures essentielles à mettre en œuvre :

- **Renforcer la sécurité des périphériques réseau** : Analysez vos niveaux d’accès et corrigez rapidement toute vulnérabilité ou configuration obsolète.  
- **Mise en place de protections contre le détournement DNS** : Les entreprises peuvent utiliser des outils qui surveillent et bloquent les modifications suspectes.  
- **Inspection des processus de mise à jour logiciel** : Intégrez des mécanismes de vérification des certificats ou des signatures numériques pour valider l’authenticité des fichiers téléchargés.  
- **Pratiquer une segmentation du réseau** : Limitez les interactions entre les systèmes critiques afin de minimiser la propagation d’éventuelles infections.  
- **Former vos équipes** : Sensibilisez vos collaborateurs aux menaces présentes dans les chaînes logicielles et aux risques liés aux insuffisances de configuration réseau.

## Conclusion : Préparer ses défenses

EdgeStepper est un exemple parmi les attaques émergentes qui illustrent la montée en puissance des cybermenaces dans des contextes géopolitiques et stratégiques. Ce malware ne se contente pas de cibler des systèmes isolés : il s’insinue dans les chaînes critiques comme les mises à jour logicielles, compromettant la sécurité de vastes infrastructures.

Les entreprises doivent donc anticiper ces nouvelles formes de menaces et investir dans des défenses adaptées, capables d’identifier rapidement les anomalies dans leur réseau. La cybersécurité n'est plus seulement une priorité technique ; elle est désormais un impératif stratégique au service des économies et de la stabilité mondiale.  

[source](https://thehackernews.com/2025/11/edgestepper-implant-reroutes-dns.html)