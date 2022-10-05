---
description: Instructions de désinstallation du serveur Insight, de la transformation ou du répéteur.
title: Désinstallation du logiciel
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Désinstallation du logiciel{#uninstalling-your-software}

{{eol}}

Instructions de désinstallation du serveur Insight, de la transformation ou du répéteur.

## Désinstallation de l’Adobe du serveur Insight {#section-7d7befe672854df79bb6c28ec02f6670}

1. Annulation de l’enregistrement de la variable [!DNL Insight Server] Service Windows.

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé. [!DNL Insight Server].

      Exemple : [!DNL C:\Adobe\Server\bin]

   1. A l’invite de commande, exécutez la commande suivante pour l’arrêter et l’annuler en tant que service sous Microsoft Windows :

      ```
      InsightServer64.exe /unregserver
      ```

1. Supprimez la variable [!DNL Insight Server] répertoire d’installation.

## Désinstallation de Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Procédez comme suit pour mettre à jour la variable [!DNL profile.cfg] pour chaque profil que vous utilisez [!DNL Transform].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

   1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Le [!DNL profile.cfg] s’affiche.

   1. Dans le [!DNL profile.cfg] , supprimez la [!DNL Transform] entrée de profil à partir du vecteur Répertoires.

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL profile.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Supprimez la variable [!DNL Transform] à partir du dossier [!DNL Profiles] dans votre dossier [!DNL Insight Server] répertoire d’installation.

## Désinstallation de Répéteur {#section-2f94141d956749d88f549dbea26e5272}

1. Annulation de l’enregistrement de la variable [!DNL Repeater] Service Windows.

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé. [!DNL Repeater].

      Exemple : [!DNL D:\Adobe\Repeater\bin]

   1. A l’invite de commande, exécutez la commande suivante pour l’arrêter et l’annuler en tant que service sous Microsoft Windows :

      ```
      InsightServer64.exe /unregserver
      ```

1. Supprimez la variable [!DNL Repeater] répertoire d’installation.
