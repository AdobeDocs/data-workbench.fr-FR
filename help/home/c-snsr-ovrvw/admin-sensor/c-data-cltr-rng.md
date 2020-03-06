---
description: Vérifiez si le collecteur est exécuté selon différentes méthodes.
solution: Insight
title: Confirmation de l’exécution du collecteur de données
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confirmation de l’exécution du collecteur de données{#confirming-that-the-data-collector-is-running}

Vérifiez si le collecteur est exécuté selon différentes méthodes.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

* [Utilisez la fonctionnalité de test de site dans l’émetteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Vérifiez si [!DNL Sensor] définit un cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Utilisation du test de site {#section-a5a697c3252e40f184c0b662926170f2}

Une manière de vérifier que le collecteur est en cours d’exécution consiste à activer la fonction Test du site dans l’émetteur. Lorsque vous activez Test du site, l’émetteur envoie régulièrement (toutes les 60 secondes) une requête GET au serveur Web sur lequel le collecteur est en cours d’exécution. Si le Test du site n&#39;obtient pas de réponse du serveur Web, il écrit un message d&#39;erreur dans syslog et envoie un message d&#39;erreur au [!DNL data workbench server] (qui est écrit dans le fichier de log du capteur).

Si Site Test reçoit une réponse du serveur Web, il recherche dans le fichier de file d’attente un paquet du serveur Web. Si le paquet n’apparaît pas (indiquant que le collecteur n’était pas en cours d’exécution pour capturer l’événement), Site Test écrit un message d’erreur dans syslog et envoie un message d’erreur à Adobe (également écrit dans le fichier de log du capteur).

Dans les requêtes envoyées par Test du site au serveur Web, Test du site définit la valeur User-Agent sur &quot; [!DNL Sensor] Test&quot;. Si vous ne souhaitez pas que ces requêtes s’affichent dans votre jeu de données, ajoutez l’agent utilisateur &quot; [!DNL Sensor] Test&quot; au [!DNL Baseline Robots List.txt] fichier ou au [!DNL Extended Robots List.txt] fichier dans le [!DNL Lookups] dossier du [!DNL data workbench server].

**Pour activer le test du site dans l’émetteur**

1. Recherchez le [!DNL txlogd.conf] fichier sur l’ordinateur [!DNL Sensor] en cours d’exécution et ouvrez-le dans un éditeur de texte.

1. Dans le [!DNL txlogd.conf] fichier, recherchez la ligne &quot;SiteTest&quot; et configurez-la comme illustré ci-dessous. Si votre [!DNL txlogd.conf] fichier n’inclut pas la ligne &quot;SiteTest&quot;, il vous suffit d’ajouter la ligne à la fin du fichier de configuration.

   SiteTest http, *serverAddress*, *port*, *ressource*

   où *serverAddress* est le nom ou l’adresse IP du serveur Web, *port* est le port d’écoute HTTP du serveur et *ressource* est la ressource spécifique que le Test du site doit demander lors du test du serveur. Notez que *resource* peut inclure une chaîne de requête.

   Exemple : SiteTest http,localhost,80,/index.jsp

   Pour tester plusieurs serveurs Web, il vous suffit de spécifier plusieurs lignes SiteTest.

## Recherche d’un cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Une autre manière de vérifier que le collecteur est en cours d’exécution sur un serveur Web consiste à vérifier si un cookie [!DNL Sensor] est défini dans les réponses que le serveur Web renvoie aux clients. Si le collecteur fonctionne, le serveur Web renvoie un cookie &quot;v1st&quot;.

Il est possible de renommer le cookie. Si vous l’avez fait, vous devez rechercher le nom spécifié, et non v1st.

Vous pouvez effectuer cette vérification à l’aide d’un script automatisé ou d’un agent de surveillance. Pour obtenir un exemple de script ou une aide supplémentaire sur cette tâche, contactez les services de conseil Adobe.
