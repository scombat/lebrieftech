---
title: "Failles de sécurité dans le navigateur Comet AI de Perplexity"
seoTitle: "Vulnérabilité critique : risques liés au navigateur Comet AI de Perplexity"
seoDescription: "Une faille dans le navigateur Comet AI pourrait permettre à des hackers de contrôler vos appareils. Découvrez les détails et les risques."
datePublished: Thu Nov 20 2025 18:53:32 GMT+0000 (Coordinated Universal Time)
cuid: cmi7shqsu000002kwfuwn1vvh
slug: vulnerabilite-navigateur-comet-ai-perplexity
canonical: https://www.techradar.com/pro/security/perplexitys-comet-ai-browser-may-have-some-concerning-security-flaws-which-could-let-hacker-hijack-your-device

---

# Failles de sécurité dans le navigateur Comet AI de Perplexity

## Résumé des failles critiques

SquareX, spécialiste de la cybersécurité, a récemment découvert une vulnérabilité critique dans le navigateur Comet développé par Perplexity. Ce navigateur, qui repose sur l'intelligence artificielle, présente une lacune majeure liée à une API cachée capable d'exécuter des commandes locales arbitraires. Une telle faille pourrait permettre aux pirates informatiques de prendre le contrôle total des appareils des utilisateurs.

La gravité de cette vulnérabilité est renforcée par l'interconnexion entre Comet et son extension intégrée **Agentic**. Une compromission du site perplexity.ai pourrait ainsi ouvrir la porte à des attaques massives, incluant le déploiement de ransomwares comme WannaCry. Ces conclusions remettent en question les principes fondamentaux de sécurité des navigateurs traditionnels.

## Analyse des vulnérabilités détectées

### Une API cachée aux capacités dangereuses

Les chercheurs ont identifié une API dissimulée, appelée MCP API (`chrome.perplexity.mcp.addStdioServer`), dans le fonctionnement du navigateur Comet. Cette fonctionnalité permet l'exécution de commandes locales sur les appareils des utilisateurs. Contrairement à des navigateurs comme Google Chrome ou Mozilla Firefox, qui imposent des restrictions strictes pour de telles opérations, Comet laisse une marge de manœuvre beaucoup trop large.

Cette situation est particulièrement inquiétante dans un contexte où la sécurité des extensions et des communications entre le navigateur et des sites web tiers repose sur des standards rigoureux. Ici, Comet semble déroger à ces standards, laissant une porte ouverte aux abus.

### L'extension Agentic : un maillon vulnérable

Un autre point de faiblesse est lié à Agentic, une extension intégrée au navigateur et fortement interconnectée avec le site perplexity.ai. En cas de compromission de ce site — via des attaques courantes comme des injections XSS ou du phishing — des pirates peuvent exploiter l'API MCP pour exécuter du code malveillant sur les appareils des utilisateurs. Cela transforme une seule faille en une menace systémique.

## Impact potentiel et scénarios d'attaque

### Illustration d'une attaque en conditions réelles

SquareX a démontré l'ampleur des risques en mettant en œuvre un scénario d'attaque réaliste :

1. Une extension légitime de Comet a été contournée.
2. Un script malveillant a été injecté sur une version compromise du site perplexity.ai.
3. L'utilisation de l'API MCP via l'extension Agentic a permis l'installation d'un ransomware bien connu, WannaCry, sur des appareils de test.
4. Les chercheurs ont également identifié des vecteurs d'attaque supplémentaires, tels que l'exploitation de failles de type man-in-the-middle ou la compromission d'autres extensions.

### Le poids disproportionné de la sécurité sur Perplexity

Dans ce contexte, Perplexity assume une responsabilité écrasante. La sécurité des utilisateurs dépend exclusivement de leurs pratiques internes, sans filet de sécurité externe. Une simple erreur, comme une faille XSS sur le site perplexity.ai, pourrait déclencher une cascade de conséquences catastrophiques. Ce modèle centralisé va à l'encontre des meilleures pratiques en matière de sécurité des navigateurs et pourrait exposer des millions d'utilisateurs à des attaques imminentes.

## Conseils en matière de cybersécurité

Face aux risques exposés, voici quelques mesures que les utilisateurs et les développeurs peuvent adopter :

1. **Mettez à jour fréquemment vos logiciels** : Installez les derniers correctifs pour réduire la surface d'attaque.
2. **Limitez les autorisations des extensions** : Désactivez les extensions que vous n’utilisez pas afin de minimiser les potentiels points d’entrée.
3. **Surveillez vos flux réseau** : Utilisez des outils de protection contre les attaques de type man-in-the-middle et filtrage des sites suspects.
4. **Adoptez une approche proactive** : Informez-vous sur les pratiques de sécurité des logiciels que vous utilisez, notamment ceux basés sur l’intelligence artificielle.
5. **Analysez les privilèges de vos outils** : Les technologies intrusives ou dangereuses, même basées sur l'IA, doivent être évaluées et parfois abandonnées.

## Conclusion sur les risques liés à Comet AI

La vulnérabilité critique identifiée dans le navigateur Comet AI de Perplexity illustre les défis grandissants de sécurité dans le cadre des technologies basées sur l'intelligence artificielle. En optant pour une configuration qui rompt avec les principes traditionnels des navigateurs, Comet expose ses utilisateurs à des cyberattaques graves, allant d'une compromission de machine à l'installation de ransomwares.

Les technologies émergentes ont besoin de reposer sur des bases solides et de respecter les standards établis en matière de cybersécurité. En l'absence de réaction officielle de Perplexity, il est primordial que les utilisateurs restent vigilants et adoptent des pratiques robustes pour protéger leurs données. Cette affaire est un signal d'alarme pour l'ensemble de l'industrie, qui doit continuer d'innover sans compromettre la sécurité.

--- 

Sources : [TechRadar](https://www.techradar.com/pro/security/perplexitys-comet-ai-browser-may-have-some-concerning-security-flaws-which-could-let-hacker-hijack-your-device)

[source](https://www.techradar.com/pro/security/perplexitys-comet-ai-browser-may-have-some-concerning-security-flaws-which-could-let-hacker-hijack-your-device)