---
description: Une fois les rapports générés, Report les répartit dans le jeu en fonction des paramètres de son fichier Report.cfg .
title: Diffusion des rapports
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Diffusion des rapports{#distributing-reports}

{{eol}}

Une fois les rapports générés, Report les répartit dans le jeu en fonction des paramètres de son fichier Report.cfg .

[!DNL Report] permet de répartir les rapports dans un ensemble à l&#39;aide des méthodes suivantes :

* **Email :** Pour distribuer des rapports sous forme de fichiers Excel, procédez comme suit : [!DNL .png] Les fichiers, ou les miniatures par courrier électronique (en ligne ou en tant que pièces jointes), spécifient les paramètres du rapport Courrier dans le rapport [!DNL Report.cfg] fichier . Tous les rapports de cet ensemble sont envoyés par courriel aux destinataires spécifiés.

* **Répertoire partagé :** Pour distribuer des rapports sous forme de fichiers Excel, procédez comme suit : [!DNL .png] Les fichiers, ou miniatures d’un répertoire partagé, spécifiez le répertoire dans le paramètre Racine de sortie du jeu de rapports. [!DNL Report.cfg] fichier .

* **Portail de création de rapports :** Un portail de création de rapports vous permet d’afficher des rapports par le biais de votre navigateur web. Adobe’s [!DNL Report Portal] affiche les rapports générés sous la forme Excel ou [!DNL .png] fichiers, mais pas ceux générés en tant que miniatures ( [!DNL .jpg]). Pour distribuer des rapports à un portail, spécifiez la racine du document du serveur web utilisé pour le portail dans le paramètre Racine de sortie du jeu de rapports. [!DNL Report.cfg] fichier . Pour plus d’informations sur l’installation et l’utilisation de [!DNL Report Portal], voir [Utilisation du portail de rapports](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Pour lire la sortie actuellement prise en charge par [!DNL Report], vous devez disposer d’une application capable d’afficher les rapports au(x) format(s) souhaité(s). Par exemple, pour afficher [!DNL .xlsx] , vous devez disposer de Microsoft Excel 2007 ou version ultérieure.

Vous pouvez également utiliser une combinaison de ces options de génération et de distribution. Par exemple, si vous définissez la variable [!DNL Report Types] pour générer un jeu de rapports au format Excel et [!DNL .png] , puis définissez la variable [!DNL Mail Report]et [!DNL Output Root] , tous les rapports de cet ensemble sont distribués dans le répertoire de sortie spécifié (peut-être à afficher dans un portail) et envoyés par courrier électronique aux destinataires dans un même message.

Pour connaître les étapes de configuration des jeux de rapports, voir [Utilisation des jeux de rapports](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Pour plus d’informations sur les [!DNL Report.cfg] paramètres, voir [Paramètres Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
