---
description: Cette section décrit la procédure à suivre pour désinstaller l’outil de donnéesGeography.
solution: Analytics
title: Désinstallation de la géographie des outils de données
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Désinstallation de la géographie des outils de données{#uninstalling-data-workbench-geography}

Cette section décrit la procédure à suivre pour désinstaller l’outil de donnéesGeography.

>[!NOTE]
>
>Si le profil avec lequel vous utilisez l’outil de données [!DNL Geography] est exécuté sur une grappe de serveurs de l’outil de données, désinstallez le [!DNL Geography] profil du serveur de l’outil de données maître de la grappe.

1. Procédez comme suit pour mettre à jour le [!DNL profile.cfg] fichier pour chaque profil avec lequel vous utilisiez les outils de données [!DNL Geography].

   1. Ouvrez le [!DNL Profile Manager].
   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL profile.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL profile.cfg] fenêtre s&#39;affiche.

   1. Dans la [!DNL profile.cfg] fenêtre, supprimez l’entrée de [!DNL Geography] profil du [!DNL Directories] vecteur.

   1. Si vous avez utilisé un service de données, supprimez l’entrée [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] de profil du [!DNL Directories] vecteur.

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL profile.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Supprimez le dossier Geography du dossier Profils du répertoire d’installation du serveur de l’outil de données.
1. Si vous avez utilisé un service de données, supprimez le dossier Géo-intelligence IP ou Géolocalisation IP du dossier Profils du répertoire d’installation du serveur de l’outil de données.
1. Supprimez le dossier Geography du dossier Lookups dans le répertoire d’installation du serveur de l’outil de données.
1. Si vous avez utilisé un service de données, supprimez le dossier Géo-intelligence IP ou Géolocalisation IP du dossier Recherches dans le répertoire d’installation du serveur de l’outil de données.
1. Si vous avez créé de nouvelles images de terrain, supprimez le [!DNL Terrain Images.cfg] fichier du dossier Composants du répertoire d’installation du serveur de l’outil de données.
