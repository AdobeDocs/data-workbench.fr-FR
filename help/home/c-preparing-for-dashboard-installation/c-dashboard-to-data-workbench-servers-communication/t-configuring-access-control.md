---
description: Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder aux données des outils de données et les afficher. Les privilèges d’écriture ne sont pas requis.
solution: Analytics
title: Configuration du contrôle d'accès
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration du contrôle d&#39;accès{#configuring-access-control}

Le tableau de bord nécessite certaines autorisations en lecture seule pour pouvoir accéder aux données des outils de données et les afficher. Les privilèges d’écriture ne sont pas requis.

La configuration du contrôle d’accès implique la modification de votre [!DNL Access Control.cfg] fichier sur le ou les FSU et l’ajout d’un nouveau groupe pour autoriser l’accès au tableau de bord de l’outil de données :

1. Modifiez le [!DNL AccessControl.cfg] fichier (de préférence en utilisant le poste de travail des outils de données).
1. Créez un groupe nommé *Insight Dashboard Access*.
1. Sous les membres de ce groupe, ajoutez le CN approprié qui vous a été fourni à cette fin (Exemple : CN:INSIGHT-USER01). Contactez le service à la clientèle d’Adobe pour obtenir ce document CN.
1. Sous l’accès en lecture seule de ce groupe, modifiez la liste pour qu’elle reflète les éléments suivants :

* /Profils/$
* /Profils/
* /Adresses
* /État/
* /Utilisateurs/$

1. Supprimez tous les éléments de la section d’accès en lecture-écriture, car aucune autorisation d’écriture n’est requise pour le tableau de bord.
1. Enregistrez les modifications apportées au [!DNL AccessControl.cfg] fichier sur le serveur pour que les autorisations prennent effet.
