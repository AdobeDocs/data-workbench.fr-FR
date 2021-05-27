---
description: Le Gestionnaire de profils affiche tous les répertoires associés à votre profil de travail.
title: Création d’un gestionnaire de profil
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Création d’un gestionnaire de profil{#create-a-profile-manager}

Le Gestionnaire de profils affiche tous les répertoires associés à votre profil de travail.

Vous pouvez accéder à un sous-répertoire de [!DNL Profile Manager] sans avoir à parcourir l’ensemble de sa structure de répertoires. Par exemple, les options de menu [!DNL Metrics] et [!DNL Workspaces] disponibles dans le menu [!DNL Manage] du menu de la fenêtre de l’espace de travail vous permettent d’ouvrir respectivement les dossiers Mesures et Espaces de travail du Gestionnaire de profils .

Pour plus d’informations sur [!DNL Profile Manager], voir [Gestionnaire de profils](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Par défaut, vous avez accès aux gestionnaires suivants :

* **[!DNL Metrics Manager]:** affiche le contenu du dossier Mesures du Gestionnaire de profils. Vous pouvez ouvrir, modifier, supprimer ou copier les mesures définies dans chaque profil.
* **[!DNL Reports Manager]:** affiche le contenu du dossier Rapports du Gestionnaire de profils. Vous pouvez ouvrir, modifier, supprimer ou copier des espaces de travail de rapport ou des fichiers [!DNL report.cfg].

* **[!DNL Workspaces Manager]:** affiche le contenu du dossier Espaces de travail du Gestionnaire de profils. Tous les fichiers pour la configuration des onglets de [!DNL Worktop] se trouvent ici. Voir [Personnalisation des onglets du plan de travail](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench vous permet de créer des gestionnaires de profil supplémentaires qui affichent un sous-répertoire à partir de [!DNL Profile Manager]. Chaque gestionnaire que vous créez doit comporter un fichier [!DNL .vw] qui spécifie le répertoire [!DNL Profile Manager] dont le contenu s’affiche et les propriétés de cette fenêtre. Vous pouvez utiliser le fichier [!DNL .vw] comme modèle pour n’importe quel responsable fourni.

**Pour créer un gestionnaire de profil**

1. Dans le répertoire [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]** pour en visualiser le contenu.
1. Dans le répertoire des menus, cliquez sur le répertoire **[!UICONTROL Admin]**, puis sur le répertoire **[!UICONTROL Profile]**. Les fichiers [!DNL .vw] des gestionnaires existants se trouvent ici.
1. Dans la colonne *nom du profil*, cliquez avec le bouton droit de la souris sur la coche de l’un des fichiers [!DNL .vw] (par exemple, [!DNL Workspaces.vw]), puis cliquez sur **[!UICONTROL Make Local]**.

   Une coche pour le fichier apparaît dans la colonne [!DNL User].

1. Cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL .vw] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Dans le champ [!DNL Profile Path] , saisissez le répertoire [!DNL Profile Manager] pour lequel vous souhaitez créer un gestionnaire. Veillez à inclure la barre oblique (/) après le nom du répertoire.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. Dans le Bloc-notes, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier modifié dans le *dossier d’installation du Data Workbench*\User\*nom du profil de travail*\Menu\Admin\Profile Management.

   Veillez à modifier le nom du fichier [!DNL .vw] pour refléter le répertoire dans la [!DNL Profile Manager] auquel il correspond.

1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit sur la coche du fichier [!DNL .vw] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > &lt; &lt;a3/&quot;.**[!UICONTROL working profile name]**
