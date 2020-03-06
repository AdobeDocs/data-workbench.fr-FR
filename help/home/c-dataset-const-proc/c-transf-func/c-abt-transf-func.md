---
description: La fonctionnalité de transformation (Transform) s’exécute sur un ordinateur serveur de l’outil de données afin de permettre l’exportation des données source du journal en vue de les utiliser par d’autres applications.
solution: Analytics
title: A propos de la fonctionnalité de transformation
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# A propos de la fonctionnalité de transformation{#about-transformation-functionality}

La fonctionnalité de transformation (Transform) s’exécute sur un ordinateur serveur de l’outil de données afin de permettre l’exportation des données source du journal en vue de les utiliser par d’autres applications.

[!DNL Transform] peuvent lire [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC et exporter les données sous forme de [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités pouvant être utilisés par les routines de chargement de DataWarehouse, les agences de contrôle ou d’autres cibles. L’extraction et la transformation des données peuvent être effectuées sur une base continue ou planifiée.

>[!NOTE]
>
>En règle générale, [!DNL Transform] est configuré sur un FSU de serveur d’outils de données. Toutefois, votre mise en oeuvre peut nécessiter une configuration sur un DPU de serveur de l’outil de données. Pour plus d’informations, contactez Adobe.

Vous pouvez afficher les informations d’utilisation de la mémoire pour [!DNL Transform] dans l’interface d’état détaillé. Pour plus d’informations, voir le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données.

La fonction d’exportation de segments offre un autre moyen d’exporter des données d’une application Adobe. [!DNL Transform] vous permet d’exporter des données non traitées vers une cible externe, mais la fonction d’exportation de segments vous permet de générer des données traitées à partir du jeu de données et exige que les données exportées soient définies comme une dimension dans le jeu de données. Pour plus d’informations sur l’exportation de segments, consultez le Guide *de l’utilisateur des outils de* données.
