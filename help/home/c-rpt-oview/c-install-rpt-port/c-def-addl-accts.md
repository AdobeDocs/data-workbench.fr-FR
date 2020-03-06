---
description: Les utilisateurs doivent disposer d’un compte valide et fournir un nom de compte et un mot de passe lorsqu’ils accèdent au portail des rapports.
solution: Analytics
title: Définir des comptes supplémentaires
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définir des comptes supplémentaires{#define-additional-accounts}

Les utilisateurs doivent disposer d’un compte valide et fournir un nom de compte et un mot de passe lorsqu’ils accèdent au portail des rapports.

Par défaut, l’authentification des utilisateurs est activée dans [!DNL Report Portal].

La liste des comptes valides pour [!DNL Report Portal] est conservée dans le fichier de base de données, [!DNL portal.mdb]. [!DNL Report Portal] est installé avec un compte avec des privilèges d’administration :

* Nom du compte : test
* Mot de passe : utilisateur

>[!NOTE]
>
>Pour des raisons de sécurité, Adobe vous recommande de modifier le mot de passe de ce compte après l’installation [!DNL Report Portal].

Pour ajouter des comptes utilisateur [!DNL Report Portal] ou modifier des informations relatives à des comptes existants, utilisez l’ [!DNL Admin] onglet de l’ [!DNL Report Portal] interface utilisateur.

Chaque fois que vous ajoutez un nouveau compte ou modifiez un compte existant, un courrier électronique de confirmation est envoyé comme spécifié dans le [!DNL email.asp] fichier du dossier \*PortalName*\PortalASP. Pour plus d’informations, voir [Modification du fichier](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)Email.asp.

Pour savoir comment ajouter d’autres utilisateurs, voir [Utilisation de comptes](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Vous pouvez également désactiver l’authentification des utilisateurs et autoriser l’accès anonyme à [!DNL Report Portal]. Pour connaître les étapes nécessaires, consultez les informations relatives au paramètre Session(&quot;In&quot;) dans [Modifier le fichier](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)de configuration de la session.

