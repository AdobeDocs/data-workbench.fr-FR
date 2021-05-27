---
description: Vérifiez si le collecteur s’exécute à l’aide de méthodes différentes.
title: Confirmation que le collecteur de données est en cours d’exécution
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Confirmation que le collecteur de données est en cours d’exécution{#confirming-that-the-data-collector-is-running}

Vérifiez si le collecteur s’exécute à l’aide de méthodes différentes.

**Fréquence recommandée :** Toutes les 5-10 minutes

* [Utilisez la fonctionnalité de test de site de l’émetteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Vérifiez si [!DNL Sensor] définit un cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Utilisation du test du site {#section-a5a697c3252e40f184c0b662926170f2}

Une méthode pour vérifier que le collecteur est en cours d’exécution consiste à activer la fonction Test du site dans l’émetteur. Lorsque vous activez Test du site, l’émetteur envoie régulièrement (toutes les 60 secondes) une demande de GET au serveur web sur lequel le collecteur est exécuté. Si Site Test n’obtient pas de réponse du serveur web, il écrit un message d’erreur dans syslog et envoie un message d’erreur à [!DNL data workbench server] (qui est écrit dans le fichier de log du capteur).

Si Test de site reçoit une réponse du serveur web, il recherche dans le fichier de file d’attente un paquet du serveur web. Si le paquet n’apparaît pas (indiquant que le collecteur n’était pas en cours d’exécution pour capturer l’événement), Site Test écrit un message d’erreur sur syslog et envoie un message d’erreur à Adobe (qui est également écrit dans le fichier de log du capteur).

Dans les requêtes envoyées par Site Test au serveur web, Site Test définit la valeur User-Agent sur &quot;[!DNL Sensor] Test&quot;. Si vous ne souhaitez pas que ces requêtes apparaissent dans votre jeu de données, ajoutez l’agent-utilisateur &quot;[!DNL Sensor] Test&quot; au fichier [!DNL Baseline Robots List.txt] ou au fichier [!DNL Extended Robots List.txt] dans le dossier [!DNL Lookups] de la balise [!DNL data workbench server].

**Activation du test de site dans l’émetteur**

1. Recherchez le fichier [!DNL txlogd.conf] sur l’ordinateur sur lequel [!DNL Sensor] est exécuté et ouvrez-le dans un éditeur de texte.

1. Dans le fichier [!DNL txlogd.conf], recherchez la ligne &quot;SiteTest&quot; et configurez-la comme illustré ci-dessous. Si votre fichier [!DNL txlogd.conf] ne contient pas la ligne &quot;SiteTest&quot;, ajoutez simplement la ligne à la fin du fichier de configuration.

   SiteTest http, *serverAddress*, *port*, *resource*

   où *serverAddress* est le nom ou l’adresse IP du serveur web, *port* est le port d’écoute HTTP du serveur et *resource* est la ressource spécifique que vous souhaitez que Site Test demande lors du test du serveur. Notez que *resource* peut inclure une chaîne de requête.

   Exemple : SiteTest http,localhost,80,/index.jsp

   Pour tester plusieurs serveurs web, il vous suffit de spécifier plusieurs lignes SiteTest.

## Recherche d’un cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Une autre manière de vérifier que le collecteur s’exécute sur un serveur web consiste à vérifier si [!DNL Sensor] définit un cookie dans les réponses que le serveur web renvoie aux clients. Si le collecteur fonctionne, le serveur web renvoie un cookie &quot;v1st&quot;.

Il est possible de renommer le cookie. Si vous l’avez fait, vous devez rechercher le nom spécifié, et non v1st.

Vous pouvez effectuer cette vérification à l’aide d’un script automatisé ou d’un agent de surveillance. Pour obtenir un exemple de script ou une aide supplémentaire concernant cette tâche, contactez les services de conseil d’Adobe.
