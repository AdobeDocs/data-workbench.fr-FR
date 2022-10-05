---
description: Le paramètre ExpFile pointe vers l’emplacement du fichier de configuration de l’expérience, qui définit votre expérience.
solution: Analytics
title: Modification du paramètre ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Modification du paramètre ExpFile{#modifying-the-expfile-parameter}

{{eol}}

Le paramètre ExpFile pointe vers l’emplacement du fichier de configuration de l’expérience, qui définit votre expérience.

La définition de ce paramètre vous permet d’exécuter des expériences. Pour connaître les étapes de création du fichier de configuration de l’expérience, voir [Configuration et déploiement de l’expérience](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Voici un exemple du paramètre ExpFile :

```
ExpFile /home/experiment.txt
```

Ce fichier texte délimité par des tabulations ( [!DNL .txt]) peut se trouver n’importe où dans la variable [!DNL Sensor] et peut avoir n’importe quel nom pratique.

Veillez à enregistrer l’emplacement du répertoire des expériences et le nom du fichier de configuration que vous indiquez, car vous devez enregistrer votre fichier de configuration d’expérience (qui doit être décrit plus loin dans ce guide) à l’aide de ce nom et dans ce répertoire.

>[!NOTE]
>
>Si vous ne définissez pas ce paramètre de la même manière sur chaque ordinateur de votre grappe web sur lequel une [!DNL Sensor] est installé, l’expérimentation contrôlée ne fonctionne pas.

Cette entrée peut être préconfigurée et reste dans la variable [!DNL Sensor] fichier de configuration de manière continue sans effet négatif. Si le nom de fichier de configuration de l’expérience spécifié est introuvable par [!DNL Sensor] ou il est vide (c’est-à-dire qu’il existe mais qu’il n’a pas de contenu), [!DNL Sensor] ne mène pas l’expérience, consigne un événement d’erreur sur le serveur HTTP et continue à fonctionner normalement à tous les autres égards.
