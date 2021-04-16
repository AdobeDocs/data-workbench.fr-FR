---
description: Procédure de désinstallation des outils de donnéesGeography.
title: Désinstallation de Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Désinstallation de Data Workbench Geography{#uninstalling-data-workbench-geography}

Procédure de désinstallation des outils de donnéesGeography.

>[!NOTE]
>
>Si le profil avec lequel vous utilisez les outils de données [!DNL Geography] s’exécute sur un cluster de serveurs de l’outil de données, désinstallez le profil [!DNL Geography] du serveur de l’outil de données maître de la grappe.

1. Suivez les étapes ci-après pour mettre à jour le fichier [!DNL profile.cfg] pour chaque profil avec lequel vous utilisiez les outils de données [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre [!DNL profile.cfg] s&#39;affiche.

   1. Dans la fenêtre [!DNL profile.cfg], supprimez l&#39;entrée de profil [!DNL Geography] du vecteur [!DNL Directories].

   1. Si vous avez utilisé un service de données, supprimez l&#39;entrée de profil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] du vecteur [!DNL Directories].

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

1. Supprimez le dossier Geography du dossier Profils du répertoire d’installation du serveur de l’outil de données.
1. Si vous utilisez un service de données, supprimez le dossier Géo-intelligence IP ou Géolocalisation IP du dossier Profils dans le répertoire d’installation du serveur de l’outil de données.
1. Supprimez le dossier Geography du dossier Lookups dans le répertoire d’installation du serveur de l’outil de données.
1. Si vous utilisez un service de données, supprimez le dossier Géo-intelligence IP ou Géolocalisation IP du dossier Recherches dans le répertoire d’installation du serveur de l’outil de données.
1. Si vous avez créé de nouvelles images de terrain, supprimez le fichier [!DNL Terrain Images.cfg] du dossier Composants du répertoire d’installation du serveur de l’outil de données.
