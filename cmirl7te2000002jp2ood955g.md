---
title: "Microsoft corrige une faille critique exploitée par des groupes étatiques"
seoTitle: "Microsoft corrige une faille critique dans les fichiers LNK utilisée par des hackers étatiques"
seoDescription: "Découvrez comment Microsoft a corrigé une faille critique dans les fichiers LNK, exploitée activement par des groupes étatiques depuis 2017."
datePublished: Thu Dec 04 2025 15:25:15 GMT+0000 (Coordinated Universal Time)
cuid: cmirl7te2000002jp2ood955g
slug: microsoft-corrige-faille-lnk-utilisee-par-hackers-etatiques
canonical: https://www.techradar.com/pro/security/microsoft-quietly-patches-lnk-vulnerability-thats-been-weaponized-for-years

---

# Microsoft corrige une faille critique exploitée par des groupes étatiques

## TL;DR
- Microsoft a corrigé la vulnérabilité **CVE-2025-9491**, qui affectait les fichiers LNK de Windows.
- Cette faille permettait l'exécution de code à distance (RCE) et était exploitée depuis 2017.
- Au moins **11 groupes de hackers étatiques** ont utilisé cette vulnérabilité pour des opérations malveillantes.
- Le correctif a été inclus dans la mise à jour de novembre 2025 après des années de négligence.
- L'incident souligne la nécessité de renforcer les pratiques de cybersécurité.

## Contexte de la faille des fichiers LNK

Les fichiers LNK, utilisés dans Windows pour créer des raccourcis vers des programmes ou des ressources, sont une fonctionnalité essentielle au système. Cependant, leur structure technique présentait une vulnérabilité majeure permettant à des cyberattaquants d’intégrer des commandes malveillantes, invisibles pour les utilisateurs. Cela transformait ces fichiers courants en vecteurs parfaits pour des attaques sophistiquées.

La vulnérabilité, référencée sous **CVE-2025-9491**, a été activement exploitée depuis 2017. Elle permettait l’exécution de code arbitraire ou malveillant à distance. Des groupes d'attaquants pouvaient ainsi infiltrer des systèmes, voler des données ou mener des opérations d'espionnage. Malgré l’alarme lancée par divers experts en cybersécurité, cette faille a perduré pendant des années, laissant des millions d’utilisateurs exposés à des risques graves.

## L'usage malveillant des groupes étatiques

Ce bug, exploité pour des campagnes ciblées, est devenu une arme populaire parmi des **groupes hackers étatiques** affiliés à des pays comme la Chine, la Russie, l’Iran et la Corée du Nord. Ces acteurs utilisaient les fichiers LNK pour contourner des mesures de sécurité avancées, particulièrement après que Microsoft a renforcé la protection sur les fichiers Office en bloquant les macros par défaut.

Des organisations sensibles, allant des agences gouvernementales aux infrastructures critiques, étaient fréquemment ciblées par des attaques exploitant cette faille. Les pirates profitaient de la confiance des utilisateurs envers les raccourcis Windows, insérant des fichiers malveillants dans des campagnes d'hameçonnage, des réseaux de collaboration et des connexions USB.

Ces stratégies démontrent à quel point les vulnérabilités « discrètes » comme celles des fichiers LNK peuvent mener à des attaques d’envergure mondiale.

## Le correctif de Microsoft et son importance

Malgré des années de demandes répétées des professionnels de la cybersécurité, Microsoft s'est montré réticent à publier un correctif immédiat. L'entreprise a longtemps avancé que ses logiciels intégrés avertissaient les utilisateurs des risques liés aux fichiers provenant de sources non fiables. Cependant, cette approche s’est avérée insuffisante face à la sophistication des acteurs malveillants.

En novembre 2025, Microsoft a enfin pris la décision d’inclure un correctif pour cette faille dans son cycle de mises à jour mensuelles. Ce correctif figure parmi les **63 vulnérabilités corrigées** lors du Patch Tuesday. Il marque une étape essentielle pour la protection des utilisateurs et met en lumière l’importance de traiter rapidement les failles exploitables.

## Recommandations en matière de cybersécurité

Bien que cette vulnérabilité spécifique soit maintenant corrigée, les incidents liés à des fichiers malveillants soulignent une réalité constante : **les utilisateurs doivent rester vigilants** face aux risques liés aux fichiers provenant de sources inconnues.

### Conseils pratiques
- **Mettre à jour immédiatement** : Assurez-vous que vos systèmes Windows sont à jour avec les derniers correctifs diffusés par Microsoft.
- **Ne pas ouvrir les fichiers suspects** : Tout fichier non sollicité ou provenant d'une source inconnue devrait être traité avec précaution.
- **Renforcer les outils de détection** : Les entreprises devraient intégrer des solutions automatisées de cybersécurité pour arrêter les menaces avant qu'elles ne s'introduisent dans leurs réseaux.
- **Sensibiliser les équipes** : Former les employés à identifier les vecteurs d'attaques courants et à adopter des comportements numériques plus sûrs.

## À surveiller

Alors que Microsoft a corrigé cette faille, les vecteurs utilisés par les groupes étatiques sont en constante évolution. Il est impératif que les utilisateurs et les professionnels de la cybersécurité maintiennent une veille sur les nouvelles techniques et exploitations mises en œuvre.

Enfin, les retours des utilisateurs et des experts après le déploiement du correctif seront cruciaux pour valider l’efficacité des nouvelles mesures.

### Conclusion
La correction de la vulnérabilité critique des fichiers LNK, exploitée depuis des années, est une avancée notable pour la sécurité des systèmes Windows. Cet incident renforce une vérité essentielle en cybersécurité : aucune faille ne doit être minimisée, et une vigilance constante reste indispensable pour protéger nos infrastructures technologiques.

[source](https://www.techradar.com/pro/security/microsoft-quietly-patches-lnk-vulnerability-thats-been-weaponized-for-years)