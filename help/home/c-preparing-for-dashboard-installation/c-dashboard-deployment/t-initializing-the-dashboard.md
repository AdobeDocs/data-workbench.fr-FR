---
description: La dernière étape consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.
solution: Analytics
title: Initialisation du tableau de bord
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Initialisation du tableau de bord{#initializing-the-dashboard}

La dernière étape consiste à exécuter le tableau de bord pour la première fois afin de l’autoriser à s’initialiser.

1. Ouvrez un navigateur Web et saisissez l’URL du site nouvellement déployé (par exemple, http://localhost/dashboard).
1. Pour la première fois, la connexion va configurer les tables de base de données, ce qui peut entraîner un léger retard.
1. Les informations d’identification de connexion initiales sont les suivantes :

* **[!UICONTROL Username]**: admin
* **[!UICONTROL Password]**: password

1. Lors de votre première connexion, accédez à **[!UICONTROL User]** > **[!UICONTROL Account Settings]** et sélectionnez **[!UICONTROL Change Password]** pour modifier le mot de passe de votre administrateur.
>L&#39;installation du tableau de bord est maintenant terminée. Si vous ne l’avez pas déjà fait, suivez les instructions de la section >
><!-->
>Préparation de l&#39;outil de données>
>-->
>Dans chaque section de ce guide, configurez votre communication avec les serveurs des outils de données et gérez les utilisateurs et les groupes. >
>>[!NOTE]
>>
>>Les journaux d’erreur et d’audit des tableaux de bord se trouvent dans le [!DNL logs] répertoire du chemin d’installation.
>[!NOTE]
Si vous devez changer l’identité du pool d’applications en un autre compte, veillez à accorder l’accès à la base de données et à lui accorder l’accès en lecture/écriture au [!DNL logs] dossier du chemin d’installation.
>[!NOTE]
Si vous devez modifier la chaîne de connexion de la base de données, modifiez simplement la valeur à l’aide de la **[!UICONTROL IIS Management Console]**.
>
>
>
