---
description: Instructions de désinstallation d’Insight Server, Transform ou Repeater.
title: Désinstallation du logiciel
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Désinstallation du logiciel{#uninstalling-your-software}

Instructions de désinstallation d’Insight Server, Transform ou Repeater.

## Désinstallation de l’Adobe du serveur Insight {#section-7d7befe672854df79bb6c28ec02f6670}

1. Annulez l&#39;enregistrement du service Windows [!DNL Insight Server].

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé [!DNL Insight Server].

      Exemple : [!DNL C:\Adobe\Server\bin]

   1. A l&#39;invite de commande, exécutez la commande suivante pour l&#39;arrêter et l&#39;annuler en tant que service sous Microsoft Windows :

      ```
      InsightServer64.exe /unregserver
      ```

1. Supprimez le répertoire d&#39;installation [!DNL Insight Server].

## Désinstallation de la transformation {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Suivez les étapes ci-après pour mettre à jour le fichier [!DNL profile.cfg] pour chaque profil avec lequel vous utilisiez [!DNL Transform].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La fenêtre [!DNL profile.cfg] s&#39;affiche.

   1. Dans la fenêtre [!DNL profile.cfg], supprimez l&#39;entrée de profil [!DNL Transform] du vecteur Répertoires.

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

1. Supprimez le dossier [!DNL Transform] du dossier [!DNL Profiles] de votre répertoire d&#39;installation [!DNL Insight Server].

## Désinstallation de Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Annulez l&#39;enregistrement du service Windows [!DNL Repeater].

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé [!DNL Repeater].

      Exemple : [!DNL D:\Adobe\Repeater\bin]

   1. A l&#39;invite de commande, exécutez la commande suivante pour l&#39;arrêter et l&#39;annuler en tant que service sous Microsoft Windows :

      ```
      InsightServer64.exe /unregserver
      ```

1. Supprimez le répertoire d&#39;installation [!DNL Repeater].
