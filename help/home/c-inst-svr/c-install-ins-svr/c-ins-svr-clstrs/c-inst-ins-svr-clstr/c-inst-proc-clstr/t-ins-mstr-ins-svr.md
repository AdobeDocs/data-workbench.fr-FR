---
description: Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.
title: Installation du serveur Insight maître
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installation du serveur Insight maître{#installing-the-master-insight-server}

Pour utiliser une grappe, vous devez désigner un serveur Insight dans la grappe pour agir en tant que serveur Insight maître.

Un composant client tel que [!DNL Insight] ou [!DNL Report] se connecte au [!DNL Insight Server] maître au début d’une session. Au cours de la session suivante, le client peut se connecter à d’autres [!DNL Insight Servers] de la grappe pour effectuer une requête. Ces connexions suivantes entre le client et l’autre [!DNL Insight Servers] de la grappe sont gérées par le [!DNL Insight Server] maître et sont transparentes pour le client.

Outre le courtage des connexions entre un client et d’autres [!DNL Insight Servers] de la grappe, le [!DNL Insight Server] maître sert de point d’administration central pour l’ensemble de la grappe. Lorsque vous administrez une grappe, vous mettez à jour le [!DNL Insight Server] maître. Les modifications administratives que vous effectuez sur le [!DNL Insight Server] maître sont récupérées par l’autre [!DNL Insight Servers] de la grappe.

**Pour installer le maître[!DNL Insight Server]**

1. Déterminez quelle machine agira comme [!DNL Insight Server] maître.
1. Installez et configurez [!DNL Insight Server] (généralement, un FSU [!DNL Insight Server]) sur cet ordinateur, comme décrit dans la section [Serveur Insight](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installez [!DNL Insight] et configurez une connexion au [!DNL Insight Server] maître comme décrit dans le *[!DNL Insight]Guide de l’utilisateur*.
