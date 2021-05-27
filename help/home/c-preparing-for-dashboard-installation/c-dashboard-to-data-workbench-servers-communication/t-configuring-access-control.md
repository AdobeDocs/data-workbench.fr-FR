---
description: Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder à vos données Data Workbench et les afficher. Les privilèges d’écriture ne sont pas requis.
title: Configuration du contrôle d’accès
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# Configuration du contrôle d’accès{#configuring-access-control}

Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder à vos données Data Workbench et les afficher. Les privilèges d’écriture ne sont pas requis.

La configuration du contrôle d’accès implique de modifier votre fichier [!DNL Access Control.cfg] sur le ou les FSU et d’ajouter un nouveau groupe pour accorder des autorisations au tableau de bord Data Workbench :

1. Modifiez le fichier [!DNL AccessControl.cfg] (de préférence à l’aide du poste de travail Data Workbench).
1. Créez un groupe nommé *Accès au tableau de bord Insight*.
1. Sous les membres de ce groupe, ajoutez le CN approprié qui vous a été fourni à cette fin (exemple : CN:INSIGHT-USER01). Contactez l’Assistance clientèle d’Adobe pour ce CN.
1. Sous l’accès en lecture seule de ce groupe, modifiez la liste pour prendre en compte les éléments suivants :

* /Profils/$
* /Profils/
* /Addresses
* /État/
* /Utilisateurs/$

1. Supprimez tous les éléments de la section d’accès en lecture-écriture, car aucune autorisation d’écriture n’est requise pour le tableau de bord.
1. Enregistrez les modifications apportées au fichier [!DNL AccessControl.cfg] sur le serveur pour que les autorisations soient prises en compte.
