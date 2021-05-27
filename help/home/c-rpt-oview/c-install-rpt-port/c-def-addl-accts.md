---
description: Les utilisateurs doivent disposer d’un compte valide et fournir un nom de compte et un mot de passe lorsqu’ils accèdent au portail de rapports.
title: Définir des comptes supplémentaires
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Définir des comptes supplémentaires

Les utilisateurs doivent disposer d’un compte valide et fournir un nom de compte et un mot de passe lorsqu’ils accèdent au portail de rapports.

Par défaut, l’authentification des utilisateurs est activée dans [!DNL Report Portal].

La liste des comptes valides pour [!DNL Report Portal] est conservée dans le fichier de base de données, [!DNL portal.mdb]. [!DNL Report Portal] est installé avec un compte pourvu de droits d’administrateur :

* Nom du compte : test
* Mot de passe : user

>[!NOTE]
>
>Pour des raisons de sécurité, Adobe vous recommande de modifier le mot de passe de ce compte après l’installation de [!DNL Report Portal].

Pour ajouter des comptes utilisateurs à [!DNL Report Portal] ou modifier des informations relatives à des comptes existants, utilisez l’onglet [!DNL Admin] de l’interface utilisateur de [!DNL Report Portal].

Chaque fois que vous ajoutez un nouveau compte ou modifiez un compte existant, un email de confirmation est envoyé, comme indiqué dans le fichier [!DNL email.asp] du dossier \*PortalName*\PortalASP. Pour plus d’informations, voir [Modifier le fichier Email.asp](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Pour connaître les étapes permettant d’ajouter d’autres utilisateurs, voir [Utilisation de comptes](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Vous pouvez éventuellement désactiver l’authentification des utilisateurs et autoriser l’accès anonyme à [!DNL Report Portal]. Pour connaître les étapes à suivre, consultez les informations sur le paramètre Session(&quot;In&quot;) dans [Modifier le fichier de configuration de session](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
