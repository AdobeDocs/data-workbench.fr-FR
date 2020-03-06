---
description: Générez des rapports en traitant les espaces de travail et en les spécifiant comme des rapports.
solution: Analytics
title: Création de rapports
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création de rapports{#generating-reports}

Générez des rapports en traitant les espaces de travail et en les spécifiant comme des rapports.

[!DNL Report] génère vos rapports à l’intervalle défini dans le [!DNL Every] paramètre du [!DNL Report.cfg] fichier (par exemple [!DNL "day]&quot;, qui traite le rapport quotidiennement) et en fonction des autres paramètres de [!DNL Report.cfg] fichier.

Lors de la génération de rapports, le pourcentage de fin s’affiche dans l’ [!DNL Reports] onglet sous la miniature du rapport en question. Si [!DNL Report] un problème survient au cours de la génération du rapport, le message d’erreur le plus récent s’affiche dans l’ [!DNL Reports] onglet du dossier du jeu de rapports. Si [!DNL Report] une erreur se produit pour un rapport particulier, il continue à traiter les autres rapports du jeu.

Vous pouvez générer les rapports dans un jeu de rapports dans n’importe quel ou tous les formats suivants à l’aide du [!DNL Report Types] paramètre du [!DNL Report.cfg] fichier :

* Fichier Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx])
* Fichier graphique réseau portable ( [!DNL .png])
* Miniature ( [!DNL .jpg])

Outre les types de sortie spécifiés, [!DNL Report] crée un [!DNL .xml] fichier nommé de la même manière que votre rapport. Ce fichier *`<report name>`*.xml contient la description du rapport qui s’affiche dans les Outils de données sur l’ [!DNL Reports] onglet situé sous la miniature du rapport. La description peut ainsi être utilisée lors de la distribution de vos rapports via un portail de création de rapports. Pour plus d’informations sur le portail [!DNL Report Portal], voir [Utilisation du portail](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)de rapports.

>[!NOTE]
>
>Si vous redéfinissez une mesure interne, le système se comporte de manière inattendue en raison d’une valeur incorrecte. Vos rapports ne seront pas générés à moins qu’une mesure ne lise 100 %. Il est recommandé de ne pas modifier les définitions de mesure.
