---
description: Générez des rapports en traitant les espaces de travail et en les spécifiant comme rapports.
title: Génération des rapports
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Génération des rapports{#generating-reports}

{{eol}}

Générez des rapports en traitant les espaces de travail et en les spécifiant comme rapports.

[!DNL Report] génère vos rapports selon l’intervalle défini dans la variable [!DNL Every] du paramètre [!DNL Report.cfg] (par exemple, [!DNL "day], qui traite le rapport quotidiennement) et en fonction des autres [!DNL Report.cfg] paramètres du fichier.

Lors de la génération de rapports, le pourcentage de fin s’affiche sur la page [!DNL Reports] sous la miniature de ce rapport spécifique. If [!DNL Report] rencontre un problème lors de la génération du rapport, le message d’erreur le plus récent s’affiche sur la page [!DNL Reports] dans le dossier du jeu de rapports. If [!DNL Report] s’il rencontre une erreur pour un rapport particulier, il continue à traiter les autres rapports de l’ensemble.

Vous pouvez générer les rapports dans un jeu de rapports dans n’importe quel ou tous les formats suivants à l’aide du [!DNL Report Types] du paramètre [!DNL Report.cfg] fichier :

* Fichier Excel Microsoft ( [!DNL .xls] ou [!DNL .xlsx])
* Fichier graphique réseau portable ( [!DNL .png])
* Miniature ( [!DNL .jpg])

Avec les types de sorties spécifiés, [!DNL Report] crée une [!DNL .xml] nommé de la même manière que votre rapport. Ceci *`<report name>`* Le fichier .xml contient la description du rapport qui s’affiche en Data Workbench sur le [!DNL Reports] sous la miniature du rapport. La description peut ainsi être utilisée lors de la distribution de vos rapports par le biais d’un portail de rapports. Pour plus d’informations sur la variable [!DNL Report Portal], voir [Utilisation du portail de rapports](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Si vous redéfinissez une mesure interne, le système se comporte de manière inattendue en raison d’une mauvaise valeur. Vos rapports ne se généreront pas, sauf si une mesure indique 100 %. Nous vous recommandons de ne pas changer les définitions de la mesure.
