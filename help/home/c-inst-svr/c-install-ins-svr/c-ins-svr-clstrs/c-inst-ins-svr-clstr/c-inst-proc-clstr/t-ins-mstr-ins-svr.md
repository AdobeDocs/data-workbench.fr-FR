---
description: Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.
title: Installation du serveur Insight maître
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installation du serveur Insight maître{#installing-the-master-insight-server}

Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.

Un composant client tel que [!DNL Insight] ou [!DNL Report] se connecte au composant principal [!DNL Insight Server] au début d&#39;une session. Lors des points suivants de la session, le client peut se connecter à d&#39;autres [!DNL Insight Servers] de la grappe pour exécuter une requête. Ces connexions suivantes entre le client et l’autre [!DNL Insight Servers] de la grappe sont gérées par le maître [!DNL Insight Server] et sont transparentes pour le client.

Outre le courtage des connexions entre un client et d&#39;autres [!DNL Insight Servers] dans la grappe, le maître [!DNL Insight Server] agit en tant que point d&#39;administration central pour l&#39;ensemble de la grappe. Lorsque vous administrez un cluster, vous mettez à jour le maître [!DNL Insight Server]. Les modifications administratives que vous apportez sur l&#39;élément maître [!DNL Insight Server] sont récupérées par l&#39;autre élément [!DNL Insight Servers] de la grappe.

**Pour installer le maître[!DNL Insight Server]**

1. Déterminez quelle machine agira en tant que maître [!DNL Insight Server].
1. Installez et configurez [!DNL Insight Server] (généralement, un FSU [!DNL Insight Server]) sur cet ordinateur, comme décrit dans [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installez [!DNL Insight] et configurez une connexion à l&#39;élément maître [!DNL Insight Server] comme décrit dans le *[!DNL Insight]Guide de l&#39;utilisateur*.
