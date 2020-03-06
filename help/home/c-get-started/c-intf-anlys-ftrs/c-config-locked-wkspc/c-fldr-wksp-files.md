---
description: Dans le dossier Workspaces du répertoire d’installation des Outils de données, un fichier folder.lock indique si les espaces de travail de ce dossier particulier sont verrouillés, tandis qu’un fichier workspace name.lock indique si un espace de travail particulier est verrouillé.
solution: Analytics
title: Fichiers Folder.lock et workspace.lock
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fichiers Folder.lock et workspace.lock{#folder-lock-and-workspace-lock-files}

Dans le dossier Workspaces du répertoire d’installation des Outils de données, un fichier folder.lock indique si les espaces de travail de ce dossier particulier sont verrouillés, tandis qu’un fichier workspace name.lock indique si un espace de travail particulier est verrouillé.

Lorsque vous verrouillez des dossiers entiers, vous pouvez les verrouiller au niveau du dossier Workspaces ou au niveau du sous-dossier (onglet). Vous pouvez également verrouiller ou déverrouiller tous vos dossiers (au niveau du dossier Workspaces), puis spécifier les exceptions pour des sous-dossiers particuliers (à l’aide de [!DNL folder.lock] fichiers) ou des espaces de travail particuliers (à l’aide de fichiers *workspace name*.lock).

L’exemple suivant illustre trois éléments : [!DNL Profile Manager]

* Un [!DNL folder.lock] fichier pour le dossier Workspaces principal
* Un [!DNL Monthly Numbers.lock] fichier pour le fichier [!DNL Monthly Numbers.vw] de l’espace de travail

* Un [!DNL folder.lock] fichier pour le sous-dossier Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

Dans cet exemple, le [!DNL Workspaces folder.lock] fichier est défini sur verrouillé, ce qui verrouille tous les espaces de travail de cette instance des Outils de données. Le [!DNL folder.lock] fichier de sous-dossier Workspaces\Custom est déverrouillé, ce qui déverrouille tous les espaces de travail sur l’ [!DNL Custom] onglet. Enfin, le [!DNL Monthly Numbers.lock] fichier est défini sur verrouillé, ce qui verrouille l’espace de travail Numéros mensuels.

## Création de fichiers .lock {#section-c4f78b4b43c347368a376904effb41d2}

Vous pouvez créer un [!DNL new folder.lock] fichier à l’aide de l’ [!DNL Create menu] option dans [!DNL Profile Manager] ou dans le [!DNL Workspaces Manager]. Vous pouvez également créer un fichier [!DNL folder.lock] ou nom *.lock de l’* espace de travail en copiant et en collant un [!DNL .lock] fichier existant dans le dossier approprié, en modifiant le nom du fichier (pour les fichiers nom **.lock de l’espace de travail uniquement) et en modifiant le paramètre du fichier si nécessaire.

**Pour créer un fichier folder.lock**

1. Dans les Outils de données, ouvrez le fichier [!DNL Workspaces Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant sur **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Cliquez sur le dossier pour lequel vous souhaitez créer un [!DNL folder.lock] fichier.
1. Dans la [!DNL User] colonne de ce dossier, cliquez avec le bouton droit de la souris dans la cellule et cliquez sur **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Un [!DNL new folder.lock] fichier apparaît. [!DNL New folder.lock] sont définis sur [déverrouillé] par défaut.
1. (Facultatif) Si vous devez modifier le paramètre du fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche du fichier.
   1. Cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL folder.lock] fichier s&#39;ouvre.

   1. Définissez le paramètre sur [verrouillé].
   1. Enregistrez et fermez le fichier.

1. Pour définir ce paramètre pour tous les utilisateurs travaillant avec le même profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Les espaces de travail de ce dossier sont désormais verrouillés ou déverrouillés selon le paramètre défini dans le nouveau fichier.

**Pour créer un fichier .lock à partir d’un fichier existant**

1. Dans le [!DNL Profile Manager] ou [!DNL Workspaces Manager], cliquez avec le bouton droit de la souris sur la coche d’un [!DNL .lock] fichier existant, puis cliquez sur **[!UICONTROL Copy]**.
1. Dans la [!DNL User] colonne du dossier dans lequel vous souhaitez coller le [!DNL .lock] fichier, cliquez avec le bouton droit de la souris dans la cellule et cliquez sur **[!UICONTROL Paste]**.
1. Si ce fichier est utilisé pour verrouiller un espace de travail individuel, cliquez avec le bouton droit de la souris sur la coche du [!DNL .lock] fichier dans la [!DNL User] colonne et modifiez son nom dans le [!DNL File] champ pour qu’il corresponde au nom de l’espace de travail à verrouiller.

   Par exemple, pour verrouiller l’ [!DNL Monthly Numbers.vw] espace de travail, vous devez nommer le fichier &quot; [!DNL Monthly Numbers.lock]&quot;.Si ce fichier est utilisé pour verrouiller un espace de travail individuel, cliquez avec le bouton droit de la souris sur la coche du [!DNL .lock] fichier dans la [!DNL User] colonne et modifiez son nom dans le [!DNL File] champ pour qu’il corresponde au nom de l’espace de travail à verrouiller. Par exemple, pour verrouiller l’ [!DNL Monthly Numbers.vw] espace de travail, vous devez nommer le fichier &quot; [!DNL Monthly Numbers.lock]&quot;.

1. Pour modifier le paramètre du fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche du fichier.
   1. Cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL .lock] fichier s&#39;ouvre.

   1. Définissez le paramètre sur [verrouillé] ou [déverrouillé].
   1. Enregistrez et fermez le fichier.

1. Pour définir ce paramètre pour tous les utilisateurs travaillant avec le même profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Les espaces de travail sélectionnés sont désormais verrouillés ou déverrouillés selon le paramètre défini dans le nouveau fichier.
