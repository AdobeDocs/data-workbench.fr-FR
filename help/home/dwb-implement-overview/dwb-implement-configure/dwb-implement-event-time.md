---
description: Cette section explique comment créer des horodatages pour un jeu de données Outils de données.
title: Configuration de l’heure d’événement
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de l’heure d’événement{#setting-up-event-time}

Cette section explique comment créer des horodatages pour un jeu de données Outils de données.

## Présentation de l’heure d’événement {#section-e10ef2b5b6244dc5b215836e3c77d663}

Heure de l’événement est la date et l’heure auxquelles la demande (ou l’événement) se produit.

Généralement, pour les données en ligne, *x_hit_time_gmt* est utilisé comme champ d’horodatage. L’heure de l’appel peut être utilisée comme horodatage pour les données hors ligne (telles que les données du centre d’appels). Il s’agit d’un champ obligatoire et toutes les sources de données doivent comporter un champ pouvant être utilisé comme horodatage. Cette information doit être fournie par votre organisation.

Dans DWB, les variables prédéfinies suivantes capturent l’horodatage :

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> Date et heure (GMT) auxquelles la demande a été reçue par le serveur. Le temps est exprimé sous la forme du nombre de 100 nanosecondes depuis le 1er janvier 1600. </p> <p>Exemple : Le mardi 13 septembre 2005, 127710989320000000 correspond à la valeur <i>x-timestamp</i> pour 11:28:52.0000000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> au format AAAA-MM-JJ HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> est l’heure de l’époque qui représente le nombre de secondes depuis le 1er janvier 1970, à 00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

Selon le format du champ de date, l’horodatage ou x-unixtime ou x-timestring est utilisé. Par exemple, si les données entrantes sont au format AAAA-MM-JJ, l’horodatage x doit être utilisé.

L’horodatage est défini dans l’un des formats et DWB génère en interne les deux autres formats. Il s’agit également de champs DWB prédéfinis et le même nom ne doit être utilisé pour aucun autre champ.

## Fuseaux horaires définis dans DWB {#section-3cdd12254342442b917376661e1d9c9f}

Si le champ de date contient l’un des fuseaux horaires mentionnés ci-dessous, DWB considère la totalité de la ligne de ce fuseau horaire particulier. Par exemple, un fichier a la date définie comme 2015-01-01 00:00:00 gmtet un autre fichier a la valeur 2015-01-01 00:00:00 cst, alors la date du premier fichier sera prise en compte dans le fuseau horaire GMT alors que la date du second fichier sera Fuseau horaire CST.

| Code | Fuseau horaire |
|---|---|
| gmt | Greenwich Mean |
| est | Standard oriental |
| edt | East Daylight |
| cst | Central Standard |
| cdt | Central Daylight |
| mst | Mountain Standard |
| mdt | Mountain Daylight |
| pst | Norme du Pacifique |
| pdt | Pacific Daylight |

>[!NOTE]
>
>DWB traite uniquement les Fuseaux horaires mentionnés ci-dessus.

## Définition de fuseaux horaires personnalisés {#section-7c351921f22b439b81c73f40d5b47536}

DWB ne traite pas le décalage dans le fuseau horaire. Pour tenir compte du décalage dans le fuseau horaire, les données doivent être formatées dans ce fuseau horaire de décalage.

Exemple : pour prendre en compte le format de date dans le fuseau horaire CST, les données doivent être fournies au format AAAA-MM-JJ HH:MM:SS UTC +/-HHMM par le client.

2015-10-18 05:00:00 UTC -0200

## Comment définir l’heure/l’horodatage d’un événement {#section-81507080f0b44ae6b83d3650ba019812}

Selon le format du champ de date, *x-timestamp, x-unixtime* ou *x-timestring* est utilisée. Dans l’exemple ci-dessous, puisque le paramètre *x-hit_time_gmt* est fourni au format époque *unix,* x-unixtimeest utilisé.

Dans le [!DNL foundation.cfg] fichier DWB (ou tout autre fichier de configuration situé sous le dossier de traitement du journal du jeu de données), utilisez la transformation Copier pour définir l’heure de l’événement comme indiqué ci-dessous :

Selon le format du champ de date, la variable x-timestamp, x-unixtime ou x-timestring est utilisée. Dans l’exemple ci-dessous, étant donné que x-hit_time_gmt est fourni au format époque unique, x-unixtime est utilisé.

Dans le fichier insight foundation.cfg (ou toute autre configuration sous le dossier de traitement du journal Datasetà), utilisez la transformation Copier pour définir l’heure de l’événement comme illustré ci-dessous : ![](assets/dwb_impl_timestamp1.png)

Si la date au format AAAA-MM-JJ HH:MM:SS.mmm est définie, la mesure x-timestring est utilisée. ![](assets/dwb_impl_timestamp2.png)Exemple : Si le champ de date est dans un format autre que celui défini dans le DWB, indiquez AAAA/MM/JJ, formatez-le d’abord dans l’un des formats d’horodatage acceptés par le DWB, puis affectez-le à la variable correspondante. Dans la capture d’écran ci-dessous, la date est d’abord convertie au format AAAA-MM-JJ, puis affectée à *x-timestring *variable. ![](assets/dwb_impl_timestamp3.png)

