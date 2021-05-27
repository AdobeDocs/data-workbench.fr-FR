---
description: Dans le portail de rapports, vous pouvez afficher les rapports générés par le serveur de rapports sous la forme de fichiers Excel (.xls ou .xlsx) ou .png .
title: Configuration des fichiers Report.cfg
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Configuration des fichiers Report.cfg{#configuring-report-cfg-files}

Dans le portail de rapports, vous pouvez afficher les rapports générés par le serveur de rapports sous la forme de fichiers Excel (.xls ou .xlsx) ou .png .

Pour afficher un jeu de rapports dans la balise [!DNL Report Portal], vous devez définir les paramètres suivants dans le fichier [!DNL Report.cfg] de ce jeu de rapports :

* Dans le paramètre **[!UICONTROL Output Root]** , spécifiez la racine du document du serveur web utilisé pour votre portail.
* Dans le paramètre **[!UICONTROL Report Types]** , spécifiez Excel, png et/ou miniature comme types de rapports à générer.

Lorsque [!DNL Report Server] génère les rapports dans les formats que vous avez spécifiés, il place ces fichiers dans la racine du document du serveur web, où vous configurez, au cours de l’installation, [!DNL Report Portal] pour accéder aux rapports.

Pour plus d’informations sur les paramètres [!DNL Report.cfg] spécifiques, voir [Paramètres Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
