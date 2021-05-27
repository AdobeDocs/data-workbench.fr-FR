---
description: Par défaut, la fermeture d’un espace de travail déverrouillé enregistre toutes les modifications apportées à l’espace de travail.
title: Enregistrer un espace de travail
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Enregistrer un espace de travail{#save-a-workspace}

Par défaut, la fermeture d’un espace de travail déverrouillé enregistre toutes les modifications apportées à l’espace de travail.

Si l’espace de travail est un espace de travail de serveur, vos modifications ne sont enregistrées que localement, sauf si vous enregistrez spécifiquement l’espace de travail mis à jour sur le serveur de Data Workbench. Pour plus d’informations sur les espaces de travail verrouillés, voir [Déverrouillage d’un espace de travail](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Enregistrement local d’un espace de travail {#section-3f331c880f1a490c96844103c2432d61}

L’emplacement d’enregistrement par défaut est le dossier **User\profile name\Workspaces\tab name** dans le répertoire d’installation du Data Workbench. Par exemple, si vous utilisez le profil Films et que vous enregistrez un espace de travail localement à partir de l’onglet [!UICONTROL Custom] , l’espace de travail est enregistré dans le dossier **User\Movies\Workspaces\Custom** du répertoire d’installation de votre Data Workbench.

**Pour enregistrer les modifications dans un espace de travail**

* Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis sur **[!UICONTROL Save]**.

**Pour enregistrer un espace de travail existant en tant que nouvel espace de travail**

1. Sur l’onglet [!DNL Worktop] souhaité, cliquez sur la miniature de l’espace de travail que vous souhaitez afficher.
1. Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis sur **[!UICONTROL Save Copy As]**.
1. Dans la boîte de dialogue [!DNL Save Workspace As], indiquez le nom et l’emplacement où vous souhaitez enregistrer l’espace de travail copié, puis cliquez sur **[!UICONTROL Save]**.

## Enregistrez un espace de travail sur le serveur Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Seuls les utilisateurs disposant des autorisations appropriées peuvent enregistrer des espaces de travail sur le serveur Data Workbench. Pour plus d’informations, contactez votre administrateur système.

L’enregistrement des espaces de travail sur le serveur de Data Workbench connecté est également appelé publication d’un espace de travail, car il met cet espace de travail à la disposition d’autres utilisateurs. Par défaut, les espaces de travail sont enregistrés dans le dossier *nom du profil de travail*\Workspaces\*nom de l’onglet* du serveur de Data Workbench. Par exemple, si vous utilisez le profil Films et que vous enregistrez un espace de travail sur le serveur de Data Workbench connecté à partir de l’onglet [!DNL Custom] , l’espace de travail est enregistré dans le dossier Movies\Workspaces\Custom folder of the Data Workbench server.

**Enregistrement d’un espace de travail sur le serveur Data Workbench**

* Dans l’onglet [!DNL Worktop] de votre choix, cliquez avec le bouton droit sur la miniature de l’espace de travail que vous souhaitez enregistrer sur le serveur du Data Workbench, puis cliquez sur **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
