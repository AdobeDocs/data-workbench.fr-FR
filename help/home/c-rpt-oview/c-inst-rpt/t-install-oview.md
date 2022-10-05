---
description: Procédure d’installation et de configuration du logiciel Report Server.
title: Aperçu de l’installation
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 8%

---

# Aperçu de l’installation{#installation-overview}

{{eol}}

Procédure d’installation et de configuration du logiciel Report Server.

Les tâches suivantes doivent être effectuées dans l’ordre :

1. Installez les fichiers de programme du serveur de rapports.
1. Téléchargez et installez le certificat numérique du serveur de rapports. Voir [Téléchargement et installation du certificat numérique](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
1. Configurez la connexion entre le serveur de rapports et le serveur Data Workbench (InsightServer64.exe). Voir [Configuration de la connexion à Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c).
1. Mettre à jour le serveur de rapports avec un fichier de langue (fichier .zbin).

   Voir [Mettre à jour le serveur de rapports avec un fichier de langue (fichier .zbin)](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b). 1. Mettez à jour le fichier de contrôle d’accès sur l’ordinateur du serveur Data Workbench pour permettre au serveur Report Server d’accéder au serveur Data Workbench. Voir [Activation de l’accès à Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc).
1. Modifiez le fichier de communication sur l’ordinateur du serveur Data Workbench maître pour afficher l’état du serveur Report Server dans la variable [!DNL Master Server Detailed Status] . Voir [Configuration du serveur Insight pour afficher l’état du serveur pour le rapport](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8).
1. Enregistrez le rapport en tant que service Windows. Voir [Enregistrement du rapport en tant que service Windows](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6).
