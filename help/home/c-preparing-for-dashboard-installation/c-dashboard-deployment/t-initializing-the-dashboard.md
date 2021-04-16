---
description: L’étape finale consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.
title: Initialisation du tableau de bord
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# Initialisation du tableau de bord{#initializing-the-dashboard}

L’étape finale consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.

1. Ouvrez un navigateur Web et saisissez l’URL du site récemment déployé (par exemple, http://localhost/dashboard).
1. La première fois que vous vous connectez, les tables de base de données sont configurées, ce qui peut occasionner un léger retard.
1. Les informations d&#39;identification de connexion initiales sont les suivantes :

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Lors de votre première connexion, accédez à **[!UICONTROL User]** > **[!UICONTROL Account Settings]** et sélectionnez **[!UICONTROL Change Password]** pour modifier le mot de passe de votre administrateur.

L&#39;installation du tableau de bord est maintenant terminée. Si vous ne l’avez pas déjà fait, suivez les instructions détaillées dans la section Préparation du Data Workbench de ce guide pour configurer votre communication avec les serveurs des outils de données et pour gérer les utilisateurs et les groupes.

>[!NOTE]
>
>Les journaux d&#39;erreurs et d&#39;audit du tableau de bord se trouvent dans le répertoire [!DNL logs] du chemin d&#39;installation.

>[!NOTE]
>
>Si vous devez changer l&#39;identité du pool d&#39;applications en un autre compte, veillez à accorder l&#39;accès à la base de données et à lui accorder l&#39;accès en lecture/écriture au dossier [!DNL logs] du chemin d&#39;installation.

>[!NOTE]
>
>Si vous devez modifier la chaîne de connexion de la base de données, modifiez simplement la valeur en utilisant **[!UICONTROL IIS Management Console]**.
