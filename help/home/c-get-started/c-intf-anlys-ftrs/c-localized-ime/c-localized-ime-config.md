---
description: Configurez le fichier insight.zbin pour définir la langue de l’application cliente.
title: Configuration des langues localisées
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration des langues localisées{#setting-up-localized-languages}

Configurez le fichier insight.zbin pour définir la langue de l’application cliente.

## Mise à jour des composants du serveur de l’outil de données {#section-5d07a081befc4eaa8fdf7fea904e0d48}

L’administrateur doit d’abord effectuer les tâches suivantes pour mettre à jour les composants du serveur :

1. **Mise à jour vers le serveur de l’outil de données version 6.x.** Vous devez mettre à jour le serveur de l’outil de données pour la localisation en mettant à jour le [!DNL base\localization\*.zbin] fichier. Ce [!DNL insight.zbin] fichier sera alors copié sur le client.

   Un [!DNL insight.zbin] fichier est inclus dans le dossier d’installation à côté du [!DNL insight.exe] fichier. Si vous vous connectez à un serveur qui ne vous fournit pas de [!DNL .zbin] fichiers spécifiques à une langue, les outils de données utiliseront ce fichier.

   Le [!DNL insight.zbin] fichier de sauvegarde peut être fourni dans n’importe quelle langue. Par conséquent, si vous utilisez des outils de données en chinois et que vous vous connectez à un serveur qui ne prend pas en charge cette langue, votre client de ces outils de données sera toujours en chinois, même si le serveur modifie votre profil de base et supprime vos [!DNL .zbin] fichiers du [!DNL Base/Localization] dossier.

1. **Mettez à jour le serveur de rapports de l’outil de données.** Par défaut, le dossier racine [!DNL insight.zbin] du serveur de rapports de l’outil de données est en anglais. En tant qu’administrateur, vous devrez sélectionner et copier le [!DNL .zbin] fichier du package du serveur de rapports mis à jour et le placer dans le répertoire racine du serveur de rapports de l’outil de données. Tout comme le client, le serveur de rapports nécessite également les arguments appropriés pour la langue sélectionnée, tels que [!DNL Insight.exe -zh-cn]

   1. Arrêtez les services du serveur de rapports.
   1. Copiez le [!DNL Localization] dossier du nouveau package du serveur de rapports.
   1. Dans le [!DNL Localization] dossier, copiez le [!DNL Insight.zbin] fichier et placez-le dans le répertoire racine du serveur de rapports sur lequel se trouve le [!DNL Insight.exe] dossier.

   1. Ajoutez les arguments requis, tels que [!DNL insight.exe -zh-cn]
   1. Redémarrez le serveur de rapports.

## Mise à jour du client de l’outil de données {#section-9653d3fcaf2a4337a97b685857e7aeac}

Après la mise à jour du serveur, procédez comme suit pour mettre à jour chaque client.

1. Pour vous assurer que le client n’est pas mis à jour à partir du serveur pendant cette mise à jour, définissez votre [!DNL Insight.cfg] argument sur False.

   ```
   Update Software = bool: false
   ```

1. Redémarrez le client.
1. Accédez au profil Software and Docs (profil SoftDocs) et téléchargez le **[!UICONTROL insight.zbin]** fichier requis à partir du package client : [!DNL Software\Insight Client\Insight_6.1.zip]

1. Déplacez le [!DNL insight.zbin] fichier vers le dossier [!DNL insight.exe] .

1. Pour vous assurer que les fichiers client sont désormais mis à jour à partir du serveur, définissez l’argument [!DNL Insight.cfg] de fichier sur True :

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Votre client se synchronise avec le serveur et un message s’affiche indiquant qu’il est en cours de mise à jour. A la fin du téléchargement, vous recevrez un message vous demandant si vous souhaitez redémarrer votre client.

1. Cliquez sur **OK** pour redémarrer le client.

Si vous obtenez le message suivant, cela signifie que le [!DNL zbin] fichier n’a pas été placé au même emplacement que le [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Ecrans de démarrage localisés**

Les outils de données recherchent les fichiers d’écran de démarrage suivants :

* Anglais (par défaut) : [!DNL Base/Images/<version_product> Splash.png]
* Chinois (démarré avec -zh-cn) : [!DNL Base/Images/<version_product> Splash zh-cn.png].

Si un écran de démarrage est demandé mais manquant, les outils de données accèdent par défaut à l’écran de démarrage en anglais.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

