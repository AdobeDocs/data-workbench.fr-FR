---
description: Une fois les rapports générés, Report répartit les rapports du jeu en fonction des paramètres définis dans son fichier Report.cfg.
title: Diffusion des rapports
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Diffusion des rapports{#distributing-reports}

Une fois les rapports générés, Report répartit les rapports du jeu en fonction des paramètres définis dans son fichier Report.cfg.

[!DNL Report] vous permet de distribuer les rapports dans un ensemble à l’aide des méthodes suivantes :

* **Courriel :** Pour distribuer les rapports sous la forme de fichiers Excel, de  [!DNL .png] fichiers ou de miniatures par courriel (en ligne ou en pièces jointes), spécifiez les paramètres du rapport Courrier dans le  [!DNL Report.cfg] fichier du jeu de rapports. Tous les rapports de cet ensemble sont envoyés par courriel en un seul message aux destinataires spécifiés.

* **Répertoire partagé :** pour distribuer les rapports sous la forme de fichiers Excel, de  [!DNL .png] fichiers ou de miniatures dans un répertoire partagé, spécifiez le répertoire dans le paramètre Racine de sortie dans le  [!DNL Report.cfg] fichier du jeu de rapports.

* **Portail des rapports :** un portail de rapports vous permet de vue de rapports par le biais de votre navigateur Web. Le [!DNL Report Portal] Adobe affiche les rapports générés sous forme de fichiers Excel ou [!DNL .png], mais pas ceux générés sous forme de miniatures ( [!DNL .jpg]). Pour distribuer des rapports à un portail, spécifiez la racine de document du serveur Web utilisé pour le portail dans le paramètre Racine de la sortie du fichier [!DNL Report.cfg] du jeu de rapports. Pour plus d&#39;informations sur l&#39;installation et l&#39;utilisation de [!DNL Report Portal], voir [Utilisation du portail de rapports](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Pour lire la sortie actuellement prise en charge par [!DNL Report], vous devez disposer d&#39;une application capable d&#39;afficher les rapports dans le ou les formats souhaités. Par exemple, pour vue à des fichiers [!DNL .xlsx], vous devez disposer de Microsoft Excel 2007 ou version ultérieure.

Vous pouvez également utiliser une combinaison de ces options de génération et de distribution. Par exemple, si vous définissez le paramètre [!DNL Report Types] pour générer un jeu de rapports sous la forme de fichiers Excel et [!DNL .png], puis les paramètres [!DNL Mail Report]et [!DNL Output Root], tous les rapports qu&#39;il contient sont distribués dans le répertoire de sortie spécifié (peut-être affichés dans un portail) et envoyés par courriel aux destinataires.

Pour connaître les étapes de configuration de vos jeux de rapports, voir [Utilisation des jeux de rapports](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Pour plus d&#39;informations sur les paramètres [!DNL Report.cfg] spécifiques, voir [Paramètres Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
