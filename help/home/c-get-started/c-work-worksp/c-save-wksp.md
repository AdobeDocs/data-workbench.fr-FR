---
description: Par défaut, la fermeture d’un espace de travail déverrouillé enregistre toutes les modifications apportées à l’espace de travail.
title: Enregistrer un espace de travail
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Enregistrer un espace de travail{#save-a-workspace}

Par défaut, la fermeture d’un espace de travail déverrouillé enregistre toutes les modifications apportées à l’espace de travail.

Si l&#39;espace de travail est un espace de travail serveur, vos modifications ne sont enregistrées que localement, sauf si vous enregistrez spécifiquement l&#39;espace de travail mis à jour sur le serveur Data Workbench. Pour plus d’informations sur les espaces de travail verrouillés, voir [Déverrouillage d’un espace de travail](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Enregistrer un espace de travail en local {#section-3f331c880f1a490c96844103c2432d61}

L’emplacement d’enregistrement par défaut est le dossier **User\profil name\Workspaces\tab name** dans le répertoire d’installation du Data Workbench. Par exemple, si vous travaillez avec le profil Films et que vous enregistrez un espace de travail localement à partir de l&#39;onglet [!UICONTROL Custom], l&#39;espace de travail est enregistré dans le dossier **User\Movies\Workspaces\Custom** du répertoire d&#39;installation du Data Workbench.

**Pour enregistrer les modifications dans un espace de travail**

* Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis sur **[!UICONTROL Save]**.

**Pour enregistrer un espace de travail existant en tant que nouvel espace de travail**

1. Sous l&#39;onglet [!DNL Worktop] de votre choix, cliquez sur la miniature de l&#39;espace de travail à afficher.
1. Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis sur **[!UICONTROL Save Copy As]**.
1. Dans la boîte de dialogue [!DNL Save Workspace As], indiquez le nom et l&#39;emplacement d&#39;enregistrement de l&#39;espace de travail copié, puis cliquez sur **[!UICONTROL Save]**.

## Enregistrer un espace de travail sur le serveur Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Seuls les utilisateurs disposant des autorisations appropriées peuvent enregistrer des espaces de travail sur le serveur Data Workbench. Pour plus d&#39;informations, contactez votre administrateur système.

L’enregistrement des espaces de travail sur le serveur de Data Workbench connecté est également appelé publication d’un espace de travail, car il rend l’espace de travail accessible à d’autres utilisateurs. Par défaut, les espaces de travail sont enregistrés dans le dossier *nom du profil de travail*\Workspaces\*nom_onglet* du serveur Data Workbench. Par exemple, si vous travaillez avec le profil Films et que vous enregistrez un espace de travail sur le serveur de Data Workbench connecté à partir de l&#39;onglet [!DNL Custom], l&#39;espace de travail est enregistré dans le dossier Movies\Workspaces\Custom folder of the Data Workbench server.

**Pour enregistrer un espace de travail sur le serveur Data Workbench**

* Sous l&#39;onglet [!DNL Worktop] de votre choix, cliquez avec le bouton droit de la souris sur la miniature de l&#39;espace de travail que vous souhaitez enregistrer sur le serveur Data Workbench, puis cliquez sur **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
