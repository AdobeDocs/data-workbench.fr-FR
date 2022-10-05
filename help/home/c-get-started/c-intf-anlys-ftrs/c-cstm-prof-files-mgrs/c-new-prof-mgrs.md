---
description: Le Gestionnaire de profils affiche tous les répertoires associés à votre profil de travail.
title: Création d’un gestionnaire de profil
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Création d’un gestionnaire de profil{#create-a-profile-manager}

{{eol}}

Le Gestionnaire de profils affiche tous les répertoires associés à votre profil de travail.

Vous pouvez accéder à un sous-répertoire du [!DNL Profile Manager] sans avoir à parcourir l’ensemble de sa structure de répertoires. Par exemple, la variable [!DNL Metrics] et [!DNL Workspaces] options de menu disponibles dans la [!DNL Manage] du menu de la fenêtre de l’espace de travail vous permet d’ouvrir les dossiers Mesures et espaces de travail du Gestionnaire de profils , respectivement.

Pour plus d’informations sur la variable [!DNL Profile Manager], voir [Gestionnaire de profils](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Par défaut, vous avez accès aux gestionnaires suivants :

* **[!DNL Metrics Manager]:** Affiche le contenu du dossier Mesures du Gestionnaire de profils. Vous pouvez ouvrir, modifier, supprimer ou copier les mesures définies dans chaque profil.
* **[!DNL Reports Manager]:** Affiche le contenu du dossier Rapports du Gestionnaire de profils. Vous pouvez ouvrir, modifier, supprimer ou copier des espaces de travail de rapport ou [!DNL report.cfg] fichiers .

* **[!DNL Workspaces Manager]:** Affiche le contenu du dossier Espaces de travail du Gestionnaire de profils. Tous les fichiers pour configurer la variable [!DNL Worktop]Les onglets de se trouvent ici. Voir [Personnalisation des onglets du plan de travail](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench vous permet de créer d’autres gestionnaires de profil qui affichent un sous-répertoire à partir du [!DNL Profile Manager]. Chaque gestionnaire que vous créez doit comporter une [!DNL .vw] qui spécifie l’objet [!DNL Profile Manager] répertoire dont il affiche le contenu et les propriétés de cette fenêtre. Vous pouvez utiliser la variable [!DNL .vw] pour l’un des gestionnaires fournis en tant que modèle.

**Pour créer un gestionnaire de profil**

1. Dans le [!DNL Profile Manager], cliquez sur le bouton **[!UICONTROL Menu]** pour afficher son contenu.
1. Dans le répertoire des menus, cliquez sur le bouton **[!UICONTROL Admin]** puis le répertoire **[!UICONTROL Profile]** répertoire . Le [!DNL .vw] les fichiers des gestionnaires existants se trouvent ici.
1. Dans le *nom du profil* , cliquez avec le bouton droit de la souris sur la coche de l’une des colonnes [!DNL .vw] fichiers (par exemple, [!DNL Workspaces.vw]), puis cliquez sur **[!UICONTROL Make Local]**.

   Une coche pour le fichier apparaît dans la variable [!DNL User] colonne .

1. Cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL .vw] dans le fichier [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Dans le [!DNL Profile Path] , saisissez la variable [!DNL Profile Manager] pour lequel vous souhaitez créer un gestionnaire. Veillez à inclure la barre oblique (/) après le nom du répertoire.

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

1. Dans Notepad, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier modifié dans la fonction *Dossier d’installation de Data Workbench*\User\*nom du profil de travail*\Menu\Admin\Profile Management.

   Veillez à modifier le nom de la variable [!DNL .vw] pour refléter le répertoire dans la variable [!DNL Profile Manager] à laquelle elle correspond.

1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL .vw] dans le fichier [!DNL User] et cliquez sur **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
