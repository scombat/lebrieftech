---
title: "L’IA et les menaces de sécurité : potentiel et limites des modèles de langage"
seoTitle: "L’IA et les menaces de sécurité : potentiel et limites des LLM"
seoDescription: "Les modèles de langage comme GPT-3.5 génèrent des scripts malveillants, mais restent peu fiables en pratique. Focus sur les défis et les garde-fous de l'IA."
datePublished: Mon Nov 24 2025 23:24:53 GMT+0000 (Coordinated Universal Time)
cuid: cmidry47t000102jp3fjnan99
slug: ia-menaces-securite-defis-limites-llm
canonical: https://www.techradar.com/pro/experts-tried-to-get-ai-to-create-malicious-security-threats-but-what-it-did-next-was-a-surprise-even-to-them

---

# L’IA et les menaces de sécurité : potentiel et limites des modèles de langage

## TL;DR

- Les modèles de langage (LLM) comme GPT-3.5 et GPT-4 peuvent générer des scripts malveillants, mais leur utilisation pratique en environnement réel reste limitée.  
- GPT-4 intègre des mécanismes visant à limiter la génération de code nuisible, bien que ces garde-fous puissent être contournés.  
- Avec GPT-5, les garde-fous sont renforcés et les scripts générés sont plus fiables, mais les modèles restent incapables de produire des cyberattaques autonomes efficaces.  
- Les environnements virtuels testés montrent que ces scripts sont souvent peu fonctionnels ou sujets à des erreurs, contrairement à leur exécution sur des systèmes physiques.  
- La progression rapide des LLM soulève des préoccupations éthiques et de sécurité importantes, appelant à une surveillance accrue.  

## Les risques posés par les modèles LLM

Les modèles de langage basés sur l’intelligence artificielle (LLM), tels que GPT-3.5, GPT-4 et plus récemment GPT-5, représentent une avancée technologique majeure. Toutefois, cette puissance soulève des interrogations sur leur potentiel à être utilisés à des fins malveillantes, voire à exécuter des cyberattaques autonomes. 

Une étude menée par Netskope a exploré cette question en demandant à ces modèles de générer des scripts malveillants. Les résultats montrent que, bien que les LLM soient capables de produire des scripts, leur application dans des scénarios réels soulève de nombreux défis. Par exemple, certains scripts visent à exécuter des techniques sophistiquées comme l’injection de processus ou la désactivation d'outils de cybersécurité. Cependant, ces scripts sont rarement fonctionnels dès leurs premières exécutions.  
  
La montée en popularité des LLM pose également la question d’un possible détournement par des acteurs mal intentionnés. Sans une supervision technologique et éthique, ces outils puissants pourraient être exploités, malgré leurs limitations inhérentes.

## Les défis des modèles actuels d’IA

### Fiabilité et scénarios réels

Les chercheurs de Netskope ont testé GPT-3.5-Turbo et GPT-4 en leur demandant de créer des scripts Python capables d'exploiter des failles spécifiques, comme l’injection de processus ou la désactivation d’antivirus. Si GPT-3.5 produit des scripts rapidement, ceux-ci sont souvent incomplets et très peu fiables, générant fréquemment des erreurs lors de leur exécution.

- **GPT-4**, quant à lui, refuse habituellement de fournir des codes malveillants en raison de ses garde-fous. Cependant, il est possible de contourner ces limitations en formulant soigneusement les instructions. Ces consignes, dites de style « persona », amènent le modèle à bypasser ses restrictions.  

Les environnements de test, souvent des machines virtuelles comme VMware Workstation ou AWS Workspace VDI, ont montré des résultats décevants. Les scripts générés par les modèles entraînent fréquemment des erreurs ou s’avèrent incapables de fonctionner correctement. Sur des environnements physiques, une partie des scripts est parfois exécutée avec succès, mais d’autres restent inutilisables sans intervention humaine pour corriger leurs lacunes.

### Dépendance aux prompts sophistiqués

La qualité des outputs des LLM dépend fortement des prompts fournis. Les modèles plus avancés, comme GPT-4 et GPT-5, sont meilleurs pour comprendre des consignes complexes et produire du code technique adapté à des scénarios très spécifiques. Néanmoins, il est évident que même ces générations de modèles ont besoin d’une intervention humaine pour optimiser et corriger leur travail.

## Les garde-fous des LLM : une solution suffisante ? 

Avec l’arrivée de GPT-5, les capacités de génération de code semblent avoir fait un bond en avant. Non seulement la qualité des scripts s’est améliorée, mais l’introduction de garde-fous plus robustes représente un pas vers une meilleure sécurité.

Ces garde-fous permettent, dans de nombreux cas, de transformer des requêtes malveillantes en conseils inoffensifs ou en exposé des risques de sécurité. Cela contraste avec les versions précédentes comme GPT-3.5, où les résultats générés pouvaient être manipulés plus facilement pour fournir du code problématique.  

Cependant, ces protections ne sont pas parfaites. Certains prompts sophistiqués, construits avec des connaissances en ingénierie sociale ou manipulation de modèles, réussissent encore à contourner les limites imposées. Cela pose un véritable défi pour garantir que les futurs développements de LLM ne deviennent pas des outils facilement exploitables par des individus ou des organisations malveillantes.  

## L’avenir des cyberattaques autonomes basées sur l’IA

Malgré l’amélioration des capacités des LLM, une conclusion importante de l’étude menée par Netskope est leur incapacité à orchestrer des cyberattaques entièrement autonomes efficacement. À l’heure actuelle, les modèles nécessitent une supervision humaine pour affiner les scripts et les adapter à des contextes spécifiques. 

En revanche, les avancées rapides dans le développement des modèles de langage poussent à s’interroger sur ce que l’avenir pourrait réserver. L’apparition de LLM plus puissants pourrait, un jour, faire peser une menace réelle sur la cybersécurité mondiale. Cette hypothèse conduit à une exigence de vigilance accrue et à une recherche continue pour renforcer les mécanismes de sécurité et les réglementations.

Les décisions concernant le développement et l’usage de ces technologies auront un impact fondamental sur leur rôle dans un monde où les cyberattaques sont de plus en plus sophistiquées. La collaboration entre chercheurs, développeurs et experts en éthique sera essentielle pour éviter les abus et garantir un usage responsable de cette technologie émergente.

## Ce qu’il faut retenir

1. **Les capacités limitées des LLM dans les cyberattaques** : Même si des modèles comme GPT-3.5 et GPT-4 sont capables de produire du code malveillant, leur exécution reste problématique dans des environnements réels.  
2. **L’évolution avec GPT-5** : Les performances des modèles continuent de progresser, mais les garde-fous intégrés offrent une barrière face aux abus. Ces mécanismes de protection sont cependant contournables dans certains cas.  
3. **Un futur incertain** : Les cyberattaques autonomes basées sur l’IA ne sont pas encore une réalité, mais pourraient devenir une menace avec l'avènement de modèles plus puissants.  

Le développement rapide des LLM exige des réflexions profondes en matière de cybersécurité et d’éthique, afin de protéger les systèmes et les utilisateurs tout en exploitant le potentiel de l’IA.

[source](https://www.techradar.com/pro/experts-tried-to-get-ai-to-create-malicious-security-threats-but-what-it-did-next-was-a-surprise-even-to-them)