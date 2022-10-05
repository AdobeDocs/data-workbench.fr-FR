---
description: Lorsqu’il est utilisé sur un serveur, le capteur peut collecter des champs de données d’événement à partir de n’importe quel en-tête ou variable HTTP valide disponible via l’API du serveur.
title: Champs extensibles
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# Champs extensibles{#extensible-fields}

{{eol}}

Lorsqu’il est utilisé sur un serveur, le capteur peut collecter des champs de données d’événement à partir de n’importe quel en-tête ou variable HTTP valide disponible via l’API du serveur.

Pour collecter ces champs de données, vous devez spécifier les champs d’en-tête ou les variables de votre choix dans la variable [!DNL txlogd.conf] fichier de configuration pour [!DNL Sensor].

* [En-têtes de requête](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variables de serveur](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## En-têtes de requête {#section-22766692b45546d8bfc93dbe3bc9368f}

Voici la syntaxe permettant de spécifier un champ d’en-tête de requête à collecter (par exemple, Hôte, Accept-Encoding, Keep-Alive, etc.) dans [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Les données collectées sont enregistrées par [!DNL Sensor] à un champ nommé &quot;cs(RequestHeaderName)&quot; dans la variable [!DNL .vsl] les fichiers créés par [!DNL data workbench server]. Par exemple, pour collecter la valeur d’en-tête de requête spécifique à partir de l’en-tête de requête &quot;Hôte&quot;, saisissez &quot;Hôte d’en-tête de journal&quot; dans [!DNL txlogd.conf]. Les données sont enregistrées dans le champ &quot;cs(Host)&quot; de l’enregistrement de données d’événement.

## Variables de serveur {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] peut collecter des champs de données à partir d’en-têtes de réponse ou de variables de serveur accessibles par l’API à l’aide des entrées SpecialLogField que vous incluez dans la variable [!DNL txlogd.conf] fichier . Vous pouvez également utiliser des entrées &quot;SpecialLogField&quot; en plus ou au lieu des entrées &quot;LogHeader&quot; pour collecter les en-têtes de requête. Voir [En-têtes de requête](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). L’option d’en-têtes de requête reste disponible pour la compatibilité ascendante.

Voici la syntaxe permettant de spécifier un &quot;SpecialLogField&quot; dans [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

Le tableau suivant comprend des descriptions des composants d’une entrée &quot;SpecialLogField&quot;.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(champ de journal) </td> 
   <td colname="col2"> Nom du champ auquel les données collectées sont enregistrées dans l’enregistrement de données d’événement et le <span class="filepath"> .vsl </span> les fichiers créés par <span class="keyword"> serveur Data Workbench </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Toute variable de serveur disponible pour <span class="wintitle"> Sensor </span> via l’API du serveur </p> <p>Exemple : response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log ou vys_cookie </p> <p>Pour spécifier l’étape, vous devez savoir quelles variables de serveur sont disponibles pour vys_log et vys_cookie. </p> <p>Exemple : Pour le fichier serverVariable response.p3p, saisissez vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour obtenir de l’aide sur la configuration [!DNL Sensor] pour collecter des champs d’enregistrement de données d’événement extensibles, contactez les services de conseil d’Adobe.
