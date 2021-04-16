---
description: Après avoir déployé l’expérience, vous devez vérifier que l’expérience fonctionne correctement.
solution: Analytics,Analytics
title: Validation de l’expérience
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Validation de l’expérience{#validating-the-experiment}

Après avoir déployé l’expérience, vous devez vérifier que l’expérience fonctionne correctement.

Comme expliqué dans [Modification du paramètre ExpCookieURL (facultatif)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), la page spécifiée dans le paramètre ExpCookieURL dans le fichier de configuration [!DNL Sensor] peut être utilisée pour vous placer dans un groupe d&#39;expériences spécifique.

La page virtuelle par défaut est [!DNL /setcookie.htm], mais vous devez utiliser la valeur que vous définissez dans le paramètre ExpCookieURL.

## Demande de la page de test {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Pour tester un groupe d’expériences spécifique pour votre site Web, votre navigateur doit être configuré pour accepter les cookies et vous ne devez pas avoir déjà de cookie pour ce site Web.

Chaque fois que vous souhaitez tester un nouveau groupe, veillez à effacer vos cookies pour le site Web.

Pour vous placer dans un groupe spécifique au sein d’une expérience spécifique, demandez la page de test avec une chaîne de requête sous la forme suivante :

[!DNL http://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Par exemple :

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Lorsque la demande d&#39;URL virtuelle est envoyée au serveur, [!DNL Sensor] vous identifie en tant que membre du groupe spécifié dans l&#39;expérience spécifiée, puis vous redirige vers la racine du site Web. Vous pouvez désormais accéder à l’emplacement approprié du site Web pour vérifier si le contenu approprié s’affiche pour cette expérience et ce groupe.

Si vous deviez entrer les informations suivantes dans votre navigateur, celui-ci afficherait la page d&#39;accueil du site Web et vous placerait dans le groupe index2 dans l&#39;expérience New_Homepage :

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Lorsque des visiteurs du groupe index2 demandent la page d&#39;accueil, le lien graphique &quot;Demander une démo&quot; s’affiche plus haut sur la page, comme dans le graphique suivant :

![](assets/TestPage.png)
