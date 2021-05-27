---
description: Le paramètre ExpFile pointe vers l’emplacement du fichier de configuration de l’expérience, qui définit votre expérience.
solution: Analytics,Analytics
title: Modification du paramètre ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Modification du paramètre ExpFile{#modifying-the-expfile-parameter}

Le paramètre ExpFile pointe vers l’emplacement du fichier de configuration de l’expérience, qui définit votre expérience.

La définition de ce paramètre vous permet d’exécuter des expériences. Pour connaître les étapes de création du fichier de configuration de l’expérience, voir [Configuration et déploiement de l’expérience](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Voici un exemple du paramètre ExpFile :

```
ExpFile /home/experiment.txt
```

Ce fichier texte délimité par des tabulations ( [!DNL .txt]) peut se trouver n’importe où dans le dossier [!DNL Sensor] et peut avoir n’importe quel nom pratique.

Veillez à enregistrer l’emplacement du répertoire des expériences et le nom du fichier de configuration que vous indiquez, car vous devez enregistrer votre fichier de configuration d’expérience (qui doit être décrit plus loin dans ce guide) à l’aide de ce nom et dans ce répertoire.

>[!NOTE]
>
>Si vous ne définissez pas ce paramètre de la même manière sur chaque machine de votre grappe web sur laquelle est installé [!DNL Sensor], l’expérimentation contrôlée ne fonctionne pas.

Cette entrée peut être préconfigurée et rester dans le fichier de configuration [!DNL Sensor] de manière continue sans aucun effet négatif. Si le nom de fichier de configuration de l’expérience spécifié est introuvable par [!DNL Sensor] ou s’il est vide (c’est-à-dire qu’il existe mais qu’il ne contient aucun contenu), [!DNL Sensor] ne mène pas l’expérience, consigne un événement d’erreur sur le serveur HTTP et continue à fonctionner normalement à tous les autres égards.
