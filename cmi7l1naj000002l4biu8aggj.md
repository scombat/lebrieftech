---
title: "Fortinet dévoile une faille zero-day critique : ce que vous devez savoir"
seoTitle: "Fortinet : une nouvelle faille zero-day critique dévoilée"
seoDescription: "Fortinet découvre une faille zero-day critique (CVE-2025-58034) affectant FortiWeb, exploitée activement. Correctif à appliquer d'urgence."
datePublished: Thu Nov 20 2025 15:25:04 GMT+0000 (Coordinated Universal Time)
cuid: cmi7l1naj000002l4biu8aggj
slug: fortinet-nouvelle-faille-zero-day-critique
canonical: https://www.techradar.com/pro/security/fortinet-admits-it-found-another-worrying-zero-day-being-exploited-in-attacks

---

# Fortinet dévoile une faille zero-day critique : ce que vous devez savoir

## Pourquoi cette faille est importante pour les entreprises

FortiWeb est un pare-feu applicatif utilisé pour protéger les sites web et les API contre les menaces en ligne. Il est largement adopté par de nombreuses entreprises, mais une vulnérabilité majeure, identifiée comme CVE-2025-58034, remet aujourd’hui en cause sa fiabilité. Cette faille, découverte par Jason McFadyen, chercheur en sécurité chez Trend Micro, permet une exploitation sans authentification préalable, offrant aux attaquants un contrôle quasi-total sur les systèmes affectés.

Ce type de vulnérabilité critique est particulièrement préoccupant pour les entreprises qui s'appuient sur FortiWeb pour protéger leurs infrastructures numériques. Les attaques rendues possibles par cette faille comprennent l'installation de logiciels malveillants, comme des backdoors, ou la réalisation de mouvements latéraux dans le réseau. Ces actions peuvent conduire à des attaques de cyberespionnage ou au déploiement de ransomwares, ce qui représente un risque significatif pour la continuité des activités et la confidentialité des données.

Avec environ 2 000 tentatives d’exploitation déjà recensées, cette vulnérabilité témoigne de l’intérêt croissant des cybercriminels pour les infrastructures critiques. Les entreprises qui n’appliquent pas immédiatement les correctifs fournis s’exposent à des intrusions coûteuses et préjudiciables.

## Comment fonctionne la vulnérabilité CVE-2025-58034 ?

### Description technique de la faille

La faille CVE-2025-58034 est classée comme critique, avec un score CVSS de 7.2. Elle résulte d'un défaut dans la gestion des caractères spéciaux dans les commandes système. Plus précisément, une absence de neutralisation correcte de ces caractères permet à des attaquants d’exécuter des commandes arbitraires via des requêtes HTTP ou un accès à l’interface en ligne de commande (CLI).

Les versions de FortiWeb affectées par cette vulnérabilité sont les suivantes :

- **7.0.0 → 7.0.11**  
- **7.2.0 → 7.2.11**  
- **7.4.0 → 7.4.10**  
- **7.6.0 → 7.6.5**  
- **8.0.0 → 8.0.1**

### Exploitation dans la nature

Les données disponibles montrent que la faille est activement exploitée. Les attaques observées consistent en des tentatives d'injection de commande système afin de compromettre des appareils vulnérables. Ces tentatives s’élèvent à plus de 2 000 incidents documentés, reflétant une exploitation réelle par des groupes malveillants.

Une des préoccupations principales réside dans la nature de ces groupes, qui pourraient agir pour des motifs divers, de simples extorsions financières à des ambitions de cyberespionnage à grande échelle. En conséquence, la réactivité pour corriger cette vulnérabilité est cruciale.

## Étapes essentielles pour protéger vos systèmes

### Mesures recommandées

Fortinet a d’ores et déjà déployé des correctifs pour contrer cette vulnérabilité. En tant qu’administrateur système ou responsable de la sécurité, il est impératif de suivre ces étapes pour sécuriser vos infrastructures :

1. **Identifier la version de FortiWeb installée** :  
   Vérifiez si votre système utilise une version concernée par le problème. Cette étape peut être réalisée via l’interface d’administration ou directement en ligne de commande.

2. **Appliquer les correctifs disponibles** :  
   Téléchargez et installez les mises à jour officielles publiées par Fortinet. Ces correctifs corrigent la faille de manière préventive.

3. **Surveiller le trafic réseau** :  
   Configurez des outils pour détecter toute activité suspecte ou des signes d’exploitation active, notamment des tentatives d’injection de commande.

4. **Renforcer la sécurité globale du réseau** :  
   En plus des correctifs, effectuez un audit complet de vos configurations réseau, activez des journaux détaillés et appliquez des politiques de durcissement pour réduire la surface d’attaque.

### Exigences de suivi

Après l'application des correctifs, il est conseillé de mettre en place une surveillance continue afin de détecter d'éventuelles nouvelles variantes ou exploits qui pourraient cibler d'autres systèmes.

## Risques liés à la persistance des vulnérabilités zero-day

Ce nouvel incident avec FortiWeb soulève des interrogations sur la manière dont les éditeurs, même renommés, gèrent le développement et les tests de sécurité de leurs produits. Fortinet, bien que réputée, n'est pas à sa première controverse concernant des failles critiques.

En février 2025, le groupe étatique chinois Volt Typhoon avait exploité une vulnérabilité similaire dans des pare-feux lors d’opérations ciblées contre des infrastructures gouvernementales. Ce contexte montre que les cybercriminels, en particulier ceux opérant pour des organisations étatiques, sont de plus en plus habiles à identifier et exploiter des failles zero-day.

Il est essentiel que les entreprises adoptent une approche proactive en matière de cybersécurité. En intégrant des solutions de détection avancée et en mettant à jour régulièrement leurs systèmes, elles peuvent réduire les risques liés à ce type d’attaques.

## Conclusion

La faille CVE-2025-58034 démontre une fois encore l’importance de la vigilance face aux menaces zero-day. Les entreprises utilisant FortiWeb sont particulièrement exposées à des risques importants, allant de pertes financières majeures jusqu’à des compromissions sensibles. La mise en œuvre des correctifs est une étape incontournable pour protéger vos infrastructures et vos données critiques.

[source](https://www.techradar.com/pro/security/fortinet-admits-it-found-another-worrying-zero-day-being-exploited-in-attacks)