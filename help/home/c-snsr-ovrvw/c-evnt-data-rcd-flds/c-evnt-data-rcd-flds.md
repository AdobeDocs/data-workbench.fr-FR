---
description: Les fichiers journaux (.vsl) contiennent les champs de données d’événement collectés à partir des serveurs par Capteurs et utilisés par le serveur Data Workbench dans le processus de construction du jeu de données.
title: Champs d’enregistrement des données d’événement
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 5%

---

# Champs d’enregistrement des données d’événement{#event-data-record-fields}

Les fichiers journaux (.vsl) contiennent les champs de données d’événement collectés à partir des serveurs par Capteurs et utilisés par le serveur Data Workbench dans le processus de construction du jeu de données.

Les noms des champs respectent généralement la convention de dénomination du format de fichier journal étendu W3C. La plupart des champs comportent des préfixes qui indiquent la source des informations contenues dans le champ :

* &quot;cs&quot; indique la communication du client au serveur
* &quot;sc&quot; indique la communication du serveur au client
* &quot;s&quot; indique des informations provenant du serveur
* &quot;c&quot; indique des informations provenant du client
* &quot;x&quot; indique les informations créées par un produit Adobe
