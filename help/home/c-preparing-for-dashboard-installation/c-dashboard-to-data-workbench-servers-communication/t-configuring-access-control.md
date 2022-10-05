---
description: Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder à vos données Data Workbench et les afficher. Les privilèges d’écriture ne sont pas requis.
title: Configuration du contrôle d’accès du tableau de bord
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 2%

---

# Configuration du contrôle d’accès du tableau de bord{#configuring-dashboard-access-control}

{{eol}}

Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder à vos données Data Workbench et les afficher. Les privilèges d’écriture ne sont pas requis.

La configuration du contrôle d’accès implique la modification de votre [!DNL Access Control.cfg] sur le ou les FSU et en ajoutant un nouveau groupe pour accorder des autorisations au tableau de bord Data Workbench :

1. Modifiez la variable [!DNL AccessControl.cfg] de préférence en utilisant le poste de travail de Data Workbench.
1. Créez un groupe nommé *Accès au tableau de bord Insight*.
1. Sous les membres de ce groupe, ajoutez le CN approprié qui vous a été fourni à cette fin (exemple : CN:INSIGHT-USER01). Contactez l’Assistance clientèle d’Adobe pour ce CN.
1. Sous l’accès en lecture seule de ce groupe, modifiez la liste pour prendre en compte les éléments suivants :

* /Profils/$
* /Profils/
* /Addresses
* /État/
* /Utilisateurs/$

1. Supprimez tous les éléments de la section d’accès en lecture-écriture, car aucune autorisation d’écriture n’est requise pour le tableau de bord.
1. Enregistrez les modifications dans le [!DNL AccessControl.cfg] sur le serveur pour que les autorisations prennent effet.
