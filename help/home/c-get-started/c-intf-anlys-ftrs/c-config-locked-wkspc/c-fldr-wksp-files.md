---
description: Dans le dossier Espaces de travail du répertoire d’installation de votre Data Workbench, un fichier folder.lock indique si les espaces de travail de ce dossier particulier sont verrouillés, tandis qu’un fichier nom.lock de l’espace de travail indique si un espace de travail particulier est verrouillé.
title: Fichiers folder.lock et workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Fichiers folder.lock et workspace.lock{#folder-lock-and-workspace-lock-files}

{{eol}}

Dans le dossier Espaces de travail du répertoire d’installation de votre Data Workbench, un fichier folder.lock indique si les espaces de travail de ce dossier particulier sont verrouillés, tandis qu’un fichier nom.lock de l’espace de travail indique si un espace de travail particulier est verrouillé.

Lors du verrouillage de dossiers entiers, vous pouvez les verrouiller au niveau du dossier Espaces de travail ou au niveau du sous-dossier (onglet). Vous pouvez également verrouiller ou déverrouiller tous vos dossiers (au niveau du dossier Espaces de travail), puis spécifier les exceptions pour des sous-dossiers particuliers (à l’aide de [!DNL folder.lock] fichiers) ou certains espaces de travail (en utilisant *nom de l&#39;espace de travail* fichiers .lock).

L’exemple suivant de la variable [!DNL Profile Manager] met en évidence trois éléments :

* A [!DNL folder.lock] pour le dossier principal Espaces de travail
* A [!DNL Monthly Numbers.lock] pour le fichier [!DNL Monthly Numbers.vw] fichier workspace

* A [!DNL folder.lock] pour le sous-dossier Espaces de travail\Personnalisé

![](assets/wsp_Locking_lockFiles.png)

Dans cet exemple, la variable [!DNL Workspaces folder.lock] est défini sur verrouillé, ce qui verrouille tous les espaces de travail de cette instance de Data Workbench. Sous-dossier Espaces de travail\Personnalisés [!DNL folder.lock] est défini sur unlocked, ce qui déverrouille tous les espaces de travail sur le [!DNL Custom] . Enfin, la [!DNL Monthly Numbers.lock] est défini sur verrouillé, ce qui verrouille l’espace de travail des numéros mensuels .

## Création de fichiers .lock {#section-c4f78b4b43c347368a376904effb41d2}

Vous pouvez créer un [!DNL new folder.lock] à l’aide du fichier [!DNL Create menu] dans le [!DNL Profile Manager] ou le [!DNL Workspaces Manager]. Vous pouvez également créer une [!DNL folder.lock] ou *nom de l&#39;espace de travail* fichier .lock en copiant et en collant un fichier existant [!DNL .lock] dans le dossier approprié, en modifiant le nom du fichier (pour *nom de l&#39;espace de travail* fichiers .lock uniquement) et modifier le paramètre dans le fichier si nécessaire.

**Pour créer un fichier folder.lock**

1. Dans Data Workbench, ouvrez le [!DNL Workspaces Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Cliquez sur le dossier pour lequel vous souhaitez créer un [!DNL folder.lock] fichier .
1. Dans le [!DNL User] pour ce dossier, cliquez avec le bouton droit dans la cellule, puis cliquez sur **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] s’affiche. [!DNL New folder.lock] Les fichiers sont définis sur [unlocked] par défaut.
1. (Facultatif) Si vous devez modifier le paramètre dans le fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche du fichier.
   1. Cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL folder.lock] s’ouvre.

   1. Modifiez le paramètre en [verrouillé].
   1. Enregistrez le fichier, puis fermez-le.

1. Pour définir ce paramètre pour tous les utilisateurs travaillant avec le même profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Les espaces de travail de ce dossier sont désormais verrouillés ou déverrouillés selon le paramètre défini dans le nouveau fichier.

**Pour créer un fichier .lock à partir d’un fichier existant**

1. Dans le [!DNL Profile Manager] ou [!DNL Workspaces Manager], cliquez avec le bouton droit de la souris sur la coche d’une [!DNL .lock] et cliquez sur **[!UICONTROL Copy]**.
1. Dans le [!DNL User] pour le dossier dans lequel vous souhaitez coller le [!DNL .lock] , cliquez avec le bouton droit dans la cellule, puis cliquez sur **[!UICONTROL Paste]**.
1. Si ce fichier est utilisé pour verrouiller un espace de travail individuel, cliquez avec le bouton droit de la souris sur la coche de la fonction [!DNL .lock] dans le fichier [!DNL User] et modifiez son nom dans la variable [!DNL File] pour correspondre au nom de l’espace de travail que vous souhaitez verrouiller.

   Par exemple, pour verrouiller la variable [!DNL Monthly Numbers.vw] workspace, vous nommeriez le fichier &quot; [!DNL Monthly Numbers.lock].&quot;Si ce fichier est utilisé pour verrouiller un espace de travail individuel, cliquez avec le bouton droit de la souris sur la coche de la fonction [!DNL .lock] dans le fichier [!DNL User] et modifiez son nom dans la variable [!DNL File] pour correspondre au nom de l’espace de travail que vous souhaitez verrouiller. Par exemple, pour verrouiller la variable [!DNL Monthly Numbers.vw] workspace, vous nommeriez le fichier &quot; [!DNL Monthly Numbers.lock].&quot;

1. Pour modifier le paramètre du fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche du fichier.
   1. Cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL .lock] s’ouvre.

   1. Modifiez le paramètre en [verrouillé] ou [unlocked].
   1. Enregistrez le fichier, puis fermez-le.

1. Pour définir ce paramètre pour tous les utilisateurs travaillant avec le même profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Les espaces de travail sélectionnés sont désormais verrouillés ou déverrouillés selon le paramètre défini dans le nouveau fichier.
