---
description: Si vous travaillez avec les données collectées à partir du trafic sur le site Web, vous pouvez utiliser la transformation Sessioniser pour déterminer comment les sessions sont définies.
title: Sessionize
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
exl-id: bb25cb4b-7185-4524-8ff5-740b672e1cd9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Sessionize{#sessionize}

Si vous travaillez avec les données collectées à partir du trafic sur le site Web, vous pouvez utiliser la transformation Sessioniser pour déterminer comment les sessions sont définies.

La transformation prend comme entrée un horodatage et un ID de suivi et génère un numéro de session pour chaque entrée de journal. Le numéro de session est &quot;1&quot; pour la première session avec un ID de suivi donné, &quot;2&quot; pour la deuxième session avec le même ID de suivi, etc. La sortie peut être utilisée directement en tant que clé de session car elle possède une valeur unique pour chaque session.

>[!NOTE]
>
>Pour fonctionner, la transformation [!DNL Sessionize] requiert que les données soient triées dans le temps et regroupées par ID de suivi dans vos données source. Par conséquent, [!DNL Sessionize] ne fonctionne que lorsqu&#39;il est défini dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include].

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom descriptif de la transformation. Vous pouvez entrer n'importe quel nom ici. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commentaires </td> 
   <td colname="col2"> Facultatif. Remarques sur la transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> Conditions d'application de cette transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Horodatage d’entrée </td> 
   <td colname="col2"> Champ contenant les valeurs de l’horodatage à utiliser. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de suivi d’entrée </td> 
   <td colname="col2"> <p>Champ contenant les valeurs de l'ID de suivi à utiliser. La valeur doit être un nombre hexadécimal 64 bits (16 chiffres) ou plus petit ou un nombre décimal inférieur ou égal à 16 chiffres. </p> <p> <p>Remarque : Si vous souhaitez utiliser un champ autre que x-trackingid pour l’ID de suivi, vous devez d’abord hacher le champ. Voir <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée maximale de session </p> </td> 
   <td colname="col2">Durée la plus longue avant le démarrage d’une nouvelle session. (Cela empêche les pages Web dont le contenu est automatiquement actualisé de créer des sessions arbitrairement longues.) Si la <span class="wintitle"> condition de dépassement de délai</span> est satisfaite et que le parrain d'un clic est défini sur l'une des entrées du paramètre Domaines internes, la durée maximale de la session est utilisée pour définir la fin d'une session. Aucune session ne peut être plus longue que la durée maximale de session spécifiée, quel que soit le nombre de clics qu’elle contient. La valeur recommandée est de 48 heures. Pour plus d'informations sur les paramètres Durée maximale de session et Domaines internes, voir <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Paramètres de configuration pour les données Web</a>. </td> 
   <td colname="col3"> 48 heures </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéro de session de sortie </td> 
   <td colname="col2"> Champ dans lequel le numéro de session est stocké. Ce champ a une valeur unique pour chaque session pour chaque visiteur. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délai d’expiration de la session </td> 
   <td colname="col2"> <p>Durée nécessaire entre les entrées de journal d’un visiteur donné pour déterminer la fin d’une session et le début d’une nouvelle session (c’est-à-dire le délai d’attente habituel utilisé pour définir une session utilisateur). La valeur recommandée de ce paramètre est de 30 minutes. Si la condition de dépassement de délai n'est pas remplie et que le parrain d'un clic n'est pas défini sur l'un des parrains du paramètre Domaines internes, le délai d'expiration de la session est utilisé pour définir la session. </p> <p> Si la condition de dépassement de délai est remplie et si cs(parrain-domain) pour une entrée de journal se trouve dans la liste des domaines internes, la durée maximale de la session détermine si l'entrée de journal active fait partie d'une session existante ou du début d'une nouvelle session. </p> <p> Pour plus d'informations sur le paramètre Délai d'expiration de session, voir <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Paramètres de configuration pour les données Web</a>. </p> </td> 
   <td colname="col3"> 30 minutes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition de dépassement de délai </td> 
   <td colname="col2"> Condition qui doit être remplie pour qu’une entrée de journal soit considérée comme le début d’une nouvelle session. Notez que le temps qui s’écoule entre l’entrée de journal et l’entrée de journal précédente doit être au moins la valeur du paramètre Délai d’expiration de session. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Une nouvelle session commence lorsque l’une des situations suivantes se produit :

* L’ID de suivi change.
* Le temps écoulé depuis la dernière entrée de journal est au moins égal à la valeur du paramètre Délai d’expiration de la session et la condition Délai d’expiration est remplie.
* Le temps écoulé depuis la première entrée de journal de la dernière session dépasse la valeur du paramètre Durée maximale de la session.

>[!NOTE]
>
>Si vous avez déjà défini les paramètres Durée maximale de session et Délai d’expiration de session dans le fichier [!DNL Session Parameters.cfg], n’entrez pas de valeurs pour ces paramètres dans la configuration. Vous pouvez référencer les paramètres en saisissant *$(nom du paramètre)* comme indiqué dans l’exemple suivant. Pour plus d&#39;informations sur ces paramètres, voir [Paramètres de configuration pour les données Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

La transformation [!DNL Sessionize] de cet exemple prend comme entrée les champs x-timestamp et x-trackingid et enregistre le numéro de session pour chaque entrée de journal dans le champ x-session-key. [!DNL Timeout Condition] de la transformation repose sur une condition [!DNL Neither] : Si le champ cs(domaine-parrain) d&#39;une entrée de journal correspond à un membre du paramètre Domaines internes, la condition est évaluée sur false. Notez les références aux paramètres Domaines internes et Délai d’expiration de session.

Pour plus d&#39;informations sur [!DNL NeitherCondition], consultez [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Pour plus d’informations sur les paramètres Domaines internes et Délai d’expiration de session, voir [Paramètres de configuration pour les données Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

![](assets/cfg_TransformationType_Sessionize.png)
