---
description: Procédure de modification des comptes d’utilisateurs existants.
solution: Analytics
title: Modification d’utilisateurs existants
topic: Data workbench
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification d’utilisateurs existants{#editing-existing-users}

Procédure de modification des comptes d’utilisateurs existants.

1. Dans la [!DNL Report Portal], cliquez sur l’ **[!UICONTROL Admin]** onglet. La [!DNL Admin] page s’affiche.

   ![](assets/report_admintag2.png)

1. Cliquez sur la lettre représentant la première lettre du nom du compte à modifier. Si, par exemple, vous souhaitez modifier le compte &quot;Marketing&quot;, cliquez sur la lettre &quot;M&quot;.

   Une liste des noms de compte commençant par cette lettre s’affiche.

1. Sélectionnez le nom du compte à modifier, puis cliquez sur le **[!UICONTROL select]** bouton. La [!DNL Edit Account Info] page s’affiche.

   ![Infos sur l’étape](assets/rptPort_scrn_AdminTab_editUser.png)

1. Modifiez uniquement les champs de cette page qui doivent être mis à jour. Le tableau suivant décrit chacun de ces champs :

   | Dans ce champ . . . | Spécifiez les . . . |
   |---|---|
   | email | Adresse électronique de l’utilisateur. |
   | ancien mot de passe | mot de passe actuel, qui doit être utilisé lors de la modification d’un compte administrateur ou lors de la réinitialisation du mot de passe d’un compte non administrateur. |
   | nouveau mot de passe | Nouveau mot de passe que l’utilisateur doit fournir lors de la connexion à [!DNL Report Portal]. |
   | confirmer le mot de passe | Nouveau mot de passe que l’utilisateur doit fournir lors de la connexion à [!DNL Report Portal]. |
   | accès au profil | Profils auxquels cet utilisateur est autorisé à accéder (par exemple, ProductSales). Pour autoriser l’accès à plusieurs profils, séparez les noms par des virgules. Si l’utilisateur est autorisé à accéder à tous les profils associés à [!DNL Report Portal], saisissez &quot;ALL&quot;. |
   | accès à l’onglet | Onglets auxquels cet utilisateur est autorisé à accéder (par exemple, [!DNL Admin]). Pour autoriser l’accès à plusieurs onglets, séparez les noms par des virgules. Si l’utilisateur est autorisé à accéder à tous les onglets du [!DNL Report Portal], tapez &quot;ALL&quot;. Ce champ, associé au champ Type de compte, est très utile pour définir les droits d’accès des groupes. |
   | type de compte | Indique si ce compte est destiné à un individu ou à un groupe. Les comptes individuels permettent aux utilisateurs de réinitialiser leurs mots de passe, contrairement aux groupes. Un administrateur est la seule personne capable de réinitialiser le mot de passe d’un compte de groupe. |
   | status | Indique si ce compte est actif ou inactif. La valeur par défaut est active. Pour désactiver un compte utilisateur, sélectionnez **[!UICONTROL inactive]**. |
   | admin | Autoriser cet utilisateur à créer, mettre à jour et supprimer des comptes d’utilisateurs, ainsi qu’à modifier les notes associées à chaque rapport. Le paramètre par défaut est false. Pour en faire un utilisateur administrateur, sélectionnez true. |
   | date d&#39;expiration | Date, au format MM/JJ/AAAA, jusqu’à laquelle cet utilisateur est autorisé à utiliser [!DNL Report Portal]. |

1. Cliquez sur **[!UICONTROL update]**.
