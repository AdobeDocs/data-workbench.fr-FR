---
description: Générez des rapports en traitant les espaces de travail et en les spécifiant comme rapports.
title: Génération des rapports
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Génération des rapports{#generating-reports}

Générez des rapports en traitant les espaces de travail et en les spécifiant comme rapports.

[!DNL Report] génère vos rapports selon l’intervalle défini dans le  [!DNL Every] paramètre du  [!DNL Report.cfg] fichier ( [!DNL "day], qui traite le rapport quotidiennement, par exemple) et en fonction des autres paramètres du  [!DNL Report.cfg] fichier.

Lors de la génération de rapports, le pourcentage de fin s’affiche dans l’onglet [!DNL Reports] sous la miniature de ce rapport particulier. Si [!DNL Report] rencontre un problème au cours de la génération du rapport, le message d’erreur le plus récent s’affiche sur l’onglet [!DNL Reports] du dossier du jeu de rapports. Si [!DNL Report] rencontre une erreur pour un rapport particulier, il continue à traiter les autres rapports de l’ensemble.

Vous pouvez générer les rapports dans un jeu de rapports dans n’importe lequel ou dans tous les formats suivants à l’aide du paramètre [!DNL Report Types] du fichier [!DNL Report.cfg] :

* Fichier Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx])
* Fichier graphique réseau portable ( [!DNL .png])
* Miniature ( [!DNL .jpg])

En plus des types de sortie spécifiés, [!DNL Report] crée un fichier [!DNL .xml] nommé de la même manière que votre rapport. Ce fichier *`<report name>`*.xml contient la description du rapport qui s’affiche en Data Workbench sous l’onglet [!DNL Reports] sous la miniature du rapport. La description peut ainsi être utilisée lors de la distribution de vos rapports par le biais d’un portail de rapports. Pour plus d’informations sur [!DNL Report Portal], voir [Utilisation du portail de rapports](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Si vous redéfinissez une mesure interne, le système se comporte de manière inattendue en raison d’une mauvaise valeur. Vos rapports ne se généreront pas, sauf si une mesure indique 100 %. Nous vous recommandons de ne pas changer les définitions de la mesure.
