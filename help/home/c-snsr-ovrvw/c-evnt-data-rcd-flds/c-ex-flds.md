---
description: Lorsqu’il est utilisé sur un serveur, le capteur peut collecter des champs de données de événement à partir de n’importe quel en-tête ou variable de réponse HTTP valide disponible par le biais de l’API du serveur.
solution: Analytics
title: Champs extensibles
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---


# Champs extensibles{#extensible-fields}

Lorsqu’il est utilisé sur un serveur, le capteur peut collecter des champs de données de événement à partir de n’importe quel en-tête ou variable de réponse HTTP valide disponible par le biais de l’API du serveur.

Pour collecter ces champs de données, vous devez spécifier les champs d’en-tête ou les variables de votre choix dans le fichier de [!DNL txlogd.conf] configuration [!DNL Sensor].

* [En-têtes de demande](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variables de serveur](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## En-têtes de demande {#section-22766692b45546d8bfc93dbe3bc9368f}

Voici la syntaxe permettant de spécifier un champ d’en-tête de requête à collecter (par exemple, Hôte, Acceptation-Encodage, Conserver-Alive, etc.) dans [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Les données collectées sont enregistrées par [!DNL Sensor] un champ nommé &quot;cs(RequestHeaderName)&quot; dans les [!DNL .vsl] fichiers créés par [!DNL data workbench server]. Par exemple, pour collecter la valeur d’en-tête de requête spécifique dans l’en-tête de requête &quot;Hôte&quot;, tapez &quot;Hôte LogHeader&quot; dans [!DNL txlogd.conf]. Les données sont enregistrées dans le champ &quot;cs(Host)&quot; de l’enregistrement de données du événement.

## Variables de serveur {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] Vous pouvez collecter des champs de données à partir d&#39;en-têtes de réponse ou de variables de serveur accessibles par API à l&#39;aide des entrées SpecialLogField que vous incluez dans le [!DNL txlogd.conf] fichier. Vous pouvez également utiliser des entrées &quot;SpecialLogField&quot; en plus ou à la place des entrées &quot;LogHeader&quot; pour collecter les en-têtes de demande. Voir En-têtes [de](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)requête. L’option d’en-têtes de demande reste disponible pour une compatibilité ascendante.

Voici la syntaxe permettant de spécifier un &quot;SpecialLogField&quot; dans [!DNL txlogd.conf]:

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
   <td colname="col2"> Nom du champ auquel les données collectées sont enregistrées dans l’enregistrement de données du événement et les fichiers <span class="filepath"> .vsl </span> créés par le serveur <span class="keyword"> Outils de données </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Toute variable de serveur disponible pour <span class="wintitle"> Sensor </span> via l’API du serveur </p> <p>Exemple : response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log ou vys_cookie </p> <p>Pour définir l’étape, vous devez connaître les variables de serveur disponibles pour vys_log et vys_cookie. </p> <p>Exemple : Pour serverVariable response.p3p, vous devez entrer vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour obtenir de l’aide sur la configuration [!DNL Sensor] de la collecte de champs d’enregistrement de données de événement extensibles, contactez les services de conseil en Adobe.
