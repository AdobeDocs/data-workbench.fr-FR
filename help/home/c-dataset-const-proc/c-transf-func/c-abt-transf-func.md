---
description: La fonctionnalité de transformation (Transform) s’exécute sur un ordinateur serveur de l’outil de données afin de permettre l’exportation des données source du journal en vue de les utiliser par d’autres applications.
title: À propos de la fonctionnalité de transformation
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# À propos de la fonctionnalité de transformation{#about-transformation-functionality}

La fonctionnalité de transformation (Transform) s’exécute sur un ordinateur serveur de l’outil de données afin de permettre l’exportation des données source du journal en vue de les utiliser par d’autres applications.

[!DNL Transform] peuvent lire  [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de  [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités qui peuvent être utilisés par des routines de chargement de DataWarehouse, des agences de contrôle ou d&#39;autres cibles. L&#39;extraction et la transformation des données peuvent être effectuées en continu ou selon d&#39;autres méthodes planifiées.

>[!NOTE]
>
>En règle générale, [!DNL Transform] est configuré sur un FSU serveur de l’outil de données. Toutefois, votre mise en oeuvre peut nécessiter une configuration sur un DPU de serveur de l’outil de données. Pour plus d&#39;informations, contactez l&#39;Adobe.

Vous pouvez vue des informations sur l&#39;utilisation de la mémoire pour [!DNL Transform] dans l&#39;interface Statut détaillé. Pour plus d&#39;informations, consultez le chapitre Interfaces d&#39;administration du *Guide de l&#39;utilisateur Data Workbench*.

La fonction d’exportation de segments offre un autre moyen d’exporter des données à partir d’une application d’Adobe. [!DNL Transform] vous permet d’exporter des données non traitées vers une cible externe, mais la fonction d’exportation de segments vous permet de générer des données traitées à partir du jeu de données et exige que les données exportées soient définies comme une dimension dans le jeu de données. Pour plus d&#39;informations sur l&#39;exportation de segments, consultez le *Guide de l&#39;utilisateur Data Workbench*.
