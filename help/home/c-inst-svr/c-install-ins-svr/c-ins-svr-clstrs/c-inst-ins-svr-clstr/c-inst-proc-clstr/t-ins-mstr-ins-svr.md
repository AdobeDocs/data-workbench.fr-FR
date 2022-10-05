---
description: Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.
title: Installation du serveur Insight maître
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installation du serveur Insight maître{#installing-the-master-insight-server}

{{eol}}

Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.

Un composant client, tel que [!DNL Insight] ou [!DNL Report] se connecte au maître [!DNL Insight Server] au début d’une session. Lors des moments suivants de la session, le client peut se connecter à d’autres [!DNL Insight Servers] dans la grappe pour effectuer une requête. Ces connexions suivantes entre le client et l’autre [!DNL Insight Servers] dans la grappe, sont gérés par le maître [!DNL Insight Server] et sont transparents pour le client.

Outre le courtage de connexions entre un client et d’autres [!DNL Insight Servers] dans la grappe, le maître [!DNL Insight Server] agit comme point d’administration central de l’ensemble de la grappe. Lorsque vous administrez une grappe, vous mettez à jour le maître [!DNL Insight Server]. Modifications administratives que vous effectuez sur le gabarit [!DNL Insight Server] sont récupérés par l’autre [!DNL Insight Servers] dans la grappe.

**Pour installer le maître[!DNL Insight Server]**

1. Déterminer quelle machine agira comme maître [!DNL Insight Server].
1. Installation et configuration [!DNL Insight Server] (généralement, une [!DNL Insight Server] FSU) sur cette machine, comme décrit dans la section [Serveur Insight](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installer [!DNL Insight] et configurer une connexion au maître [!DNL Insight Server] comme décrit dans la section *[!DNL Insight]Guide de l’utilisateur*.
