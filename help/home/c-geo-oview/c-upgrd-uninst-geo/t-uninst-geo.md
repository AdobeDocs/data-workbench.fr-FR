---
description: Procédure de désinstallation de Data WorkbenchGeography.
title: Désinstallation de Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Désinstallation de Data Workbench Geography{#uninstalling-data-workbench-geography}

{{eol}}

Procédure de désinstallation de Data WorkbenchGeography.

>[!NOTE]
>
>Si le profil avec lequel vous utilisez Data Workbench [!DNL Geography] s’exécute sur une grappe de serveurs Data Workbench, désinstallez la variable [!DNL Geography] profil du serveur de Data Workbench maître dans la grappe.

1. Procédez comme suit pour mettre à jour la variable [!DNL profile.cfg] fichier pour chaque profil avec lequel vous utilisez Data Workbench [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

   1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL profile.cfg] s’affiche.

   1. Dans le [!DNL profile.cfg] , supprimez la [!DNL Geography] entrée de profil à partir de [!DNL Directories] vectoriel.

   1. Si vous avez utilisé un service de données, supprimez la variable [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] entrée de profil à partir de [!DNL Directories] vectoriel.

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL profile.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Supprimez le dossier Geography du dossier Profils du répertoire d’installation du serveur Data Workbench.
1. Si vous avez utilisé un service de données, supprimez le dossier Géo-intelligence IP ou Géolocalisation IP du dossier Profils dans le répertoire d’installation du serveur Data Workbench.
1. Supprimez le dossier Geography du dossier Lookups du répertoire d’installation du serveur Data Workbench.
1. Si vous avez utilisé un service de données, supprimez le dossier Géo-intelligence IP ou Géolocalisation IP du dossier Recherches du répertoire d’installation du serveur Data Workbench.
1. Si vous avez créé de nouvelles images du terrain, supprimez la variable [!DNL Terrain Images.cfg] à partir du dossier Components du répertoire d’installation du serveur data workbench.
