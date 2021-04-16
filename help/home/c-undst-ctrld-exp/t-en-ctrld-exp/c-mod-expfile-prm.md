---
description: Le paramètre ExpFile pointe vers l'emplacement du fichier de configuration de l'expérience, qui définit votre expérience.
solution: Analytics,Analytics
title: Modification du paramètre ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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

Ce fichier texte délimité par des tabulations ( [!DNL .txt]) peut se trouver n&#39;importe où dans le dossier [!DNL Sensor] et peut avoir n&#39;importe quel nom approprié.

Assurez-vous d&#39;enregistrer l&#39;emplacement du répertoire d&#39;expériences et le nom du fichier de configuration que vous spécifiez, car vous devez enregistrer votre fichier de configuration d&#39;expérience (à décrire plus loin dans ce guide) en utilisant ce nom et dans ce répertoire.

>[!NOTE]
>
>Si vous ne définissez pas ce paramètre de manière identique sur chaque machine de votre grappe Web sur laquelle [!DNL Sensor] est installé, l’expérimentation contrôlée ne fonctionne pas.

Cette entrée peut être préconfigurée et rester dans le fichier de configuration [!DNL Sensor] en permanence sans effet négatif. Si le nom de fichier de configuration de l&#39;expérience spécifié n&#39;est pas trouvé par [!DNL Sensor] ou s&#39;il est vide (c&#39;est-à-dire qu&#39;il existe mais qu&#39;il n&#39;a pas de contenu), [!DNL Sensor] n&#39;effectue pas l&#39;expérience, consigne un événement d&#39;erreur sur le serveur HTTP et continue à fonctionner normalement à tous les autres égards.
