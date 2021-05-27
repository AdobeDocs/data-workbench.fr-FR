---
description: Avant que le tableau de bord puisse fonctionner, vous devez lui permettre d’accéder à SQL Server.
title: Configuration de SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Configuration de SQL Server{#configuring-the-sql-server}

Avant que le tableau de bord puisse fonctionner, vous devez lui permettre d’accéder à SQL Server.

1. Ouvrez SQL Management Studio en tant qu’administrateur.
1. Ajoutez une nouvelle connexion en cliquant avec le bouton droit de la souris sur **[!UICONTROL Logins]** et en sélectionnant **[!UICONTROL New Login]**.
1. Saisissez le nom d’identité complet du pool d’applications.

   Par défaut, l’identité du pool d’applications est nommée d’après le pool d’applications. Si vous choisissez `dashboard`, l’identité sera nommée `IIS AppPool\dashboard`. 1. Sélectionnez **[!UICONTROL Server Roles]** et vérifiez le rôle **[!UICONTROL dbcreator]**.
1. Cliquez sur **[!UICONTROL OK]** pour ajouter le nouvel utilisateur.
