---
description: Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder à vos données d’outils de données et les afficher. Les privilèges d’écriture ne sont pas requis.
title: Configuration du contrôle d’accès
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# Configuration du contrôle d’accès{#configuring-access-control}

Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder à vos données d’outils de données et les afficher. Les privilèges d’écriture ne sont pas requis.

La configuration du contrôle d&#39;accès implique la modification de votre fichier [!DNL Access Control.cfg] sur les unités de gestion de données et l&#39;ajout d&#39;un nouveau groupe pour accorder des autorisations au tableau de bord de l&#39;outil de données :

1. Modifiez le fichier [!DNL AccessControl.cfg] (en utilisant de préférence la station de travail data bench).
1. Créez un nouveau groupe nommé *Accès au Tableau de bord Insight*.
1. Dans le cas des membres de ce groupe, ajoutez le CN approprié qui vous a été fourni à cette fin (Exemple : CN:INSIGHT-USER01). Contactez le service à la clientèle de l&#39;Adobe pour ce CN.
1. Dans le cadre de l’accès en lecture seule de ce groupe, modifiez la liste pour refléter les éléments suivants :

* /Profils/$
* /Profils/
* /Adresses
* /État/
* /Utilisateurs/$

1. Supprimez tous les éléments de la section d’accès en lecture-écriture, car aucune autorisation d’écriture n’est requise pour le tableau de bord.
1. Enregistrez les modifications apportées au fichier [!DNL AccessControl.cfg] sur le serveur pour que les autorisations soient prises en compte.
