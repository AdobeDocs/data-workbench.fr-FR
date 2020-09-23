---
description: Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.
solution: Analytics
title: Installation du serveur Insight maître
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---


# Installation du serveur Insight maître{#installing-the-master-insight-server}

Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.

Un composant client tel que [!DNL Insight] ou [!DNL Report] se connecte au maître [!DNL Insight Server] au début d’une session. Lors des points suivants de la session, le client peut se connecter à d’autres [!DNL Insight Servers] membres de la grappe pour effectuer une requête. Ces connexions suivantes entre le client et l’autre [!DNL Insight Servers] de la grappe sont gérées par le maître [!DNL Insight Server] et sont transparentes pour le client.

Outre le courtage des connexions entre un client et d’autres [!DNL Insight Servers] membres de la grappe, le maître [!DNL Insight Server] agit en tant que point d’administration central pour l’ensemble de la grappe. Lorsque vous administrez une grappe, vous mettez à jour le maître [!DNL Insight Server]. Les modifications administratives que vous apportez sur le maître [!DNL Insight Server] sont récupérées par l’autre [!DNL Insight Servers] dans la grappe.

**Pour installer le maître[!DNL Insight Server]**

1. Déterminez quelle machine agira comme maître [!DNL Insight Server].
1. Installez et configurez [!DNL Insight Server] (généralement, un [!DNL Insight Server] FSU) sur cet ordinateur, comme décrit dans [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installez [!DNL Insight] et configurez une connexion à l’original [!DNL Insight Server] comme décrit dans le *[!DNL Insight]Guide* de l’utilisateur.
