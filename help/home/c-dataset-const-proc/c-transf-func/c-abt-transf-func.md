---
description: La fonctionnalité de transformation (Transform) s’exécute sur un serveur Data Workbench pour permettre l’exportation des données de source de journal en vue de leur utilisation par d’autres applications.
title: À propos de la fonctionnalité de transformation
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# À propos de la fonctionnalité de transformation{#about-transformation-functionality}

La fonctionnalité de transformation (Transform) s’exécute sur un serveur Data Workbench pour permettre l’exportation des données de source de journal en vue de leur utilisation par d’autres applications.

[!DNL Transform] peut lire  [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de  [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités pouvant être utilisés par des routines de chargement de DataWarehouse, des agences de contrôle ou d’autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées sur une base continue ou planifiée.

>[!NOTE]
>
>En règle générale, [!DNL Transform] est configuré sur un FSU de serveur Data Workbench. Cependant, votre mise en oeuvre peut nécessiter une configuration sur un DPU de serveur Data Workbench. Pour plus d’informations, contactez Adobe.

Vous pouvez afficher les informations d’utilisation de la mémoire pour [!DNL Transform] dans l’interface de statut détaillé. Pour plus d’informations, reportez-vous au chapitre Interfaces d’administration du *Guide de l’utilisateur du Data Workbench*.

La fonction d’exportation de segments offre un autre moyen d’exporter des données à partir d’une application Adobe. [!DNL Transform] vous permet d’exporter des données non traitées vers une cible externe, mais la fonction d’exportation de segments vous permet de générer des données traitées du jeu de données et exige que les données exportées soient définies comme une dimension dans le jeu de données. Pour plus d’informations sur l’exportation de segments, consultez le *Guide de l’utilisateur du Data Workbench*.
