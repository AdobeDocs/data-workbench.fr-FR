---
description: Après avoir déployé votre expérience, vous devez vérifier que l’expérience fonctionne correctement.
solution: Analytics,Analytics
title: Validation de l’expérience
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Validation de l’expérience{#validating-the-experiment}

Après avoir déployé votre expérience, vous devez vérifier que l’expérience fonctionne correctement.

Comme expliqué dans la section [Modification du paramètre ExpCookieURL (facultatif)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), la page spécifiée dans le paramètre ExpCookieURL du fichier de configuration [!DNL Sensor] peut être utilisée pour vous placer dans un groupe d’expériences spécifique.

La page virtuelle par défaut est [!DNL /setcookie.htm], mais vous devez utiliser la valeur que vous définissez dans le paramètre ExpCookieURL .

## Requête de la page de test {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Pour tester un groupe d’expériences spécifique pour votre site web, votre navigateur doit être configuré pour accepter les cookies et vous ne devez pas encore avoir de cookie pour ce site web.

Chaque fois que vous souhaitez tester un nouveau groupe, veillez à effacer vos cookies pour le site web.

Pour vous placer dans un groupe spécifique au cours d’une expérience spécifique, demandez la page de test avec une chaîne de requête sous la forme suivante :

[!DNL https://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Par exemple :

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

Lorsque la demande d’URL virtuelle est envoyée au serveur, [!DNL Sensor] vous identifie en tant que membre du groupe spécifié dans l’expérience spécifiée, puis vous redirige vers la racine du site web. Vous pouvez maintenant accéder à l’emplacement approprié sur le site web pour vérifier si le contenu correct s’affiche pour cette expérience et ce groupe.

Si vous deviez taper ce qui suit dans votre navigateur, celui-ci afficherait la page d’accueil du site web et vous placerait dans le groupe index2 dans l’expérience New_Homepage :

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

Lorsque les visiteurs du groupe index2 demandent la page d’accueil, le lien graphique &quot;Demander une démonstration&quot; s’affiche plus haut sur la page, comme dans le graphique suivant :

![](assets/TestPage.png)
