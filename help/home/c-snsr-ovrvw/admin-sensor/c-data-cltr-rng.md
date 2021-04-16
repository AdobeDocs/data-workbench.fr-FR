---
description: Vérifiez si le collecteur fonctionne selon différentes méthodes.
title: Confirmation que le collecteur de données est en cours d’exécution
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Confirmation que le collecteur de données est en cours d’exécution{#confirming-that-the-data-collector-is-running}

Vérifiez si le collecteur fonctionne selon différentes méthodes.

**Fréquence recommandée :** toutes les 5 à 10 minutes

* [Utilisez la fonctionnalité de test de site dans l&#39;émetteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Vérifiez  [!DNL Sensor] si un cookie est défini.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Utilisation du test de site {#section-a5a697c3252e40f184c0b662926170f2}

Une façon de vérifier que le collecteur est en cours d&#39;exécution consiste à activer la fonction Test du site dans l&#39;émetteur. Lorsque vous activez Test du site, l’émetteur envoie périodiquement (toutes les 60 secondes) une demande de GET au serveur Web sur lequel le collecteur est en cours d’exécution. Si Site Test n&#39;obtient pas de réponse du serveur Web, il écrit un message d&#39;erreur à syslog et envoie un message d&#39;erreur à [!DNL data workbench server] (écrit dans le fichier de log de capteur).

Si Site Test reçoit une réponse du serveur Web, il recherche dans le fichier de file d’attente un paquet du serveur Web. Si le paquet n&#39;apparaît pas (indiquant que le collecteur n&#39;était pas en cours d&#39;exécution pour capturer le événement), Site Test écrit un message d&#39;erreur sur syslog et envoie un message d&#39;erreur à l&#39;Adobe (également écrit dans le fichier de log du capteur).

Dans les requêtes envoyées par Site Test au serveur Web, Site Test définit la valeur User-Agent sur &quot;[!DNL Sensor] Test&quot;. Si vous ne souhaitez pas que ces requêtes apparaissent dans votre jeu de données, ajoutez l&#39;User-Agent &quot;[!DNL Sensor] Test&quot; au fichier [!DNL Baseline Robots List.txt] ou au fichier [!DNL Extended Robots List.txt] dans le dossier [!DNL Lookups] de [!DNL data workbench server].

**Pour activer le test du site dans l’émetteur**

1. Recherchez le fichier [!DNL txlogd.conf] sur l’ordinateur sur lequel [!DNL Sensor] est exécuté et ouvrez-le dans un éditeur de texte.

1. Dans le fichier [!DNL txlogd.conf], recherchez la ligne &quot;SiteTest&quot; et configurez-la comme indiqué ci-dessous. Si votre fichier [!DNL txlogd.conf] n&#39;inclut pas la ligne &quot;SiteTest&quot;, il vous suffit d&#39;ajouter la ligne à la fin du fichier de configuration.

   SiteTest http, *serverAddress*, *port*, *resource*

   où *serverAddress* correspond au nom ou à l’adresse IP du serveur Web, *port* est le port d’écoute HTTP du serveur et *resource* est la ressource spécifique que vous souhaitez que Site Test demande lors du test du serveur. Notez que *resource* peut inclure une chaîne de requête.

   Exemple : SiteTest http,localhost,80,/index.jsp

   Pour tester plusieurs serveurs Web, il vous suffit de spécifier plusieurs lignes SiteTest.

## Recherche d&#39;un cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Une autre manière de vérifier que le collecteur s’exécute sur un serveur Web consiste à vérifier si [!DNL Sensor] définit un cookie dans les réponses que le serveur Web renvoie aux clients. Si le collecteur fonctionne, le serveur Web renvoie un cookie &quot;v1st&quot;.

Il est possible de renommer le cookie. Si vous l’avez fait, vous devez rechercher le nom spécifié, et non v1st.

Vous pouvez effectuer cette vérification à l’aide d’un script automatisé ou d’un agent de surveillance. Pour obtenir un exemple de script ou une aide supplémentaire concernant cette tâche, veuillez contacter les Services de conseil en Adobe.
