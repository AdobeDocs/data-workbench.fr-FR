---
description: Worktop permet de déterminer facilement où est stocké chaque espace de travail, qu’il se trouve sur le serveur Outils de données, sur votre ordinateur local ou sur les deux.
solution: Analytics
title: Version des fichiers
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Version des fichiers{#file-versioning}

Worktop permet de déterminer facilement où est stocké chaque espace de travail, qu’il se trouve sur le serveur Outils de données, sur votre ordinateur local ou sur les deux.

## Identification des versions de fichiers {#section-d555c96b016344f19b356c12213dd2a9}

**Serveur**

Un espace de travail serveur est stocké sur le serveur des outils de données connecté et est accessible à tous les utilisateurs qui ont accès à ce profil et à cet onglet. Un espace de travail serveur s’affiche sous la forme d’une seule miniature.

![](assets/wsp_thumb_server.png)

Les espaces de travail du serveur sont stockés par défaut dans le sous-dossier approprié du dossier Workspaces du serveur de outils de données connecté.

**Local**

Un espace de travail local est la version locale d’un espace de travail serveur. Un espace de travail local s’affiche sous la forme de deux miniatures qui se chevauchent. La miniature en haut est entourée d’une lueur qui indique que des modifications récentes ont été apportées localement à l’espace de travail du serveur. Cette lueur se dissipe au fil du temps.

![](assets/wsp_thumb_local.png)

Les espaces de travail locaux sont stockés par défaut dans le dossier des [!DNL User\working profile name\Workspaces\tab] noms du répertoire d’installation des outils de données (ou d’Insight).

>[!NOTE]
>
>Lorsque vous disposez d’une version locale d’un espace de travail serveur, vous devez revenir à la version serveur avant de pouvoir télécharger une version mise à jour de l’espace de travail serveur. Pour revenir à la version du serveur sans modifications locales, cliquez avec le bouton droit de la souris sur la vignette de l’espace de travail local et cliquez sur **[!UICONTROL Revert to server version]**.

**Utilisateur**

Un espace de travail utilisateur est un espace de travail qui a été créé sur l’ordinateur local et qui existe uniquement sur cet ordinateur. Un espace de travail utilisateur s’affiche sous la forme d’une miniature unique avec un contour en pointillé d’un espace de travail vierge derrière, indiquant qu’il n’existe aucun espace de travail source sur le serveur des outils de données connecté.

![](assets/wsp_thumb_user.png)

Les espaces de travail utilisateur sont stockés par défaut dans le dossier User\*working profile name*\Workspaces\*tab name* du répertoire d’installation d’Insight.
