---
description: Lorsqu’il est utilisé sur un serveur, le capteur peut collecter des champs de données de événement à partir de n’importe quel en-tête ou variable de réponse HTTP valide disponible par le biais de l’API du serveur.
title: Champs extensibles
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Champs extensibles{#extensible-fields}

Lorsqu’il est utilisé sur un serveur, le capteur peut collecter des champs de données de événement à partir de n’importe quel en-tête ou variable de réponse HTTP valide disponible par le biais de l’API du serveur.

Pour collecter ces champs de données, vous devez spécifier les champs d&#39;en-tête ou les variables de votre choix dans le fichier de configuration [!DNL txlogd.conf] pour [!DNL Sensor].

* [En-têtes de demande](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variables de serveur](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## En-têtes de requête {#section-22766692b45546d8bfc93dbe3bc9368f}

Voici la syntaxe permettant de spécifier un champ d’en-tête de requête à collecter (par exemple, Hôte, Acceptation-Encodage, Conserver-Alive, etc.) dans [!DNL txlogd.conf] :

```
LogHeader RequestHeaderName
```

Les données collectées sont enregistrées par [!DNL Sensor] dans un champ nommé &quot;cs(RequestHeaderName)&quot; dans les fichiers [!DNL .vsl] créés par [!DNL data workbench server]. Par exemple, pour collecter la valeur d&#39;en-tête de requête spécifique à partir de l&#39;en-tête de requête &quot;Hôte&quot;, tapez &quot;Hôte LogHeader&quot; dans [!DNL txlogd.conf]. Les données sont enregistrées dans le champ &quot;cs(Host)&quot; de l’enregistrement de données du événement.

## Variables de serveur {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] Vous pouvez collecter des champs de données à partir d&#39;en-têtes de réponse ou de variables de serveur accessibles par API à l&#39;aide des entrées SpecialLogField que vous incluez dans le  [!DNL txlogd.conf] fichier. Vous pouvez également utiliser des entrées &quot;SpecialLogField&quot; en plus ou à la place des entrées &quot;LogHeader&quot; pour collecter les en-têtes de demande. Voir [En-têtes de requête](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). L’option d’en-têtes de demande reste disponible pour une compatibilité ascendante.

Voici la syntaxe permettant de spécifier un &quot;champJournalSpécial&quot; dans [!DNL txlogd.conf] :

```
SpecialLogField cs(log field) = serverVariable stage
```

Le tableau suivant inclut des descriptions des composants d&#39;une entrée &quot;SpecialLogField&quot;.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(champ journal) </td> 
   <td colname="col2"> Nom du champ dans lequel les données collectées sont enregistrées dans l'enregistrement de données du événement et les fichiers <span class="filepath"> .vsl </span> créés par le serveur d'outils de données <span class="keyword"> </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Toute variable de serveur disponible pour <span class="wintitle"> Capteur </span> via l’API du serveur. </p> <p>Exemple : response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log ou vys_cookie </p> <p>Pour définir l’étape, vous devez connaître les variables de serveur disponibles pour vys_log et vys_cookie. </p> <p>Exemple : Pour serverVariable response.p3p, vous devez entrer vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour obtenir de l&#39;aide sur la configuration de [!DNL Sensor] pour collecter des champs d&#39;enregistrement de données de événement extensibles, contactez les services de conseil en Adobe.
