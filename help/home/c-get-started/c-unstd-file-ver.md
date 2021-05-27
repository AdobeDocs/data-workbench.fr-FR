---
description: Le plan de travail facilite la détermination de l’emplacement de stockage de chaque espace de travail, qu’il se trouve sur le serveur du Data Workbench, sur votre ordinateur local ou sur les deux.
title: Contrôle de version des fichiers
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 2%

---

# Contrôle de version des fichiers{#file-versioning}

Le plan de travail facilite la détermination de l’emplacement de stockage de chaque espace de travail, qu’il se trouve sur le serveur du Data Workbench, sur votre ordinateur local ou sur les deux.

## Identification des versions de fichier {#section-d555c96b016344f19b356c12213dd2a9}

**Serveur**

Un espace de travail de serveur est stocké sur le serveur de Data Workbench connecté et est disponible pour tous les utilisateurs ayant accès à ce profil et à cet onglet. Un espace de travail du serveur s’affiche sous la forme d’une seule miniature.

![](assets/wsp_thumb_server.png)

Les espaces de travail du serveur sont stockés par défaut dans le sous-dossier approprié du dossier Espaces de travail du serveur Data Workbench connecté.

**Local**

Un espace de travail local est la version locale d’un espace de travail de serveur. Un espace de travail local s’affiche sous la forme de deux miniatures qui se chevauchent. La miniature sur le haut est initialement entourée d’une lueur, ce qui indique que des modifications récentes ont été apportées localement à l’espace de travail du serveur. Cette lueur se dissipe au fil du temps.

![](assets/wsp_thumb_local.png)

Les espaces de travail locaux sont stockés par défaut dans le dossier [!DNL User\working profile name\Workspaces\tab] name du répertoire d’installation du Data Workbench (ou Insight).

>[!NOTE]
>
>Lorsque vous disposez d’une version locale d’un espace de travail de serveur, vous devez revenir à la version du serveur avant de pouvoir télécharger une version mise à jour de l’espace de travail du serveur. Pour revenir à la version du serveur sans modifications locales, cliquez avec le bouton droit de la souris sur la miniature de l’espace de travail local et cliquez sur **[!UICONTROL Revert to server version]**.

**Utilisateur**

Un espace de travail utilisateur est un espace de travail qui a été créé sur et qui existe uniquement sur l’ordinateur local. Un espace de travail utilisateur s’affiche sous la forme d’une miniature unique avec le contour en pointillés d’un espace de travail vierge derrière lui, indiquant qu’il n’existe aucun espace de travail source sur le serveur de Data Workbench connecté.

![](assets/wsp_thumb_user.png)

Les espaces de travail utilisateur sont stockés par défaut dans le dossier User\*working profile name*\Workspaces\*tab name* du répertoire d’installation Insight.
