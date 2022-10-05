---
description: La fonctionnalité de transformation (Transform) s’exécute sur un serveur Data Workbench pour permettre l’exportation des données de source de journal en vue de leur utilisation par d’autres applications.
title: À propos de la fonctionnalité de transformation
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# À propos de la fonctionnalité de transformation{#about-transformation-functionality}

{{eol}}

La fonctionnalité de transformation (Transform) s’exécute sur un serveur Data Workbench pour permettre l’exportation des données de source de journal en vue de leur utilisation par d’autres applications.

[!DNL Transform] peut lire [!DNL .vsl] fichiers, fichiers journaux, fichiers XML et données ODBC et exporter les données sous la forme [!DNL .vsl] fichiers, fichiers texte ou fichiers texte délimités pouvant être utilisés par des routines de chargement de DataWarehouse, des agences de contrôle ou d’autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées sur une base continue ou planifiée.

>[!NOTE]
>
>En règle générale, [!DNL Transform] est configuré sur un FSU de serveur Data Workbench. Cependant, votre mise en oeuvre peut nécessiter une configuration sur un DPU de serveur Data Workbench. Pour plus d’informations, contactez l’Adobe.

Vous pouvez afficher les informations d’utilisation de la mémoire pour [!DNL Transform] dans l’interface d’état détaillé. Pour plus d’informations, reportez-vous au chapitre Interfaces d’administration de la section *Guide de l’utilisateur de Data Workbench*.

La fonction d’exportation de segments offre un autre moyen d’exporter des données à partir d’une application Adobe. [!DNL Transform] vous permet d’exporter des données non traitées vers une cible externe, mais la fonction d’exportation de segments vous permet de générer des données traitées du jeu de données et exige que les données exportées soient définies comme une dimension dans le jeu de données. Pour plus d’informations sur l’exportation de segments, voir *Guide de l’utilisateur de Data Workbench*.
