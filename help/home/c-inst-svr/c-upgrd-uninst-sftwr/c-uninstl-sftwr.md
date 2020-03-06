---
description: Instructions pour désinstaller Insight Server, Transform ou Repeater.
solution: Insight
title: Désinstallation de votre logiciel
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Désinstallation de votre logiciel{#uninstalling-your-software}

Instructions pour désinstaller Insight Server, Transform ou Repeater.

## Désinstallation d’Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Annulez l’enregistrement du service [!DNL Insight Server] Windows.

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé [!DNL Insight Server].

      Exemple : [!DNL C:\Adobe\Server\bin]

   1. A l’invite de commande, exécutez la commande suivante pour l’arrêter et l’annuler en tant que service sous Microsoft Windows :

      ```
      InsightServer64.exe /unregserver
      ```

1. Supprimez le répertoire [!DNL Insight Server] d’installation.

## Désinstallation de Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Suivez les étapes ci-après pour mettre à jour le [!DNL profile.cfg] fichier de chaque profil avec lequel vous utilisiez [!DNL Transform].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL profile.cfg] fenêtre s&#39;affiche.

   1. Dans la [!DNL profile.cfg] fenêtre, supprimez l’entrée de [!DNL Transform] profil du vecteur Répertoires.

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Supprimez le [!DNL Transform] dossier du [!DNL Profiles] dossier dans votre répertoire [!DNL Insight Server] d’installation.

## Désinstallation de Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Annulez l’enregistrement du service [!DNL Repeater] Windows.

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé [!DNL Repeater].

      Exemple : [!DNL D:\Adobe\Repeater\bin]

   1. A l’invite de commande, exécutez la commande suivante pour l’arrêter et l’annuler en tant que service sous Microsoft Windows :

      ```
      InsightServer64.exe /unregserver
      ```

1. Supprimez le répertoire [!DNL Repeater] d’installation.

