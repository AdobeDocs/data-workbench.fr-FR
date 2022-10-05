---
description: Étapes de modification des comptes d’utilisateurs existants.
title: Modification d’utilisateurs existants
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# Modification d’utilisateurs existants{#editing-existing-users}

{{eol}}

Étapes de modification des comptes d’utilisateurs existants.

1. Dans le [!DNL Report Portal], cliquez sur le bouton **[!UICONTROL Admin]** . Le [!DNL Admin] s’affiche.

   ![](assets/report_admintag2.png)

1. Cliquez sur la lettre représentant la première lettre du nom du compte que vous souhaitez modifier. Par exemple, si vous souhaitez modifier le compte &quot;Marketing&quot;, cliquez sur la lettre &quot;M&quot;.

   Une liste des noms de compte commençant par cette lettre s’affiche.

1. Sélectionnez le nom du compte à modifier, puis cliquez sur le bouton **[!UICONTROL select]** bouton . Le [!DNL Edit Account Info] s’affiche.

   ![Infos sur l’étape](assets/rptPort_scrn_AdminTab_editUser.png)

1. Modifiez uniquement les champs de cette page qui doivent être mis à jour. Le tableau suivant décrit chacun de ces champs :

   | Dans ce champ . . . | Spécifiez les . . . |
   |---|---|
   | email | Adresse électronique de l’utilisateur. |
   | ancien mot de passe | mot de passe actuel, qui doit être utilisé lors de la modification d’un compte administrateur ou de la réinitialisation du mot de passe d’un compte non administrateur. |
   | nouveau mot de passe | le nouveau mot de passe que l’utilisateur doit fournir lors de la connexion à [!DNL Report Portal]. |
   | confirmer le mot de passe | le nouveau mot de passe que l’utilisateur doit fournir lors de la connexion à [!DNL Report Portal]. |
   | accès au profil | Profils auxquels cet utilisateur est autorisé à accéder (par exemple, ProductSales). Pour autoriser l’accès à plusieurs profils, séparez les noms par des virgules. Si l’utilisateur est autorisé à accéder à tous les profils associés à [!DNL Report Portal], saisissez &quot;ALL&quot;. |
   | accès aux onglets | Les onglets auxquels cet utilisateur est autorisé à accéder (par exemple, [!DNL Admin]). Pour autoriser l’accès à plusieurs onglets, séparez les noms par des virgules. Si l’utilisateur est autorisé à accéder à tous les onglets de la variable [!DNL Report Portal], saisissez &quot;ALL&quot;. Ce champ, combiné avec le champ type de compte, est très utile pour définir les droits d&#39;accès des groupes. |
   | type de compte | Si ce compte est destiné à un individu ou à un groupe. Les comptes individuels permettent aux utilisateurs de réinitialiser leurs mots de passe, contrairement aux groupes. Un administrateur est la seule personne capable de réinitialiser le mot de passe d’un compte de groupe. |
   | statut | Si ce compte est principal ou inactif. La valeur par défaut est principale. Pour désactiver un compte utilisateur, sélectionnez **[!UICONTROL inactive]**. |
   | admin | Permet à l’utilisateur de créer, mettre à jour et supprimer des comptes d’utilisateurs, ainsi que de modifier les notes associées à chaque rapport. Le paramètre par défaut est false. Pour en faire un utilisateur administrateur, sélectionnez true. |
   | date d&#39;expiration | Date, au format MM/JJ/AAAA, jusqu’à laquelle cet utilisateur est autorisé à utiliser [!DNL Report Portal]. |

1. Cliquez sur **[!UICONTROL update]**.
