---
description: Configurez le fichier insight.zbin pour définir la langue de l’application cliente.
title: Configuration des langues localisées
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Configuration des langues localisées{#setting-up-localized-languages}

Configurez le fichier insight.zbin pour définir la langue de l’application cliente.

## Mettre à jour les composants du serveur de l&#39;outil de données {#section-5d07a081befc4eaa8fdf7fea904e0d48}

L’administrateur doit d’abord effectuer les tâches suivantes pour mettre à jour les composants de serveur suivants :

1. **Mise à jour vers le serveur de l’outil de données 6.x.** Vous devez mettre à jour le serveur de l’outil de données pour localisation en mettant à jour le  [!DNL base\localization\*.zbin] fichier. Ce fichier [!DNL insight.zbin] sera alors copié sur le client.

   Un fichier [!DNL insight.zbin] est inclus dans le dossier d&#39;installation à côté du fichier [!DNL insight.exe]. Si vous vous connectez à un serveur qui ne vous fournit pas de fichiers [!DNL .zbin] spécifiques à la langue, les outils de données utiliseront ce fichier.

   Le fichier de sauvegarde [!DNL insight.zbin] peut être fourni dans n&#39;importe quelle langue. Par conséquent, si vous utilisez les outils de données en chinois et que vous vous connectez à un serveur qui ne prend pas en charge cette langue, votre client de ces outils sera toujours en chinois, même si le serveur modifie votre profil de base et supprime vos fichiers [!DNL .zbin] du dossier [!DNL Base/Localization].

1. **Mettez à jour le serveur de rapports des outils de données.** Par défaut, le dossier racine  [!DNL insight.zbin] du serveur de rapports de l’outil de données est en anglais. En tant qu’administrateur, vous devrez sélectionner et copier le fichier [!DNL .zbin] du package du serveur de rapports mis à jour et le placer dans le répertoire racine du serveur de rapports de l’outil de données. Tout comme le client, le serveur de rapports nécessite également les arguments appropriés pour la langue sélectionnée, tels que [!DNL Insight.exe -zh-cn]

   1. Arrêtez les services du serveur de rapports.
   1. Copiez le dossier [!DNL Localization] du nouveau package du serveur de rapports.
   1. Dans le dossier [!DNL Localization], copiez le fichier [!DNL Insight.zbin] et placez-le dans le répertoire racine du serveur de rapports où se trouve [!DNL Insight.exe].

   1. Ajouter tous les arguments requis, tels que [!DNL insight.exe -zh-cn]
   1. Redémarrez le serveur de rapports.

## Mettre à jour le client de l&#39;outil de données {#section-9653d3fcaf2a4337a97b685857e7aeac}

Après la mise à jour du serveur, procédez comme suit pour mettre à jour chaque client.

1. Pour vous assurer que le client n&#39;est pas mis à jour à partir du serveur pendant cette mise à jour, définissez l&#39;argument [!DNL Insight.cfg] sur False.

   ```
   Update Software = bool: false
   ```

1. Redémarrez le client.
1. Accédez au profil Software and Docs (profil SoftDocs) et téléchargez le fichier **[!UICONTROL insight.zbin]** requis à partir du package client : [!DNL Software\Insight Client\Insight_6.1.zip]

1. Déplacez le fichier [!DNL insight.zbin] dans le dossier contenant [!DNL insight.exe].

1. Pour vous assurer que les fichiers client sont désormais mis à jour à partir du serveur, définissez l&#39;argument de fichier [!DNL Insight.cfg] sur True :

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Votre client se synchronise avec le serveur et vous verrez un message indiquant qu’il est en cours de mise à jour. À la fin du téléchargement, vous recevrez un message vous demandant si vous souhaitez redémarrer votre client.

1. Cliquez sur **OK** pour redémarrer le client.

Si vous obtenez le message suivant, cela signifie que le fichier [!DNL zbin] n&#39;a pas été placé au même emplacement que le fichier [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Ecrans de démarrage localisés**

Les outils de données recherchent les fichiers d’écran de démarrage suivants :

* Anglais (par défaut) : [!DNL Base/Images/<version_product> Splash.png]
* Chinois (démarré avec -zh-cn) : [!DNL Base/Images/<version_product> Splash zh-cn.png].

Si un écran de démarrage est demandé mais absent, les outils de données accèdent par défaut à l’écran de démarrage en anglais.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
