---
title: "Failles sur JSONFormatter et CodeBeautify : données critiques exposées"
seoTitle: "Failles de sécurité sur JSONFormatter et CodeBeautify : Données exposées"
seoDescription: "Les sites JSONFormatter et CodeBeautify exposent des données sensibles via des fonctionnalités non protégées. Développeurs, méfiez-vous!"
datePublished: Wed Nov 26 2025 11:36:36 GMT+0000 (Coordinated Universal Time)
cuid: cmifxiy9p000102la1myu37j4
slug: failles-jsonformatter-codebeautify-donnees-exposees
canonical: https://www.techradar.com/pro/security/top-code-formatting-sites-are-exposing-huge-amounts-of-user-data

---

# Failles sur JSONFormatter et CodeBeautify : données critiques exposées

## TL;DR

- Les fonctionnalités publiques de JSONFormatter et CodeBeautify exposent des données sensibles via des "Liens récents" non protégés.
- Ces données incluent des clés d'accès, des tokens API, et des informations personnelles, parfois liées à des organisations critiques et gouvernementales.
- Ces failles sont déjà exploitées activement par des cybercriminels.
- Évitez de téléverser des données sensibles sur des services publics de formatage de code et privilégiez des solutions sécurisées.

## Les dangers des services JSONFormatter et CodeBeautify

Les plateformes comme JSONFormatter et CodeBeautify sont très populaires parmi les développeurs, notamment pour leur capacité à formater et à simplifier le débogage de code. Cependant, une analyse récente menée par les chercheurs de WatchTowr a mis en lumière une grave faille de sécurité dans leur fonctionnement.

Ces services proposent une fonctionnalité appelée "Liens récents", qui liste publiquement les fichiers ou URL récemment manipulés par les utilisateurs. Le problème ? Ces liens sont accessibles sans aucune mesure de sécurité, comme un mot de passe ou une authentification. En exploitant la prévisibilité des URL générées, des acteurs malveillants peuvent facilement accéder aux données sensibles téléversées sur ces plateformes.

De nombreux développeurs utilisent ces sites sans se douter qu'ils pourraient compromettre la confidentialité de leurs données. Malheureusement, cette négligence peut ouvrir la voie à des attaques sophistiquées, ciblant aussi bien des entreprises que des gouvernements.

## Découvertes alarmantes des chercheurs en cybersécurité

Les chercheurs ont récupéré jusqu'à cinq années de données exposées via ces "Liens récents", révélant un nombre préoccupant d'informations sensibles. Parmi les données collectées, on retrouve :

- **Identifiants sécurisés** : accès à des infrastructures cloud, bases de données, et environnements Active Directory.
- **Secrets critiques** : clés SSH, clés API pour des pipelines CI/CD, et tokens d'accès à des passerelles de paiement.
- **Données personnelles** : informations KYC (Know Your Customer), documents d'identité et autres informations confidentielles.

Ces données provenaient de secteurs variés, comme les infrastructures critiques, les institutions financières, les agences gouvernementales, l'industrie aérospatiale, et même la santé. De plus, même lorsque les fichiers ne contenaient pas directement de clés ou secrets, les configurations exposées pouvaient fournir un aperçu précieux pour planifier des attaques ciblées.

## Conséquences pour les organisations et développeurs

Les données ainsi accessibles représentent un risque majeur pour les utilisateurs et les organisations qui dépendent de ces services. Elles peuvent être exploitées par des cybercriminels pour :

- Accéder directement à des systèmes critiques via des identifiants trouvés.
- Procurer des informations permettant des attaques par hameçonnage ou des intrusions plus ciblées.
- Mettre en œuvre des attaques contre des infrastructures critiques, des réseaux gouvernementaux, ou des systèmes financiers.

Les chercheurs de WatchTowr ont également constaté une surveillance active par des acteurs malveillants de ces plateformes. Un exemple frappant est l’utilisation de clés AWS ayant une date d'expiration simulée pour tromper les utilisateurs. Même après expiration, des mouvements suspects sur ces clés ont été détectés, confirmant une exploitation continue par des cybercriminels.

## Recommandations pour la sécurité des développeurs

Face à ces risques, il est indispensable de prendre des mesures proactives pour protéger les données et prévenir les fuites. Voici quelques recommandations essentielles :

1. **Évitez d'utiliser des services publics** : Ne téléversez jamais des données critiques ou sensibles sur des outils comme JSONFormatter ou CodeBeautify. Même pour un usage temporaire, ces données peuvent être exploitées.
   
2. **Privilégiez des outils locaux** : Utilisez des solutions de formatage et d'analyse locales ou internes à votre organisation. Ces outils permettent un contrôle total sur la confidentialité des informations.

3. **Auditez régulièrement vos configurations** : Vérifiez que vos environnements de développement et vos comptes ne sont pas exposés sur des plateformes publiques. Cela inclut des audits approfondis de vos clés d’accès et configurations.

4. **Adoptez des alternatives sécurisées** : De nombreux outils de formatage proposent des mécanismes robustes pour protéger vos données. Priorisez les services offrant une sécurité renforcée, même si cela implique des coûts supplémentaires.

## À surveiller

Face à cette découverte, plusieurs évolutions sont à surveiller dans les mois à venir :

- Une probable augmentation des attaques ciblées utilisant les données récupérées via JSONFormatter et CodeBeautify.
- Les réactions des services concernés : mettront-ils en place des mécanismes de sécurisation adéquats ? Pour l'instant, aucune mesure corrective n'a été annoncée.
- L'émergence d'autres "dépotoirs" de données sensibles sur des services similaires, attirant l'attention de cybercriminels.

## Conclusion

Les failles découvertes sur JSONFormatter et CodeBeautify sont une piqûre de rappel : même les plateformes apparemment simples et utiles peuvent comporter des risques majeurs si elles ne sont pas conçues avec la sécurité en tête. Pour les développeurs et ingénieurs, il est essentiel de toujours évaluer les implications de sécurité avant d'utiliser un service public, même pour des actions courantes telles que le formatage ou le débogage.

Privilégiez des solutions sécurisées et adoptez une approche proactive en matière de protection des données.

**Source** : [TechRadar](https://www.techradar.com/pro/security/top-code-formatting-sites-are-exposing-huge-amounts-of-user-data)

[source](https://www.techradar.com/pro/security/top-code-formatting-sites-are-exposing-huge-amounts-of-user-data)