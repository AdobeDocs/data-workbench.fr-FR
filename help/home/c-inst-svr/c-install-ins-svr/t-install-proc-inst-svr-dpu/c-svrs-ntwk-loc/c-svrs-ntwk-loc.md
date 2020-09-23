---
description: Les clients d’Insight Server (Report and Insight) utilisent des noms courants pour faire référence aux serveurs Insight.
solution: Analytics
title: Définition de l’emplacement réseau du serveur
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---


# Définition de l’emplacement réseau du serveur{#defining-the-server-s-network-location}

Les clients d’Insight Server (Report and Insight) utilisent des noms courants pour faire référence aux serveurs Insight.

Par exemple, lorsque vous vous connectez [!DNL Insight] ou [!DNL Report] à un [!DNL Insight Server]serveur, vous identifiez le serveur par son nom commun (par exemple, [!DNL Server.MyCompany.com]). En interne, le client résout le nom commun en adresse IP numérique avant d’envoyer une requête au serveur.

Pour résoudre les noms courants en adresses IP, [!DNL Insight Server’s] les clients utilisent un fichier de recherche local appelé fichier d’adresse. Le fichier d’adresses liste les noms courants des [!DNL Insight Servers] ordinateurs installés dans votre organisation et identifie leurs adresses IP numériques. Un client reçoit automatiquement une copie du fichier d&#39;adresse lorsqu&#39;il ouvre un profil sur le [!DNL Insight Server]serveur.

Lorsqu’un client envoie une requête à un [!DNL Insight Server]utilisateur, il tente de résoudre le nom commun du serveur par le biais du fichier d’adresse. Si le fichier d’adresse identifie une adresse IP pour le serveur demandé, le client achemine la demande vers l’adresse spécifiée. Si l’adresse n’est pas définie (par exemple, le fichier d’adresse ne définit pas le nom commun du serveur), la requête échoue. Vous pouvez éventuellement configurer les clients pour qu’ils résolvent les adresses au moyen du mécanisme DNS (Domain Naming Service) normal de l’environnement d’exploitation si un nom n’est pas défini dans le fichier d’adresse du client. Pour obtenir des instructions, voir le paramètre Parent dans le tableau [Paramètres](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) NetworkLocation dans la section suivante.
