---
description: Une fois les rapports générés, Report les répartit dans le jeu en fonction des paramètres de son fichier Report.cfg .
title: Diffusion des rapports
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Diffusion des rapports{#distributing-reports}

Une fois les rapports générés, Report les répartit dans le jeu en fonction des paramètres de son fichier Report.cfg .

[!DNL Report] permet de répartir les rapports dans un ensemble à l&#39;aide des méthodes suivantes :

* **Courriel :** pour distribuer les rapports sous forme de fichiers Excel,  [!DNL .png] de fichiers ou de miniatures par courriel (en ligne ou en pièces jointes), spécifiez les paramètres du rapport Courrier électronique dans le  [!DNL Report.cfg] fichier du jeu de rapports. Tous les rapports de cet ensemble sont envoyés par courriel aux destinataires spécifiés.

* **Répertoire partagé :** pour distribuer les rapports sous forme de fichiers Excel,  [!DNL .png] de fichiers ou de miniatures vers un répertoire partagé, spécifiez le répertoire dans le paramètre Racine de sortie du  [!DNL Report.cfg] fichier du jeu de rapports.

* **Portail de création de rapports :** un portail de création de rapports vous permet d’afficher des rapports par le biais de votre navigateur web. La balise [!DNL Report Portal] d’Adobe affiche les rapports générés sous forme de fichiers Excel ou [!DNL .png], mais pas ceux générés sous forme de miniatures ( [!DNL .jpg]). Pour distribuer des rapports à un portail, spécifiez la racine du document du serveur web utilisé pour le portail dans le paramètre Racine de sortie du fichier [!DNL Report.cfg] du jeu de rapports. Pour plus d’informations sur l’installation et l’utilisation de [!DNL Report Portal], voir [Utilisation du portail de rapports](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Pour lire la sortie actuellement prise en charge par [!DNL Report], vous devez disposer d’une application capable d’afficher les rapports au(x) format(s) souhaité(s). Par exemple, pour afficher les fichiers [!DNL .xlsx], vous devez disposer de Microsoft Excel 2007 ou version ultérieure.

Vous pouvez également utiliser une combinaison de ces options de génération et de distribution. Par exemple, si vous définissez le paramètre [!DNL Report Types] pour générer un jeu de rapports sous la forme de fichiers Excel et [!DNL .png], puis définissez les paramètres [!DNL Mail Report]et [!DNL Output Root], tous les rapports qu’il contient sont distribués dans le répertoire de sortie spécifié (qui peut être affiché dans un portail) et envoyés par courrier électronique aux destinataires dans un seul message électronique.

Pour connaître les étapes de configuration des jeux de rapports, voir [Utilisation des jeux de rapports](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Pour plus d’informations sur les paramètres [!DNL Report.cfg] spécifiques, voir [Paramètres Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
