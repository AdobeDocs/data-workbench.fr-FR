---
description: Le Gestionnaire de profils affiche tous les répertoires associés à votre profil de travail.
solution: Analytics
title: Création d’un gestionnaire de profils
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Création d’un gestionnaire de profils{#create-a-profile-manager}

Le Gestionnaire de profils affiche tous les répertoires associés à votre profil de travail.

Vous pouvez accéder à un sous-répertoire du [!DNL Profile Manager] sans avoir à parcourir l’intégralité de sa structure de répertoires. Par exemple, les options [!DNL Metrics] et [!DNL Workspaces] de menu disponibles dans le [!DNL Manage] menu de la fenêtre de l’espace de travail vous permettent d’ouvrir respectivement les dossiers Mesures du Gestionnaire de profils et Espaces de travail.

Pour plus d’informations sur le [!DNL Profile Manager], voir [Le Gestionnaire](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)de profils.

Par défaut, vous avez accès aux gestionnaires suivants :

* **[!DNL Metrics Manager]:**Affiche le contenu du dossier Mesures du Gestionnaire de profils. Vous pouvez ouvrir, modifier, supprimer ou copier les mesures définies dans chaque profil.
* **[!DNL Reports Manager]:**Affiche le contenu du dossier Rapports du Gestionnaire de profils. Vous pouvez ouvrir, modifier, supprimer ou copier des espaces de travail ou des[!DNL report.cfg]fichiers de rapport.

* **[!DNL Workspaces Manager]:**Affiche le contenu du dossier des espaces de travail du gestionnaire de profils. Tous les fichiers permettant de configurer les onglets[!DNL Worktop]sont situés ici. Voir[Personnalisation des onglets](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)de Worktop.

Les outils de données vous permettent de créer d’autres gestionnaires de profil qui affichent un sous-répertoire à partir du [!DNL Profile Manager]. Chaque gestionnaire que vous créez doit disposer d’un [!DNL .vw] fichier qui spécifie le [!DNL Profile Manager] répertoire dont il affiche le contenu et les propriétés de cette fenêtre. Vous pouvez utiliser le [!DNL .vw] fichier pour n’importe quel gestionnaire fourni comme modèle.

**Pour créer un gestionnaire de profils**

1. Dans [!DNL Profile Manager], cliquez sur le **[!UICONTROL Menu]** répertoire pour afficher son contenu.
1. Dans le répertoire Menu, cliquez sur le **[!UICONTROL Admin]** répertoire, puis sur le **[!UICONTROL Profile]** répertoire. Les [!DNL .vw] dossiers des gestionnaires existants sont disponibles ici.
1. Dans la colonne Nom *du* profil, cliquez avec le bouton droit de la souris sur la coche correspondant à l’un des [!DNL .vw] fichiers (par exemple, [!DNL Workspaces.vw]), puis cliquez sur **[!UICONTROL Make Local]**.

   Une coche du fichier apparaît dans la [!DNL User] colonne.

1. Cliquez avec le bouton droit de la souris sur la coche du [!DNL .vw] fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Dans le [!DNL Profile Path] champ, saisissez le [!DNL Profile Manager] répertoire pour lequel vous souhaitez créer un nouveau gestionnaire. Veillez à inclure la barre oblique (/) après le nom du répertoire.

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

1. Dans le Bloc-notes, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier modifié dans le dossier *d’installation des outils de* données \User\*nom du profil de travail*\Menu\Admin\Profile Management.

   Veillez à modifier le nom du [!DNL .vw] fichier afin qu’il reflète le répertoire [!DNL Profile Manager] auquel il correspond.

1. (Facultatif) Pour rendre les modifications accessibles à tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche du [!DNL .vw] fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

