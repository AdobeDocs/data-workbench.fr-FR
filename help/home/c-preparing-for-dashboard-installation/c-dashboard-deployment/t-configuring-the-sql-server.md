---
description: Avant que le tableau de bord puisse fonctionner, vous devez l'autoriser à accéder à SQL Server.
solution: Analytics
title: Configuration de SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de SQL Server{#configuring-the-sql-server}

Avant que le tableau de bord puisse fonctionner, vous devez l&#39;autoriser à accéder à SQL Server.

1. Ouvrez SQL Management Studio en tant qu’administrateur.
1. Ajoutez une nouvelle connexion en cliquant avec le bouton droit **[!UICONTROL Logins]** et en sélectionnant **[!UICONTROL New Login]**.
1. Entrez le nom d&#39;identité complet du pool d&#39;applications.

   Par défaut, l’identité du pool d’applications est nommée d’après le pool d’applications. Si vous le choisissez `dashboard`, l&#39;identité sera nommée `IIS AppPool\dashboard`. 1. Sélectionnez **[!UICONTROL Server Roles]** et vérifiez le **[!UICONTROL dbcreator]** rôle.
1. Click **[!UICONTROL OK]** to add the new user.
