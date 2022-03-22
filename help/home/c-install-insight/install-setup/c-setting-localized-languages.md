---
description: Configurez le fichier insight.zbin pour définir la langue de l’application cliente.
title: Configuration de Localized Languages insight.zbin
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Configuration des langues localisées{#setting-up-localized-languages}

Configurez le fichier insight.zbin pour définir la langue de l’application cliente.

## Mise à jour des composants du serveur Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

L’administrateur doit d’abord effectuer les tâches suivantes pour mettre à jour les composants de serveur suivants :

1. **Mise à jour vers le serveur Data Workbench 6.x.** Vous devez mettre à jour le serveur Data Workbench pour la localisation en mettant à jour le [!DNL base\localization\*.zbin] fichier . Ceci [!DNL insight.zbin] est alors copié vers le client.

   Un [!DNL insight.zbin] est inclus dans le dossier d’installation à côté du dossier [!DNL insight.exe] fichier . Si vous vous connectez à un serveur qui ne vous fournit pas de langue spécifique [!DNL .zbin] puis data workbench utilisera ce fichier.

   La sauvegarde [!DNL insight.zbin] peut être fourni dans n’importe quelle langue. Par conséquent, si vous utilisez Data Workbench en chinois et que vous vous connectez à un serveur qui ne prend pas en charge cette langue, votre client Data Workbench sera toujours en chinois, même si le serveur modifie votre profil de base et supprime votre [!DNL .zbin] des fichiers [!DNL Base/Localization] dossier.

1. **Mettez à jour le serveur de rapports Data Workbench.** Le [!DNL insight.zbin] Le dossier racine du serveur de rapports Data Workbench est en anglais par défaut. En tant qu’administrateur, vous devrez sélectionner et copier la variable [!DNL .zbin] à partir du package de serveur de rapports mis à jour et placez-le dans le répertoire racine du serveur de rapports data workbench. Comme le client, le serveur de rapports nécessite également les arguments appropriés pour la langue sélectionnée, tels que [!DNL Insight.exe -zh-cn]

   1. Arrêtez les services du serveur de rapports.
   1. Copiez le [!DNL Localization] à partir du nouveau package de serveur de rapports.
   1. Dans la [!DNL Localization] , copiez le dossier [!DNL Insight.zbin] et placez-le dans le répertoire racine du serveur de rapports où l’objet [!DNL Insight.exe] se trouve.

   1. Ajoutez les arguments requis, tels que [!DNL insight.exe -zh-cn]
   1. Redémarrez le serveur de rapports.

## Mise à jour du client Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Après la mise à jour du serveur, procédez comme suit pour mettre à jour chaque client.

1. Pour vous assurer que le client n’est pas mis à jour à partir du serveur lors de cette mise à jour, définissez votre [!DNL Insight.cfg] sur False.

   ```
   Update Software = bool: false
   ```

1. Redémarrez le client.
1. Accédez au profil Software and Docs (profil SoftDocs) et téléchargez les **[!UICONTROL insight.zbin]** à partir du package client : [!DNL Software\Insight Client\Insight_6.1.zip]

1. Déplacer le [!DNL insight.zbin] dans le dossier où [!DNL insight.exe] se trouve.

1. Pour vous assurer que les fichiers client sont désormais mis à jour à partir du serveur, modifiez la variable [!DNL Insight.cfg] argument de fichier sur True :

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Votre client se synchronise avec le serveur et un message vous indique qu’il est en train de se mettre à jour. À la fin du téléchargement, vous recevrez un message vous demandant si vous souhaitez redémarrer votre client.

1. Cliquez sur **OK** pour redémarrer le client.

Si vous obtenez le message suivant, cela signifie que la variable [!DNL zbin] n’a pas été placé au même emplacement que le fichier [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Écrans de démarrage localisés**

Data Workbench recherche les fichiers d’écran de démarrage suivants :

* Anglais (par défaut) : [!DNL Base/Images/<version_product> Splash.png]
* Chinois (démarré avec -zh-cn) : [!DNL Base/Images/<version_product> Splash zh-cn.png].

Si un écran de démarrage est demandé mais manquant, Data Workbench accède par défaut à l’écran de démarrage en anglais.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
