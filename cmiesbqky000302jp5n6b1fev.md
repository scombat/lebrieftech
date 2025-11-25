---
title: "Campagne ClickFix : malwares cachés dans des images et de fausses mises à jour Windows"
seoTitle: "Campagne ClickFix : malwares cachés dans des images et de fausses mises à jour Windows"
seoDescription: "Découvrez comment la campagne ClickFix utilise des fausses mises à jour Windows et des techniques de stéganographie pour propager des malwares. Soyez vigilant !"
datePublished: Tue Nov 25 2025 16:23:15 GMT+0000 (Coordinated Universal Time)
cuid: cmiesbqky000302jp5n6b1fev
slug: campagne-clickfix-malwares-images-fausses-mises-a-jour-windows
canonical: https://www.malwarebytes.com/blog/news/2025/11/new-clickfix-wave-infects-users-with-hidden-malware-in-images-and-fake-windows-updates

---

```markdown
# Campagne ClickFix : malwares cachés dans des images et de fausses mises à jour Windows

## TL;DR

- Les attaquants exploitent de fausses fenêtres de mise à jour Windows pour piéger les utilisateurs peu vigilants.
- Les malwares sont dissimulés dans des fichiers image via une technique de stéganographie.
- Une chaîne d'infection complexe utilise `mshta.exe`, PowerShell et des scripts obfusqués pour déployer le malware.
- Des fichiers légitimes sont détournés pour échapper aux systèmes de détection des antivirus.
- La vigilance face aux actions non vérifiées et aux fichiers suspects est essentielle.

## Les techniques de la campagne ClickFix

ClickFix repose principalement sur l'ingénierie sociale et des visuels élaborés pour tromper les utilisateurs. Les victimes sont confrontées à une interface qui mime les fenêtres authentiques de mise à jour Windows, affichant par exemple :

> **"Travail sur les mises à jour. Ne redémarrez pas votre ordinateur."**

Cette fausse mise à jour invite explicitement l’utilisateur à exécuter manuellement une commande particulière via la boîte de dialogue « Exécuter » de Windows. Cette commande déclenche un script malveillant via l’application légitime `mshta.exe`, marquant ainsi le début du processus de compromise.

## La chaîne d'infection expliquée

La sophistication de la campagne repose sur une chaîne d'infection bien structurée et difficile à détecter :

1. **Exécution via mshta.exe**  
   - Une commande semblant anodine initie le téléchargement d'un fichier JScript malveillant depuis un serveur distant. Les chemins des URL sont encodés en hexadécimal pour compliquer leur détection par les antivirus.

2. **Script PowerShell obfusqué**  
   - Le fichier JScript exécute un script PowerShell fortement obfusqué. Cette étape vise non seulement à activer la charge utile initiale, mais aussi à dissimuler son contenu lorsque des outils d’analyse tentent de l’évaluer.

3. **Chargeur .NET malveillant**  
   - Une fois le script PowerShell exécuté, il déploie un chargeur basé sur .NET pour héberger et exécuter le malware au sein de processus système légitimes.

4. **Utilisation de la stéganographie**  
   - L'image PNG semble être un fichier ordinaire, mais contient des données malveillantes cachées dans ses pixels. Ces données sont extraites directement en mémoire grâce à des scripts, empêchant ainsi tout enregistrement visible sur le disque.

5. **Injection de shellcode**  
   - La charge malveillante finale est injectée dans des processus légitimes comme `explorer.exe`, ce qui permet de masquer ses activités et d'éviter de déclencher une alerte antivirus.

## Qu'est-ce que la stéganographie ?

La stéganographie, au cœur de cette campagne, est une technique permettant de cacher des informations dans des fichiers apparemment inoffensifs, comme des images. Dans ClickFix, les attaquants exploitent le canal rouge des pixels d’une image PNG pour y insérer des payloads infectieux. Ces informations sont imperceptibles à l'œil nu et nécessitent des scripts pour les extraire. 

Les avantages de cette méthode incluent :

- **Discrétion** : Les fichiers semblent normaux et passent sous le radar des solutions de sécurité automatisées.
- **Pas de traces sur le disque** : Le code est reconstitué directement en mémoire, rendant son analyse plus complexe pour les chercheurs en cybersécurité.
- **Flexibilité** : Des fichiers légitimes peuvent être remplacés de manière aléatoire par des fichiers contaminés, diversifiant ainsi les points d'entrée.

## Conseils pour se protéger des attaques ClickFix

Il existe plusieurs bonnes pratiques que les utilisateurs et organisations peuvent adopter pour limiter leur exposition aux campagnes telles que ClickFix :

1. **Ne jamais exécuter des commandes non vérifiées**  
   Méfiez-vous des instructions copiées depuis des sources douteuses. Vérifiez toujours si les commandes ou actions suggérées proviennent de sites officiels ou d’une source fiable.

2. **Évaluer la légitimité des mises à jour Windows**  
   - Les mises à jour authentiques de Windows ne nécessitent jamais d’exécution manuelle via des commandes. Si vous recevez des instructions inhabituelles, il s’agit vraisemblablement d’un piège.

3. **Installer des solutions de sécurité robustes**  
   - Optez pour des logiciels antivirus offrant une protection en temps réel et vérifiez régulièrement leur état de mise à jour.

4. **Se tenir informé des nouvelles menaces**  
   - Abonnez-vous à des blogs et des rapports spécialisés en cybersécurité pour connaître les dernières tactiques des attaquants. Plus vous êtes informé, mieux vous pouvez réagir.

5. **Adopter une approche proactive à toute sollicitation technique**  
   - Vérifiez minutieusement toute action nécessitant l'autorisation d'administrateur, surtout si elle émane d’un système ou message inattendu.

**Astuce utile :**  
Le *Malwarebytes Browser Guard* est une extension recommandée pour repérer les activités suspectes, comme les tentatives de modification du presse-papiers ou de redirection.

---

Les campagnes comme ClickFix mettent en lumière l'importance de la vigilance et de l'éducation en matière de cybersécurité. Grâce à des techniques de dissimulation avancées et des formes élaborées d'ingénierie sociale, ces attaques sont capables de tromper des utilisateurs avertis. L'adoption de bonnes pratiques et l'utilisation d'outils de sécurité adaptés doivent toujours être une priorité.

```

[source](https://www.malwarebytes.com/blog/news/2025/11/new-clickfix-wave-infects-users-with-hidden-malware-in-images-and-fake-windows-updates)