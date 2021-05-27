---
description: Configurez le fichier insight.zbin pour définir la langue de l’application cliente.
title: Configuration des langues localisées
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Configuration des langues localisées{#setting-up-localized-languages}

Configurez le fichier insight.zbin pour définir la langue de l’application cliente.

## Mise à jour des composants du serveur Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

L’administrateur doit d’abord effectuer les tâches suivantes pour mettre à jour les composants de serveur suivants :

1. **Mise à jour vers le serveur Data Workbench 6.x.** Vous devez mettre à jour le serveur Data Workbench pour la localisation en mettant à jour le  [!DNL base\localization\*.zbin] fichier. Ce fichier [!DNL insight.zbin] sera alors copié dans le client.

   Un fichier [!DNL insight.zbin] est inclus dans le dossier d’installation à côté du fichier [!DNL insight.exe]. Si vous vous connectez à un serveur qui ne vous fournit pas de fichiers [!DNL .zbin] spécifiques à la langue, Data Workbench utilisera ce fichier.

   Le fichier [!DNL insight.zbin] de sauvegarde peut être fourni dans n’importe quelle langue. Par conséquent, si vous utilisez Data Workbench en chinois et que vous vous connectez à un serveur qui ne prend pas en charge cette langue, votre client Data Workbench sera toujours en chinois, même si le serveur modifie votre profil de base et supprime vos fichiers [!DNL .zbin] du dossier [!DNL Base/Localization].

1. **Mettez à jour le serveur de rapports Data Workbench.** Le dossier racine  [!DNL insight.zbin] du serveur de rapports Data Workbench est en anglais par défaut. En tant qu’administrateur, vous devrez sélectionner et copier le fichier [!DNL .zbin] du package de serveur de rapports mis à jour et le placer dans le répertoire racine du serveur de rapports Data Workbench. Comme le client, le serveur de rapports nécessite également les arguments appropriés pour la langue sélectionnée, tels que [!DNL Insight.exe -zh-cn]

   1. Arrêtez les services du serveur de rapports.
   1. Copiez le dossier [!DNL Localization] du nouveau package du serveur de rapports.
   1. Dans le dossier [!DNL Localization] , copiez le fichier [!DNL Insight.zbin] et placez-le dans le répertoire racine du serveur de rapports où se trouve [!DNL Insight.exe].

   1. Ajoutez les arguments requis, tels que [!DNL insight.exe -zh-cn]
   1. Redémarrez le serveur de rapports.

## Mise à jour du client Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Après la mise à jour du serveur, procédez comme suit pour mettre à jour chaque client.

1. Pour vous assurer que le client n’est pas mis à jour à partir du serveur lors de cette mise à jour, définissez votre argument [!DNL Insight.cfg] sur False.

   ```
   Update Software = bool: false
   ```

1. Redémarrez le client.
1. Accédez au profil Software and Docs (profil SoftDocs) et téléchargez le fichier **[!UICONTROL insight.zbin]** requis à partir du package client : [!DNL Software\Insight Client\Insight_6.1.zip]

1. Déplacez le fichier [!DNL insight.zbin] vers le dossier où se trouve [!DNL insight.exe].

1. Pour vous assurer que les fichiers client sont maintenant mis à jour à partir du serveur, remplacez l’argument de fichier [!DNL Insight.cfg] par True :

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Votre client se synchronise avec le serveur et un message vous indique qu’il est en train de se mettre à jour. À la fin du téléchargement, vous recevrez un message vous demandant si vous souhaitez redémarrer votre client.

1. Cliquez sur **OK** pour redémarrer le client.

Si vous obtenez le message suivant, cela signifie que le fichier [!DNL zbin] n’a pas été placé au même emplacement que le [!DNL Insight.exe].

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
