---
description: Par défaut, la fermeture d’un espace de travail déverrouillé enregistre les modifications apportées à l’espace de travail.
solution: Analytics
title: Enregistrement d’un espace de travail
topic: Data workbench
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Enregistrement d’un espace de travail{#save-a-workspace}

Par défaut, la fermeture d’un espace de travail déverrouillé enregistre les modifications apportées à l’espace de travail.

Si l’espace de travail est un espace de travail serveur, vos modifications ne sont enregistrées que localement, sauf si vous enregistrez spécifiquement l’espace de travail mis à jour sur le serveur Outils de données. Pour plus d’informations sur les espaces de travail verrouillés, voir [Déverrouillage d’un espace de travail](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Enregistrement local d’un espace de travail {#section-3f331c880f1a490c96844103c2432d61}

L’emplacement d’enregistrement par défaut est le dossier **User\profile name\Workspaces\tab name** dans le répertoire d’installation des outils de données. Par exemple, si vous travaillez avec le profil Films et que vous enregistrez un espace de travail localement à partir de l’ [!UICONTROL Custom] onglet, l’espace de travail est enregistré dans le dossier **User\Movies\Workspaces\Custom** du répertoire d’installation des outils de données.

**Pour enregistrer les modifications dans un espace de travail**

* Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis **[!UICONTROL Save]**.

**Pour enregistrer un espace de travail existant en tant que nouvel espace de travail**

1. Sur l’ [!DNL Worktop] onglet de votre choix, cliquez sur la miniature de l’espace de travail à afficher.
1. Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis sur **[!UICONTROL Save Copy As]**.
1. Dans la [!DNL Save Workspace As] boîte de dialogue, indiquez le nom et l’emplacement d’enregistrement de l’espace de travail copié, puis cliquez sur **[!UICONTROL Save]**.

## Enregistrement d’un espace de travail sur le serveur Outils de données {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Seuls les utilisateurs disposant des autorisations appropriées peuvent enregistrer les espaces de travail sur le serveur Outils de données. Pour plus d’informations, contactez votre administrateur système.

L’enregistrement des espaces de travail sur le serveur des outils de données connecté est également appelé publication d’un espace de travail, car il rend l’espace de travail accessible à d’autres utilisateurs. Par défaut, les espaces de travail sont enregistrés dans le dossier *\Workspaces\*nom**onglet* du serveur Outils de données. Par exemple, si vous travaillez avec le profil Films et que vous enregistrez un espace de travail sur le serveur des outils de données connecté à partir de l’ [!DNL Custom] onglet, l’espace de travail est enregistré dans le dossier Movies\Workspaces\Custom folder of the Data Workbench server.

**Pour enregistrer un espace de travail sur le serveur Outils de données**

* Sous l’ [!DNL Worktop] onglet de votre choix, cliquez avec le bouton droit de la souris sur la miniature de l’espace de travail à enregistrer sur le serveur Outils de données, puis cliquez sur **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
