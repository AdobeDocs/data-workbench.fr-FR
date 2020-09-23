---
description: Le paramètre ExpFile pointe vers l'emplacement du fichier de configuration de l'expérience, qui définit votre expérience.
solution: Analytics,Analytics
title: Modification du paramètre ExpFile
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---


# Modification du paramètre ExpFile{#modifying-the-expfile-parameter}

Le paramètre ExpFile pointe vers l&#39;emplacement du fichier de configuration de l&#39;expérience, qui définit votre expérience.

La définition de ce paramètre permet d&#39;exécuter des expériences. Pour connaître les étapes de création du fichier de configuration de l&#39;expérience, voir [Configuration et déploiement de l&#39;expérience](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Voici un exemple du paramètre ExpFile :

```
ExpFile /home/experiment.txt
```

Ce fichier texte délimité par des tabulations ( [!DNL .txt]) peut se trouver n’importe où dans le [!DNL Sensor] dossier et peut porter n’importe quel nom pratique.

Assurez-vous d&#39;enregistrer l&#39;emplacement du répertoire d&#39;expériences et le nom du fichier de configuration que vous spécifiez, car vous devez enregistrer votre fichier de configuration d&#39;expérience (à décrire plus loin dans ce guide) en utilisant ce nom et dans ce répertoire.

>[!NOTE]
>
>Si vous ne définissez pas ce paramètre de la même manière sur chaque machine de votre grappe Web sur laquelle une grappe [!DNL Sensor] est installée, l’expérimentation contrôlée ne fonctionne pas.

Cette entrée peut être préconfigurée et rester dans le fichier de [!DNL Sensor] configuration en permanence sans effet négatif. Si le nom de fichier de configuration de l&#39;expérience spécifié n&#39;est pas trouvé par [!DNL Sensor] ou s&#39;il est vide (c&#39;est-à-dire qu&#39;il existe mais qu&#39;il n&#39;a pas de contenu), [!DNL Sensor] ne mène pas l&#39;expérience, consigne un événement d&#39;erreur sur le serveur HTTP et continue à fonctionner normalement à tous les autres égards.
