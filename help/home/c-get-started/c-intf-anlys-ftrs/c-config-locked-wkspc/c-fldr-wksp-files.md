---
description: Dans le dossier Espaces de travail du répertoire d’installation de votre Data Workbench, un fichier folder.lock indique si les espaces de travail de ce dossier particulier sont verrouillés, tandis qu’un fichier nom.lock de l’espace de travail indique si un espace de travail particulier est verrouillé.
title: Fichiers folder.lock et workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Fichiers folder.lock et workspace.lock{#folder-lock-and-workspace-lock-files}

Dans le dossier Espaces de travail du répertoire d’installation de votre Data Workbench, un fichier folder.lock indique si les espaces de travail de ce dossier particulier sont verrouillés, tandis qu’un fichier nom.lock de l’espace de travail indique si un espace de travail particulier est verrouillé.

Lors du verrouillage de dossiers entiers, vous pouvez les verrouiller au niveau du dossier Espaces de travail ou au niveau du sous-dossier (onglet). Vous pouvez également verrouiller ou déverrouiller tous vos dossiers (au niveau du dossier Espaces de travail), puis spécifier les exceptions pour des sous-dossiers particuliers (à l’aide de fichiers [!DNL folder.lock]) ou des espaces de travail particuliers (à l’aide des fichiers *nom de l’espace de travail*.lock).

L’exemple suivant de [!DNL Profile Manager] met en évidence trois éléments :

* Un fichier [!DNL folder.lock] pour le dossier principal Espaces de travail
* Un fichier [!DNL Monthly Numbers.lock] pour le fichier de l’espace de travail [!DNL Monthly Numbers.vw]

* Un fichier [!DNL folder.lock] pour le sous-dossier Espaces de travail\Personnalisé

![](assets/wsp_Locking_lockFiles.png)

Dans cet exemple, le fichier [!DNL Workspaces folder.lock] est défini sur verrouillé, ce qui verrouille tous les espaces de travail de cette instance de Data Workbench. Le fichier [!DNL folder.lock] sous-dossier Espaces de travail\Personnalisé est déverrouillé, ce qui déverrouille tous les espaces de travail sur l’onglet [!DNL Custom]. Enfin, le fichier [!DNL Monthly Numbers.lock] est défini sur verrouillé, ce qui verrouille l’espace de travail des numéros mensuels .

## Création de fichiers .lock {#section-c4f78b4b43c347368a376904effb41d2}

Vous pouvez créer un fichier [!DNL new folder.lock] à l’aide de l’option [!DNL Create menu] dans la balise [!DNL Profile Manager] ou [!DNL Workspaces Manager]. Vous pouvez également créer un fichier [!DNL folder.lock] ou *nom de l’espace de travail*.lock en copiant et en collant un fichier [!DNL .lock] existant dans le dossier approprié, en modifiant le nom du fichier (pour les fichiers *nom de l’espace de travail*.lock uniquement) et en modifiant le paramètre dans le fichier si nécessaire.

**Pour créer un fichier folder.lock**

1. Dans Data Workbench, ouvrez le [!DNL Workspaces Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Cliquez sur le dossier pour lequel vous souhaitez créer un fichier [!DNL folder.lock].
1. Dans la colonne [!DNL User] de ce dossier, cliquez avec le bouton droit dans la cellule, puis cliquez sur **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Un fichier [!DNL new folder.lock] s’affiche. [!DNL New folder.lock] Par défaut, les fichiers sont définis sur  [] unverrouedunlockedle.
1. (Facultatif) Si vous devez modifier le paramètre dans le fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche du fichier.
   1. Cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier [!DNL folder.lock] s’ouvre.

   1. Définissez le paramètre sur [locked].
   1. Enregistrez le fichier, puis fermez-le.

1. Pour définir ce paramètre pour tous les utilisateurs travaillant avec le même profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Les espaces de travail de ce dossier sont désormais verrouillés ou déverrouillés selon le paramètre défini dans le nouveau fichier.

**Pour créer un fichier .lock à partir d’un fichier existant**

1. Dans la balise [!DNL Profile Manager] ou [!DNL Workspaces Manager], cliquez avec le bouton droit de la souris sur la coche d’un fichier [!DNL .lock] existant, puis cliquez sur **[!UICONTROL Copy]**.
1. Dans la colonne [!DNL User] du dossier dans lequel vous souhaitez coller le fichier [!DNL .lock], cliquez avec le bouton droit dans la cellule, puis cliquez sur **[!UICONTROL Paste]**.
1. Si ce fichier est utilisé pour verrouiller un espace de travail individuel, cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL .lock] dans la colonne [!DNL User] et modifiez son nom dans le champ [!DNL File] pour qu’il corresponde au nom de l’espace de travail que vous souhaitez verrouiller.

   Par exemple, pour verrouiller l’espace de travail [!DNL Monthly Numbers.vw], nommez le fichier &quot;[!DNL Monthly Numbers.lock]&quot;.Si ce fichier est utilisé pour verrouiller un espace de travail individuel, cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL .lock] dans la colonne [!DNL User] et modifiez son nom dans le champ [!DNL File] pour qu’il corresponde au nom de l’espace de travail que vous souhaitez verrouiller. Par exemple, pour verrouiller l’espace de travail [!DNL Monthly Numbers.vw], nommez le fichier &quot;[!DNL Monthly Numbers.lock]&quot;.

1. Pour modifier le paramètre du fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche du fichier.
   1. Cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier [!DNL .lock] s’ouvre.

   1. Définissez le paramètre sur [locked] ou [unlocked].
   1. Enregistrez le fichier, puis fermez-le.

1. Pour définir ce paramètre pour tous les utilisateurs travaillant avec le même profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Les espaces de travail sélectionnés sont désormais verrouillés ou déverrouillés selon le paramètre défini dans le nouveau fichier.
