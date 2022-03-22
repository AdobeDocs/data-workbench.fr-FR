---
description: Les fichiers journaux (.vsl) contiennent les champs de données d’événement collectés à partir des serveurs par Capteurs et utilisés par le serveur Data Workbench dans le processus de construction du jeu de données.
title: Champs d’enregistrement des données d’événement (fichiers .vsl)
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 2%

---

# Champs d’enregistrement des données d’événement{#event-data-record-fields}

Les fichiers journaux (.vsl) contiennent les champs de données d’événement collectés à partir des serveurs par Capteurs et utilisés par le serveur Data Workbench dans le processus de construction du jeu de données.

Les noms des champs respectent généralement la convention de dénomination du format de fichier journal étendu W3C. La plupart des champs comportent des préfixes qui indiquent la source des informations contenues dans le champ :

* &quot;cs&quot; indique la communication du client au serveur
* &quot;sc&quot; indique la communication du serveur au client
* &quot;s&quot; indique des informations provenant du serveur
* &quot;c&quot; indique des informations provenant du client
* &quot;x&quot; indique les informations créées par un produit Adobe
