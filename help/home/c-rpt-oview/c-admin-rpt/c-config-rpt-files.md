---
description: Dans le portail des rapports, vous pouvez afficher les rapports générés par le serveur de rapports sous la forme de fichiers Excel (.xls ou .xlsx) ou .png.
solution: Analytics
title: Configuration des fichiers Report.cfg
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration des fichiers Report.cfg{#configuring-report-cfg-files}

Dans le portail des rapports, vous pouvez afficher les rapports générés par le serveur de rapports sous la forme de fichiers Excel (.xls ou .xlsx) ou .png.

Pour afficher un jeu de rapports dans le [!DNL Report Portal], vous devez définir les paramètres suivants dans le [!DNL Report.cfg] fichier pour ce jeu de rapports :

* Dans le **[!UICONTROL Output Root]** paramètre, spécifiez la racine du document du serveur Web utilisé pour votre portail.
* Dans le **[!UICONTROL Report Types]** paramètre, spécifiez Excel, png et/ou la miniature comme types de rapport à générer.

Lorsque vous [!DNL Report Server] générez les rapports dans les formats que vous avez spécifiés, il place ces fichiers dans la racine du document du serveur Web, où vous configurez, au cours de l’installation, les fichiers [!DNL Report Portal] pour y accéder.

Pour plus d’informations sur les [!DNL Report.cfg] paramètres spécifiques, voir Paramètres [](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.
