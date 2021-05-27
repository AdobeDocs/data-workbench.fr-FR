---
description: Les sources de journal sont des fichiers qui contiennent les données à utiliser pour créer un jeu de données.
title: Sources de journalisation
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---

# Sources de journalisation{#log-sources}

Les sources de journal sont des fichiers qui contiennent les données à utiliser pour créer un jeu de données.

Les données disponibles dans les sources de journal sont appelées données d’événement, car chaque enregistrement de données représente un enregistrement de transaction ou une instance unique d’un événement. Le serveur Data Workbench peut traiter les sources de journaux dérivées des données collectées par [!DNL Sensors] ou extraites d’autres sources de données.

* **Données collectées par [!DNL Sensors] : ** Les données collectées par [!DNL Sensors] à partir de serveurs HTTP et d’applications sont transmises aux serveurs Data Workbench, qui convertissent les données en fichiers journaux hautement compressés ( [!DNL .vsl]). Voir [Fichiers Capteur](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Données extraites par le serveur Insight :**  le serveur Data Workbench lit les données d’événement contenues dans des fichiers plats, des fichiers XML ou des bases de données conformes à la ODBC et utilise ses décodeurs pour extraire les éléments souhaités des données. Ces données d’événement ne doivent pas nécessairement résider dans la mémoire, mais les enregistrements qui contiennent les données doivent inclure un ID de suivi. Voir [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [Sources de journal XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887) et [Sources de données ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**Pour ajouter une source de journal**

1. Ouvrez [!DNL Log Processing.cfg] dans Data Workbench.
1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Log Sources]**, puis cliquez sur **[!UICONTROL Add New]**.

1. Sélectionnez l’une des options suivantes :

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Les paramètres spécifiques utilisés pour définir un jeu de données varient en fonction du type de source de journal à utiliser dans le processus de configuration du jeu de données. Spécifiez les paramètres comme indiqué dans la section correspondant à la source de journal appropriée :

   * [Fichiers de Capteur](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [Sources de journal XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [Sources de données ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Après avoir défini votre source de journal (et apporté des modifications à d’autres paramètres) dans le fichier [!DNL Log Processing.cfg], enregistrez le fichier localement et enregistrez-le dans votre profil de jeu de données sur le serveur Data Workbench.

   >[!NOTE]
   >
   >Un serveur Data Workbench [!DNL File Server Unit] peut recevoir et stocker des fichiers [!DNL Sensor], des fichiers journaux et des fichiers XML et les envoyer au [!DNL Data Processing Units] du serveur Data Workbench qui construit le jeu de données. Voir [Configuration d’une unité de serveur de fichiers du serveur Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Vous pouvez ouvrir la configuration de n’importe quelle source de journal à partir d’une [!DNL Transformation Dependency Map]. Pour plus d’informations sur [!DNL Transformation Dependency Map], voir [Outils de configuration des jeux de données](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Conditions  {#section-d5901a4872774ad5bd01a18db114f1f2}

Les données d’événement collectées par [!DNL Sensors] à partir de serveurs HTTP et d’applications sont transmises aux serveurs Data Workbench, qui convertissent les données en fichiers journaux hautement compressés ( [!DNL .vsl]). Le format de fichier [!DNL .vsl] est géré par le serveur Data Workbench et chaque fichier porte le nom du format :

YYYYMDD-*SENSORID*.VSL

où YYYYMMDD est la date du fichier et *SENSORID* est le nom (attribué par votre organisation) qui indique quelles [!DNL Sensor] ont collecté et transmis les données au serveur Data Workbench.

## Paramètres {#section-5c3f1e341c284486aeba3452057da7f3}

Pour les fichiers [!DNL Sensor], les paramètres suivants sont disponibles :

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Chemins du journal </td> 
   <td colname="col2"> <p>Répertoires dans lesquels les fichiers <span class="filepath"> .vsl</span> sont stockés. L’emplacement par défaut est le répertoire Journaux . Un chemin relatif fait référence au répertoire d’installation du serveur Data Workbench. </p> <p>Vous pouvez utiliser des caractères génériques pour spécifier les fichiers <span class="filepath"> .vsl</span> à traiter : 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * correspond à n’importe quel nombre de caractères </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? correspond à un caractère unique </li> 
     </ul> </p> <p> Par exemple, le chemin d’accès au journal <span class="filepath"> Journaux\*.vsl</span> correspond à n’importe quel fichier du répertoire Journaux se terminant par <span class="filepath"> .vsl</span>. Le chemin d’accès au journal <span class="filepath"> Journaux\*-SENSOR?.vsl</span> correspond aux fichiers du répertoire Journaux avec n’importe quelle date (YYYMMDD) et un caractère unique après le CAPTEUR, comme dans SENSOR1. </p> <p> Si vous souhaitez rechercher tous les sous-répertoires du chemin spécifié, vous devez définir le paramètre Récursif sur true. </p> <p> <p>Remarque : Si les fichiers doivent être lus à partir d’une <span class="wintitle"> unité de serveur de fichiers </span> d’un serveur Data Workbench, vous devez saisir les URI appropriés dans le paramètre Chemins de journal . Par exemple, l’URI <span class="filepath"> /Logs/*-*.vsl</span> correspond à n’importe quel fichier <span class="filepath"> .vsl</span> dans le répertoire Journaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité de serveur de fichiers du serveur Insight</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur de journal </td> 
   <td colname="col2">Informations (adresse, nom, port, etc.) nécessaires à la connexion à un serveur de fichiers. Si le paramètre Serveur de journaux contient une entrée , les <span class="wintitle"> chemins de journal</span> sont interprétés comme des URI. Sinon, elles sont interprétées comme des chemins locaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité de serveur de fichiers du serveur Insight</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identifiant de source de journal </td> 
   <td colname="col2"> <p>La valeur de ce paramètre peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce paramètre permet de différencier les entrées de journal de différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné avec une valeur identifiant la source du journal pour chaque entrée de journal. Par exemple, si vous souhaitez identifier les entrées de journal d’un capteur <span class="wintitle"> </span> nommé VSensor01, vous pouvez saisir <span class="filepath"> de VSensor01</span>, et cette chaîne sera transmise au champ x-log-source-id pour chaque entrée de journal de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Champs d’enregistrement des données d’événement</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Récursif </td> 
   <td colname="col2"> Vrai ou faux. S’il est défini sur true, tous les sous-répertoires de chaque chemin spécifié dans <span class="wintitle"> Chemins du journal</span> sont recherchés dans les fichiers correspondant au nom de fichier ou au modèle de caractère générique spécifié. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser les heures de début/fin </td> 
   <td colname="col2"> <p>Vrai ou faux. Si la valeur est définie sur true et que l’heure de début ou l’heure de fin est spécifiée, tous les fichiers de cette source de journal doivent avoir des noms de fichier commençant par des dates au format ISO (YYYMMDD). Chaque fichier contient des données pour un jour GMT (par exemple, la période commençant à 0000 GMT un jour et se terminant à 0000 GMT le jour suivant). Si les fichiers de sources de journaux contiennent des données qui ne correspondent pas à un jour GMT, ce paramètre doit être défini sur false pour éviter des résultats incorrects. </p> <p> <p>Remarque : Par défaut, les fichiers <span class="filepath"> .vsl </span>contenant des données collectées par <span class="wintitle"> Capteur</span> répondent automatiquement aux exigences d’attribution de noms et de période décrites ci-dessus. Si vous définissez ce paramètre sur true, le serveur Data Workbench traite toujours les données à partir de fichiers dont les noms incluent des dates ISO comprises entre l’heure de début et l’heure de fin spécifiées. Si vous définissez ce paramètre sur false, le serveur Data Workbench lit tous les fichiers <span class="filepath"> .vsl</span> pendant le traitement du journal pour déterminer les fichiers qui contiennent des données dans la plage Heure de début et Heure de fin. </p> </p> <p> Pour plus d’informations sur les paramètres Heure de début et Heure de fin, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>N’utilisez pas les paramètres de configuration des sources de données [!DNL Sensor] pour déterminer quelles entrées de journal dans un fichier journal doivent être incluses dans un jeu de données. Configurez plutôt la source de données pour qu’elle pointe vers tous les fichiers journaux d’un répertoire. Ensuite, utilisez les paramètres Heure de début et Heure de fin de [!DNL Log Processing.cfg] pour déterminer les entrées de journal à utiliser dans la création du jeu de données. Voir [Filtres de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

Le fichier contenant les données d’événement doit répondre aux exigences suivantes :

* Chaque enregistrement de données d’événement dans le fichier doit être représenté par une ligne.
* Les champs d’un enregistrement doivent être séparés, qu’ils soient vides ou non, par un délimiteur ASCII. Le serveur Data Workbench ne nécessite pas l’utilisation d’un délimiteur spécifique. Vous pouvez utiliser n’importe quel caractère qui n’est pas un caractère de fin de ligne et n’apparaît nulle part dans les données d’événement elles-mêmes.
* Chaque enregistrement du fichier doit contenir :

   * Un ID de suivi
   * Horodatage

* Pour spécifier les heures de début et de fin du traitement des données, chaque nom de fichier doit être au format suivant :

   * [!DNL YYYYMMDD-SOURCE.log]

   où *YYYMMDD* est le jour de l’heure moyenne de Greenwich (GMT) de toutes les données du fichier, et *SOURCE* est une variable identifiant la source des données contenues dans le fichier.

   >[!NOTE]
   >
   >Veuillez contacter les services de conseil d’Adobe pour une révision des fichiers journaux que vous prévoyez d’incorporer dans le jeu de données.

## Paramètres {#section-83a861ac24954d54bbb9530e4d8bf23c}

Pour les sources de journal des fichiers journaux, les paramètres du tableau suivant sont disponibles.

>[!NOTE]
>
>Le traitement des sources de journaux de fichiers journaux nécessite des paramètres supplémentaires définis dans un fichier [!DNL Log Processing Dataset Include], qui contient un sous-ensemble des paramètres inclus dans un fichier [!DNL Log Processing.cfg] ainsi que des paramètres spéciaux pour définir les décodeurs permettant d’extraire des données du fichier journal. Pour plus d’informations sur la définition de décodeurs pour les sources de journaux de fichiers journaux, voir [Groupes de décodeur de fichier texte](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> L’identifiant de la source du fichier journal. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chemins du journal </td> 
   <td colname="col2"> <p>Les répertoires dans lesquels les fichiers journaux sont stockés. L’emplacement par défaut est le répertoire Journaux . Un chemin relatif fait référence au répertoire d’installation du serveur Data Workbench. </p> <p> Vous pouvez utiliser des caractères génériques pour spécifier les fichiers journaux à traiter : 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * correspond à n’importe quel nombre de caractères. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? correspond à un seul caractère. </li> 
     </ul> </p> <p> Par exemple, le chemin d’accès au journal <span class="filepath"> Journaux\*.log</span> correspond à n’importe quel fichier du répertoire Journaux se terminant par <span class="filepath"> .log</span>. </p> <p> Si vous souhaitez rechercher tous les sous-répertoires du chemin spécifié, vous devez définir le paramètre Récursif sur true. </p> <p> Si les fichiers doivent être lus à partir d’une <span class="wintitle"> unité de serveur de fichiers </span> d’un serveur Data Workbench, vous devez saisir les URI appropriés dans le paramètre Chemins de journal . Par exemple, <span class="filepath"> URI/Logs/*.log</span> correspond à n’importe quel fichier <span class="filepath"> .log</span> dans le répertoire Journaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité de serveur de fichiers du serveur Insight</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur de journal </td> 
   <td colname="col2"> Informations (adresse, nom, port, etc.) nécessaires à la connexion à un serveur de fichiers. Si le paramètre Serveur de journaux contient une entrée , les <span class="wintitle"> chemins de journal</span> sont interprétés comme des URI. Sinon, elles sont interprétées comme des chemins locaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité de serveur de fichiers du serveur Insight</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressé </td> 
   <td colname="col2"> Vrai ou faux. Cette valeur doit être définie sur true si les fichiers journaux à lire par le serveur Data Workbench sont des fichiers gzip compressés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de décodeur </td> 
   <td colname="col2"> Nom du groupe de décodeur de fichier texte à appliquer à la source du journal du fichier journal. Ce nom doit correspondre exactement au nom du groupe de décodeur de fichier texte correspondant spécifié dans le fichier <span class="wintitle"> Log Processing Dataset Include</span> . Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Groupes de décodeur de fichier texte</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identifiant de source de journal </td> 
   <td colname="col2"> <p>La valeur de ce paramètre peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce paramètre permet de différencier les entrées de journal de différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné avec une valeur identifiant la source du journal pour chaque entrée de journal. Par exemple, si vous souhaitez identifier les entrées de journal à partir d’une source de fichier journal nommée LogFile01, vous pouvez saisir <span class="filepath"> à partir de LogFile01</span>, et cette chaîne sera transmise au champ x-log-source-id pour chaque entrée de journal provenant de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Champs d’enregistrement des données d’événement</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle de masque </td> 
   <td colname="col2"> <p>Expression régulière avec un seul sous-modèle de capture qui extrait un nom cohérent utilisé pour identifier la source d’une série de fichiers journaux. Seul le nom de fichier est pris en compte. Le chemin et l’extension ne sont pas pris en compte pour la correspondance de l’expression régulière. Si vous ne spécifiez pas de <span class="wintitle"> modèle de masque</span>, un masque est généré automatiquement. </p> <p> Pour les fichiers <span class="filepath"> Logs\010105server1.log</span> et <span class="filepath"> Logs\010105server2.log</span>, le <span class="wintitle"> modèle de masque</span> serait <code>[0-9]{6}(.*)</code>. Ce modèle extrait la chaîne "server1" ou "server2" des noms de fichiers ci-dessus. </p> <p> Voir <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expressions régulières</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Récursif </td> 
   <td colname="col2"> Vrai ou faux. Si ce paramètre est défini sur true, tous les sous-répertoires de chaque chemin spécifié dans <span class="wintitle"> Chemins du journal</span> sont recherchés dans les fichiers correspondant au modèle de nom de fichier ou de caractère générique spécifié. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeter le fichier </td> 
   <td colname="col2"> Chemin d’accès et nom de fichier du fichier contenant les entrées de journal qui ne répondent pas aux conditions du décodeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser les heures de début/fin </td> 
   <td colname="col2"> <p>Vrai ou faux. Si ce paramètre est défini sur true et que l’heure de début ou l’heure de fin est spécifiée, tous les fichiers de cette source de journal doivent avoir des noms de fichier commençant par des dates au format ISO (YYYMMDD). Chaque fichier contient des données pour un jour GMT (par exemple, la période commençant à 0000 GMT un jour et se terminant à 0000 GMT le jour suivant). Si les noms de fichiers des sources de journaux ne commencent pas par des dates ISO ou si les fichiers contiennent des données qui ne correspondent pas à un jour GMT, ce paramètre doit être défini sur false pour éviter des résultats incorrects. </p> <p> <p>Remarque :  Si les exigences d’attribution de noms et de période décrites ci-dessus sont respectées pour les fichiers journaux et que vous définissez ce paramètre sur true, le groupe de décodeur de fichier texte spécifié limite les fichiers lus à ceux dont les noms comportent des dates ISO comprises entre l’heure de début et l’heure de fin spécifiées. Si vous définissez ce paramètre sur false, le serveur Data Workbench lit tous les fichiers journaux pendant le traitement des journaux pour déterminer les fichiers qui contiennent des données dans les plages Heure de début et Heure de fin. </p> </p> <p> Pour plus d’informations sur les paramètres Heure de début et Heure de fin, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, le jeu de données est construit à partir de deux types de sources de journal.

La source de journal 0 spécifie les fichiers journaux générés à partir des données d’événement capturées par [!DNL Sensor]. Cette source de données pointe vers un répertoire appelé Logs et vers tous les fichiers de ce répertoire avec une extension de nom de fichier [!DNL .vsl].

La source de journal 1 pointe vers tous les fichiers du répertoire Journaux avec une extension de nom de fichier [!DNL .txt]. Le groupe de décodeur pour cette source de journal est appelé &quot;Journaux de texte&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Vous ne devez pas supprimer ni déplacer les fichiers journaux une fois les sources de données d’un jeu de données définies. Seuls les fichiers journaux nouvellement créés doivent être ajoutés au répertoire pour les sources de données.

<!--
c_xml_log_sources.xml
-->

Le fichier contenant les données d’événement doit répondre aux exigences suivantes :

* Les données d’événement doivent être incluses dans un fichier XML correctement formaté avec les relations parent-enfant appropriées.
* Un groupe de décodeur unique doit exister pour chaque format de fichier XML. Pour plus d’informations sur la création d’un groupe de décodeurs, voir [Groupes de décodeurs XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Chaque enregistrement de visiteur dans le fichier doit contenir :

   * Un ID de suivi
   * Horodatage

* Pour spécifier les heures de début et de fin du traitement des données, chaque nom de fichier doit se présenter sous la forme

[!DNL YYYYMMDD-SOURCE.log]

où *YYYMMDD* est le jour de l’heure moyenne de Greenwich (GMT) de toutes les données du fichier, et *SOURCE* est une variable identifiant la source des données contenues dans le fichier.

Pour un exemple de fichier XML qui répond à ces exigences, voir [Groupes de décodeur XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Veuillez contacter les services de conseil d’Adobe pour une révision des fichiers journaux XML que vous prévoyez d’incorporer dans le jeu de données.

## Paramètres {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Pour les sources de logs XML, les paramètres du tableau suivant sont disponibles.

>[!NOTE]
>
>Le traitement des sources de logs XML nécessite des paramètres supplémentaires définis dans un fichier [!DNL Log Processing Dataset Include], qui contient un sous-ensemble des paramètres inclus dans un fichier [!DNL Log Processing.cfg] ainsi que des paramètres spéciaux pour définir les décodeurs permettant d&#39;extraire des données du fichier XML. Pour plus d’informations sur la définition de décodeurs pour les sources de journaux XML, voir [Groupes de décodeurs XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> L’identifiant de la source du journal XML. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chemins du journal </td> 
   <td colname="col2"> <p>Les répertoires dans lesquels les sources du journal XML sont stockées. L’emplacement par défaut est le répertoire Journaux . Un chemin relatif fait référence au répertoire d’installation du serveur Data Workbench. </p> <p> Vous pouvez utiliser des caractères génériques pour spécifier les sources de journal XML à traiter : 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * correspond à n’importe quel nombre de caractères </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? correspond à un caractère unique </li> 
     </ul> </p> <p>Par exemple, le chemin d’accès au journal <span class="filepath"> Journaux\*.xml</span> correspond à n’importe quel fichier du répertoire Journaux se terminant par <span class="filepath"> .xml</span>. </p> <p> Si vous souhaitez rechercher tous les sous-répertoires du chemin spécifié, vous devez définir le champ <span class="wintitle"> Récursif</span> sur true. </p> <p> <p>Remarque : Si les fichiers doivent être lus à partir d’une <span class="wintitle"> unité de serveur de fichiers </span> d’un serveur Data Workbench, vous devez saisir les URI appropriés dans le champ <span class="wintitle"> Chemins du journal</span> . Par exemple, <span class="filepath"> URI/Logs/*.xml</span> correspond à n’importe quel fichier <span class="filepath"> .xml</span> dans le répertoire Journaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité de serveur de fichiers du serveur Insight</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur de journal </td> 
   <td colname="col2"> Informations (adresse, nom, port, etc.) nécessaires à la connexion à un serveur de fichiers. S’il existe une entrée dans le champ <span class="wintitle"> Serveur de journal</span> , les <span class="wintitle"> chemins de journal</span> sont interprétés comme des URI. Sinon, elles sont interprétées comme des chemins locaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité de serveur de fichiers du serveur Insight</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressé </td> 
   <td colname="col2"> Vrai ou faux. Cette valeur doit être définie sur true si les sources de journaux XML à lire par le serveur Data Workbench sont des fichiers gzip compressés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de décodeur </td> 
   <td colname="col2"> Nom du groupe de décodeurs XML à appliquer à la source du journal XML. Ce nom doit correspondre exactement au nom du groupe de décodeur XML correspondant spécifié dans le fichier <span class="wintitle"> Log Processing Dataset Include</span> . Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Groupes de décodeur XML</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identifiant de source de journal </td> 
   <td colname="col2"> <p>La valeur de ce champ peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce champ vous permet de différencier les entrées de journal de différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné avec une valeur identifiant la source du journal pour chaque entrée de journal. Par exemple, si vous souhaitez identifier les entrées de journal à partir d’une source de fichier journal nommée XMLFile01, vous pouvez saisir <span class="filepath"> à partir de XMLFile01</span>, et cette chaîne sera transmise au champ x-log-source-id pour chaque entrée de journal provenant de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Champs d’enregistrement des données d’événement</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle de masque </td> 
   <td colname="col2"> <p>Expression régulière avec un seul sous-modèle de capture qui extrait un nom cohérent utilisé pour identifier la source d’une série de fichiers journaux. Seul le nom de fichier est pris en compte. Le chemin et l’extension ne sont pas pris en compte pour la correspondance de l’expression régulière. Si vous ne spécifiez pas de <span class="wintitle"> modèle de masque</span>, un masque est généré automatiquement. </p> <p> Pour les fichiers <span class="filepath"> Logs\010105server1.xml</span> et <span class="filepath"> Logs\010105server2.xml</span>, le modèle de masque serait <code>[0-9]{6}(.*)</code>. Ce modèle extrait la chaîne "server1" ou "server2" des noms de fichiers ci-dessus. </p> <p> Voir <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expressions régulières</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Récursif </td> 
   <td colname="col2"> Vrai ou faux. Si ce paramètre est défini sur true, tous les sous-répertoires de chaque chemin spécifié dans <span class="wintitle"> Chemins du journal</span> sont recherchés dans les fichiers correspondant au modèle de nom de fichier ou de caractère générique spécifié. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeter le fichier </td> 
   <td colname="col2"> Chemin d’accès et nom de fichier du fichier contenant les entrées de journal qui ne répondent pas aux conditions du décodeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser les heures de début/fin </td> 
   <td colname="col2"> <p>Vrai ou faux. Si ce paramètre est défini sur true et que l’heure de début ou l’heure de fin est spécifiée, tous les fichiers de cette source de journal doivent avoir des noms de fichier commençant par des dates au format ISO (YYYMMDD). Chaque fichier contient des données pour un jour GMT (par exemple, la période commençant à 0000 GMT un jour et se terminant à 0000 GMT le jour suivant). Si les noms de fichiers des sources de journaux ne commencent pas par des dates ISO ou si les fichiers contiennent des données qui ne correspondent pas à un jour GMT, ce paramètre doit être défini sur false pour éviter des résultats incorrects. </p> <p> <p>Remarque :  Si les exigences d’attribution de nom et de plage horaire décrites ci-dessus sont respectées pour les fichiers XML et que vous définissez ce paramètre sur true, le groupe de décodeur XML spécifié limite les fichiers lus à ceux dont les noms comportent des dates ISO comprises entre l’heure de début et l’heure de fin spécifiées. Si vous définissez ce paramètre sur false, le serveur Data Workbench lit tous les fichiers XML pendant le traitement du journal pour déterminer les fichiers contenant des données dans les plages Heure de début et Heure de fin. </p> </p> <p> Pour plus d’informations sur les paramètres Heure de début et Heure de fin, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Une fois les sources de données d’un jeu de données définies, ne supprimez pas les sources de journal XML ni ne déplacez-les. Seuls les fichiers XML nouvellement créés doivent être ajoutés au répertoire pour les sources de données.

<!--
AVRO-log-file.xml
-->

Le flux de données Avro offre une méthode plus efficace d’intégration des données dans Data Workbench :

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro fournit un format source unique pour les données de trafic et de commerce.
* Le flux Avro est constitué de données compressées de plusieurs blocs source fournis par jour. Il ne contient que des champs renseignés et fournit des fonctions de surveillance et de notification, l’accès aux données historiques et la récupération automatique.
* Le schéma, une disposition autodéfinie des fichiers journaux Avro, est inclus au début de chaque fichier.
* De nouveaux champs sont ajoutés avec des informations de prise en charge pour ingérer des données de Data Workbench sans aucune modification requise du décodeur. Ces cas comprennent notamment :

   * Evars : 1-250 (auparavant 1-75)
   * Événements personnalisés : 1 à 1 000 (par rapport à 1 à 100)
   * Accès aux variables de solution pour les données mobiles, sociales et vidéo

>[!NOTE]
>
>En outre, l’utilisation du flux Avro permet un accès immédiat à tous les nouveaux champs du flux sans arrêt, ce qui permet de mettre à jour les champs sans nécessiter d’heure de service.

Le flux de données Avro est configuré dans des fichiers distincts :

* Un **fichier journal Avro** : Il s’agit du format de journal Avro généré à partir du décodeur pour formater les données de trafic et de commerce.
* Un **fichier de décodeur Avro** : Ce fichier permet de mapper les valeurs au nouveau format Avro. Vous pouvez configurer le décodeur à l’aide de l’assistant Avro Decoder.

## Assistant de décodage Avro {#section-9a824b4c3d5549e7952a7111232035b2}

Cet assistant configure le fichier journal du décodeur Avro.

Pour ouvrir, cliquez avec le bouton droit dans un espace de travail et sélectionnez **Admin** > **Assistants** > **Assistant Avro Decoder**.

**Étape 1 :** **sélectionnez un fichier journal Avro**.

Au cours de cette étape, vous pouvez sélectionner un fichier source pour le schéma Avro. Les schémas sont accessibles à partir d’un fichier journal (.log) ou d’un fichier de décodeur existant (.avro). Les schémas peuvent être extraits de l’un des fichiers.

| **Fichier journal Avro ** | Cliquez pour ouvrir un fichier journal (.log) afin d’afficher le schéma en haut du fichier journal et de générer le fichier de décodeur. |
|---|---|
| **Fichier de décodage Avro** | Cliquez pour ouvrir et modifier le schéma d’un fichier de décodeur (.avro) existant. |

**Étape 2 : Sélectionnez Input Fields**.

Sélectionnez les champs d&#39;entrée à utiliser dans le jeu de données pour transmettre le traitement du journal. Tous les champs du fichier s’affichent, ce qui vous permet de sélectionner les champs du flux.

>[!NOTE]
>
>Un champ [!DNL x-product(Generates row)] est fourni si un tableau est rencontré dans les données. Ce champ génère de nouvelles lignes pour les données imbriquées d’un tableau en tant que champs d’entrée. Par exemple, si une ligne Accès contient de nombreuses valeurs Product dans un tableau, des lignes sont générées dans le fichier d’entrée pour chaque produit.

| **Sélectionner les valeurs par défaut** | Sélectionnez les champs à identifier comme ensemble standard de champs par défaut . |
|---|---|
| **Sélectionner tout** | Sélectionnez tous les champs du fichier. |
| **Tout désélectionner** | Effacez tous les champs du fichier. |

**Étape 3 : Sélectionnez les champs qui sont copiés pour générer des lignes.**

Comme de nouvelles lignes peuvent être créées à partir de valeurs imbriquées dans un tableau, chaque nouvelle ligne créée doit comporter un identifiant de suivi et un horodatage. Cette étape vous permet de sélectionner les champs à copier dans les lignes de l’enregistrement parent, tels qu’un ID de suivi et un horodatage. Vous pouvez également sélectionner d’autres valeurs à ajouter à chaque ligne.

| **Sélectionner les valeurs par défaut** | Sélectionnez un ensemble standard de champs par défaut qui nécessitent de nouvelles valeurs de colonne ajoutées à chaque ligne, comme un identifiant de suivi et un horodatage. Par exemple, un champ [!DNL hit_source] est une valeur par défaut à ajouter à chaque nouvelle ligne (elle est définie comme valeur par défaut dans la liste). Vous pouvez ajouter d’autres valeurs de colonne à chaque ligne, si nécessaire. |
|---|---|
| **Sélectionner tout** | Sélectionnez tous les champs du fichier. |
| **Tout désélectionner** | Effacez tous les champs du fichier. |

Utilisez la zone **Rechercher** pour rechercher des valeurs dans la liste.

**Étape 4 : spécification du nom du décodeur**

Attribuez un nom au groupe de champs et enregistrez-le en tant que fichier de décodeur. Le nom doit correspondre au nom du groupe de décodeur spécifié dans votre source de journal.

**Étape 5 : Enregistrez le fichier de décodeur.**

Le menu Fichier s’ouvre pour nommer le fichier de décodeur et l’enregistrer sous la forme d’un fichier [!DNL .cfg] dans le dossier **Logs** .
