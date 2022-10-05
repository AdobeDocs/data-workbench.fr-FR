---
description: Avant que le tableau de bord puisse fonctionner, vous devez lui permettre d’accéder à SQL Server.
title: Configuration de SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Configuration de SQL Server{#configuring-the-sql-server}

{{eol}}

Avant que le tableau de bord puisse fonctionner, vous devez lui permettre d’accéder à SQL Server.

1. Ouvrez SQL Management Studio en tant qu’administrateur.
1. Ajouter une nouvelle connexion en cliquant avec le bouton droit de la souris **[!UICONTROL Logins]** et sélection **[!UICONTROL New Login]**.
1. Saisissez le nom d’identité complet du pool d’applications.

   Par défaut, l’identité du pool d’applications est nommée d’après le pool d’applications. Si vous choisissez `dashboard`, l’identité sera nommée. `IIS AppPool\dashboard`. 1. Sélectionnez **[!UICONTROL Server Roles]** et vérifiez la variable **[!UICONTROL dbcreator]** rôle.
1. Cliquez sur **[!UICONTROL OK]** pour ajouter le nouvel utilisateur.
