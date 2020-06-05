---
description: L’étape finale consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.
solution: Analytics
title: Initialisation du Tableau de bord
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Initialisation du Tableau de bord{#initializing-the-dashboard}

L’étape finale consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.

1. Ouvrez un navigateur Web et saisissez l’URL du site récemment déployé (par exemple, http://localhost/dashboard).
1. La première fois que vous vous connectez, les tables de base de données sont configurées, ce qui peut occasionner un léger retard.
1. Les informations d&#39;identification de connexion initiales sont les suivantes :

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Lors de votre première connexion, accédez à **[!UICONTROL User]** > **[!UICONTROL Account Settings]** et sélectionnez **[!UICONTROL Change Password]** pour modifier votre mot de passe administrateur.

L&#39;installation du tableau de bord est maintenant terminée. Si ce n’est déjà fait, suivez les instructions détaillées de la section Préparation des outils de données de ce guide pour configurer votre communication avec les serveurs des outils de données et pour gérer les utilisateurs et les groupes.

>[!NOTE]
>
>Les journaux d&#39;erreurs de Tableau de bord et d&#39;audit se trouvent dans le [!DNL logs] répertoire du chemin d&#39;installation.

>[!NOTE]
>
>Si vous devez changer l’identité du pool d’applications en un autre compte, veillez à accorder l’accès à la base de données et à lui accorder l’accès en lecture/écriture au dossier [!DNL logs] du chemin d’installation.

>[!NOTE]
>
>Si vous devez modifier la chaîne de connexion de la base de données, modifiez simplement la valeur à l’aide de la **[!UICONTROL IIS Management Console]**.
