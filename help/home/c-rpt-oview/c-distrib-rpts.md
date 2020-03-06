---
description: Une fois les rapports générés, le rapport répartit les rapports dans le jeu en fonction des paramètres de son fichier Report.cfg.
solution: Analytics
title: Distribution de rapports
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribution de rapports{#distributing-reports}

Une fois les rapports générés, le rapport répartit les rapports dans le jeu en fonction des paramètres de son fichier Report.cfg.

[!DNL Report] vous permet de distribuer les rapports dans un ensemble à l’aide des méthodes suivantes :

* **Courriel :** Pour distribuer les rapports sous forme de fichiers Excel, [!DNL .png] de fichiers ou de miniatures par courrier électronique (en ligne ou en pièce jointe), spécifiez les paramètres du rapport Courrier dans le [!DNL Report.cfg] fichier du jeu de rapports. Tous les rapports de cet ensemble sont envoyés par courrier électronique dans un message aux destinataires spécifiés.

* **Répertoire partagé :** Pour distribuer les rapports sous forme de fichiers Excel, [!DNL .png] de fichiers ou de miniatures dans un répertoire partagé, spécifiez le répertoire dans le paramètre Racine de sortie du [!DNL Report.cfg] fichier du jeu de rapports.

* **Portail des rapports :** Un portail de création de rapports vous permet d’afficher des rapports par l’intermédiaire de votre navigateur Web. Adobe [!DNL Report Portal] affiche les rapports générés sous forme d’Excel ou de [!DNL .png] fichiers, mais pas sous forme de vignettes ( [!DNL .jpg]). Pour distribuer des rapports à un portail, spécifiez la racine du document du serveur Web utilisé pour le portail dans le paramètre Racine de sortie du [!DNL Report.cfg] fichier du jeu de rapports. Pour plus d’informations sur l’installation et l’utilisation [!DNL Report Portal], voir [Utilisation du portail](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)de rapports.

>[!NOTE]
>
>Pour lire la sortie actuellement prise en charge par [!DNL Report], vous devez disposer d’une application capable d’afficher les rapports dans le ou les formats souhaités. Par exemple, pour afficher [!DNL .xlsx] des fichiers, vous devez disposer de Microsoft Excel 2007 ou version ultérieure.

Vous pouvez également combiner ces options de génération et de distribution. Par exemple, si vous définissez le [!DNL Report Types] paramètre pour générer un jeu de rapports sous la forme Excel et [!DNL .png] des fichiers, puis les paramètres [!DNL Mail Report]et [!DNL Output Root] , tous les rapports de cet ensemble sont distribués dans le répertoire de sortie spécifié (à afficher dans un portail, par exemple) et envoyés par courrier électronique aux destinataires.

Pour connaître les étapes de configuration des jeux de rapports, voir [Utilisation des jeux](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)de rapports. Pour plus d’informations sur les [!DNL Report.cfg] paramètres spécifiques, voir Paramètres [](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.
