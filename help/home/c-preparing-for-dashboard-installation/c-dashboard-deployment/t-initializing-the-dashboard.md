---
description: La dernière étape consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.
title: Initialisation du tableau de bord
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# Initialisation du tableau de bord{#initializing-the-dashboard}

La dernière étape consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.

1. Ouvrez un navigateur web et saisissez l’URL du site nouvellement déployé (par exemple, http://localhost/dashboard).
1. La première connexion permet de configurer les tables de la base de données, ce qui peut entraîner un léger retard.
1. Les informations d’identification de connexion initiales sont les suivantes :

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Lors de votre première connexion, accédez à **[!UICONTROL User]** > **[!UICONTROL Account Settings]** et sélectionnez **[!UICONTROL Change Password]** pour modifier le mot de passe de votre administrateur.

L’installation du tableau de bord est maintenant terminée. Si ce n’est déjà fait, suivez les instructions de la section Préparation du Data Workbench de ce guide pour configurer votre communication avec les serveurs Data Workbench et pour gérer les utilisateurs et les groupes.

>[!NOTE]
>
>Les journaux d’erreurs des tableaux de bord et d’audit se trouvent dans le répertoire [!DNL logs] du chemin d’installation.

>[!NOTE]
>
>Si vous devez changer l’identité du pool d’applications en un autre compte, assurez-vous d’accorder l’accès à la base de données et d’accorder l’accès en lecture/écriture à l’identité au dossier [!DNL logs] dans le chemin d’installation.

>[!NOTE]
>
>Si vous devez modifier la chaîne de connexion de la base de données, modifiez simplement la valeur à l’aide de la balise **[!UICONTROL IIS Management Console]**.
