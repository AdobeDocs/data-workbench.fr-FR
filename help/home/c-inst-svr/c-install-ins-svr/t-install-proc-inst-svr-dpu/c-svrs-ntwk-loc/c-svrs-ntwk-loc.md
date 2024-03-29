---
description: Les clients d’Insight Server (Report and Insight) utilisent des noms courants pour faire référence aux serveurs Insight.
title: Définition de l’emplacement réseau du serveur
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# Définition de l’emplacement réseau du serveur{#defining-the-server-s-network-location}

{{eol}}

Les clients d’Insight Server (Report and Insight) utilisent des noms courants pour faire référence aux serveurs Insight.

Par exemple, lorsque vous vous connectez [!DNL Insight] ou [!DNL Report] à [!DNL Insight Server], vous identifiez le serveur par son nom commun (par exemple, [!DNL Server.MyCompany.com]). En interne, le client résout le nom commun en adresse IP numérique avant d’envoyer une requête au serveur.

Pour convertir des noms communs en adresses IP, procédez comme suit : [!DNL Insight Server’s] les clients utilisent un fichier de recherche local appelé fichier d’adresse. Le fichier d’adresse répertorie les noms communs des [!DNL Insight Servers] installés dans votre entreprise et identifie leurs adresses IP numériques. Un client reçoit automatiquement une copie du fichier d’adresse lorsqu’il ouvre un profil sur la [!DNL Insight Server].

Lorsqu’un client émet une requête à une [!DNL Insight Server], il tente de résoudre le nom commun du serveur par le biais du fichier d’adresse. Si le fichier d’adresse identifie une adresse IP pour le serveur demandé, le client achemine la demande vers l’adresse spécifiée. Si l’adresse n’est pas définie (par exemple, le fichier d’adresse ne définit pas le nom commun du serveur), la demande échoue. Vous pouvez éventuellement configurer les clients pour qu’ils résolvent les adresses via le mécanisme DNS (Domain Naming Service) normal de l’environnement d’exploitation si un nom n’est pas défini dans le fichier d’adresse du client. Pour obtenir des instructions, voir le paramètre Parent dans la section [Tableau Paramètres NetworkLocation](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) dans la section suivante.
