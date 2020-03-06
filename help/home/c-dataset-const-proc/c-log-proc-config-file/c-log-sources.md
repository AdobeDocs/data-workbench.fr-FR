---
description: Les sources de journal sont des fichiers qui contiennent les données à utiliser pour créer un jeu de données.
solution: Analytics
title: Sources de journal
topic: Data workbench
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sources de journal{#log-sources}

Les sources de journal sont des fichiers qui contiennent les données à utiliser pour créer un jeu de données.

Les données disponibles dans les sources du journal sont appelées données d’événement, car chaque enregistrement de données représente un enregistrement de transaction ou une instance unique d’un événement. Le serveur de l’outil de données peut traiter les sources de journaux dérivées des données collectées par [!DNL Sensors] ou extraites d’autres sources de données.

* **Données collectées par [!DNL Sensors]: ** Les données collectées par [!DNL Sensors] les serveurs HTTP et d’applications sont transmises aux serveurs des outils de données, qui convertissent les données en fichiers journaux ( [!DNL .vsl]) fortement compressés. Voir Fichiers [Sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Données extraites par le serveur Insight :** Le serveur de l’outil de données lit les données d’événement contenues dans des fichiers plats, des fichiers XML ou des bases de données conformes ODBC, et utilise ses décodeurs pour extraire les éléments souhaités des données. De telles données d’événement ne doivent pas nécessairement résider dans la mémoire, mais les enregistrements qui contiennent les données doivent inclure un ID de suivi. Voir Fichiers [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)journaux, Sources [de journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)XML et Sources [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)de données ODBC.

**Pour ajouter une source de journal**

1. Ouvrez [!DNL Log Processing.cfg] dans les outils de données.
1. Cliquez avec le bouton droit **[!UICONTROL Log Sources]**, puis cliquez **[!UICONTROL Add New]**.

1. Sélectionnez l’une des options suivantes :

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Les paramètres spécifiques utilisés pour définir un jeu de données varient selon le type de source de journal à utiliser dans le processus de configuration du jeu de données. Spécifiez les paramètres indiqués dans la section correspondant à la source de journal appropriée :

   * [Fichiers du capteur](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [Sources de journal XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [Sources de données ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Après avoir défini la source du journal (et apporté des modifications à d’autres paramètres) dans le [!DNL Log Processing.cfg] fichier, enregistrez le fichier localement et enregistrez-le dans votre profil de jeu de données sur le serveur de l’outil de données.

   >[!NOTE]
   >
   >Un serveur d’outils de données [!DNL File Server Unit] peut recevoir et stocker [!DNL Sensor] des fichiers, des fichiers journaux et des fichiers XML et les transmettre au serveur d’outils de données [!DNL Data Processing Units] qui construit le jeu de données. Voir [Configuration d’une unité](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d)de serveur de fichiers Insight Server.

   Vous pouvez ouvrir la configuration de n’importe quelle source de journal à partir d’une [!DNL Transformation Dependency Map]. Pour plus d’informations sur [!DNL Transformation Dependency Map]cette solution, voir Outils [de configuration des jeux de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)données.

<!--
c_sensor_files.xml
-->

## Conditions {#section-d5901a4872774ad5bd01a18db114f1f2}

Les données d’événement collectées par [!DNL Sensors] les serveurs HTTP et d’applications sont transmises aux serveurs des outils de données, qui convertissent les données en fichiers journaux ( [!DNL .vsl]) fortement compressés. Le format de [!DNL .vsl] fichier est géré par le serveur de l’outil de données et chaque fichier porte le nom du format :

AAAAMMJJ-*SENSORID*.VSL

où AAAAMMJJ est la date du fichier, et *SENSORID* est le nom (attribué par votre organisation) qui indique les données [!DNL Sensor] collectées et transmises au serveur de l&#39;outil de données.

## Paramètres {#section-5c3f1e341c284486aeba3452057da7f3}

Pour [!DNL Sensor] les fichiers, les paramètres suivants sont disponibles :

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
   <td colname="col2"> <p>Répertoires dans lesquels les fichiers <span class="filepath"> .vsl</span> sont stockés. L’emplacement par défaut est le répertoire Journaux. Un chemin relatif fait référence au répertoire d’installation du serveur de l’outil de données. </p> <p>Vous pouvez utiliser des caractères génériques pour spécifier les fichiers <span class="filepath"> .vsl</span> à traiter : 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * correspond à n’importe quel nombre de caractères </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? correspond à un caractère unique </li> 
     </ul> </p> <p> Par exemple, le chemin d'accès au journal <span class="filepath"> Journaux\*.vsl</span> correspond à n'importe quel fichier du répertoire Journaux se terminant par <span class="filepath"> .vsl</span>. Le chemin d'accès au journal <span class="filepath"> Journaux\*-SENSOR?.vsl</span> fait correspondre les fichiers du répertoire Journaux avec une date quelconque (AAAAMMJJ) et un caractère unique après SENSOR, comme dans SENSOR1. </p> <p> Si vous souhaitez rechercher tous les sous-répertoires du chemin d’accès spécifié, vous devez définir le paramètre Recursive sur true. </p> <p> <p>Remarque : Si les fichiers doivent être lus à partir de l’unité <span class="wintitle"> du serveur de fichiers d’un serveur</span>de l’outil de données, vous devez entrer les URI appropriés dans le paramètre Chemins du journal. Par exemple, l’ <span class="filepath"> URI /Logs/*-*.vsl</span> correspond à n’importe quel fichier <span class="filepath"> .vsl</span> dans le répertoire Logs. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité</a>de serveur de fichiers Insight Server. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur de journalisation </td> 
   <td colname="col2">Informations (adresse, nom, port, etc.) nécessaires à la connexion à un serveur de fichiers. S’il existe une entrée dans le paramètre Serveur de journaux, les chemins <span class="wintitle"></span> de journal sont interprétés comme des URI. Sinon, elles sont interprétées comme des chemins locaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité</a>de serveur de fichiers Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID source du journal </td> 
   <td colname="col2"> <p>La valeur de ce paramètre peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce paramètre vous permet de différencier les entrées de journal des différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné par une valeur identifiant la source du journal pour chaque entrée du journal. Par exemple, si vous souhaitez identifier les entrées de journal d’un <span class="wintitle"> Sensor</span> nommé VSensor01, vous pouvez saisir <span class="filepath"> depuis VSensor01</span>et cette chaîne sera transmise au champ x-log-source-id pour chaque entrée de journal provenant de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir Champs <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> d’enregistrement des données d’</a>événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rursif </td> 
   <td colname="col2"> True ou false. Si cette propriété est définie sur true, tous les sous-répertoires de chaque chemin d’accès spécifié dans <span class="wintitle"> Log Paths</span> sont recherchés dans les fichiers correspondant au nom de fichier spécifié ou au modèle de caractères génériques. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser les heures de début/fin </td> 
   <td colname="col2"> <p>True ou false. Si la valeur est définie sur true et que l’heure de début ou l’heure de fin est spécifiée, tous les fichiers de cette source de journal doivent avoir des noms de fichier commençant par des dates au format ISO (AAAAMMJJ). On suppose que chaque fichier contient des données pour un jour GMT (par exemple, la période commençant à 0000 GMT le jour même et se terminant à 0000 GMT le jour suivant). Si les fichiers de sources de journaux contiennent des données qui ne correspondent pas à un jour GMT, ce paramètre doit être défini sur false pour éviter des résultats incorrects. </p> <p> <p>Remarque : Par défaut, <span class="filepath"> les </span>fichiers .vsl contenant les données collectées par <span class="wintitle"> Sensor</span> répondent automatiquement aux exigences de nommage et de plage de temps décrites ci-dessus. Si vous définissez ce paramètre sur true, le serveur de l’outil de données traite toujours les données des fichiers dont les noms incluent des dates ISO comprises entre l’heure de début et l’heure de fin spécifiées. Si vous définissez ce paramètre sur false, le serveur de l’outil de données lit tous les fichiers <span class="filepath"> .vsl</span> pendant le traitement du journal pour déterminer les fichiers qui contiennent des données dans la plage Heure de début et Heure de fin. </p> </p> <p> Pour plus d’informations sur les paramètres Heure de début et Heure de fin, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres</a>de données. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>N’utilisez pas les paramètres de configuration des sources de [!DNL Sensor] données pour déterminer les entrées de journal d’un fichier journal qui doivent être incluses dans un jeu de données. Configurez plutôt la source de données pour qu’elle pointe vers tous les fichiers journaux d’un répertoire. Utilisez ensuite les paramètres Heure de début et Heure de fin de pour [!DNL Log Processing.cfg] déterminer les entrées de journal à utiliser pour construire le jeu de données. Voir Filtres [de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

Le fichier contenant les données d’événement doit répondre aux exigences suivantes :

* Chaque enregistrement de données d’événement dans le fichier doit être représenté par une ligne.
* Les champs d’un enregistrement doivent être séparés, qu’ils soient vides ou non, par un délimiteur ASCII. Le serveur de l’outil de données n’exige pas que vous utilisiez un délimiteur spécifique. Vous pouvez utiliser n’importe quel caractère qui n’est pas un caractère de fin de ligne et n’apparaît nulle part dans les données d’événement proprement dites.
* Chaque enregistrement du fichier doit contenir :

   * Un ID de suivi
   * Horodatage

* Pour spécifier les heures de début et de fin du traitement des données, chaque nom de fichier doit se présenter sous la forme suivante :

   * [!DNL YYYYMMDD-SOURCE.log]
   où *AAAAMMJJ* est le jour GMT (Heure de Greenwich) de toutes les données du fichier, et *SOURCE* est une variable identifiant la source des données contenues dans le fichier.

   >[!NOTE]
   >
   >Contactez les services de conseil Adobe pour obtenir une révision des fichiers journaux que vous prévoyez d’incorporer dans le jeu de données.

## Paramètres {#section-83a861ac24954d54bbb9530e4d8bf23c}

Pour les sources de journaux des fichiers journaux, les paramètres du tableau suivant sont disponibles.

>[!NOTE]
>
>Le traitement des sources de journaux de fichiers journaux requiert des paramètres supplémentaires définis dans un [!DNL Log Processing Dataset Include] fichier, qui contient un sous-ensemble des paramètres inclus dans un [!DNL Log Processing.cfg] fichier, ainsi que des paramètres spéciaux pour la définition de décodeurs pour l&#39;extraction de données du fichier journal. Pour plus d’informations sur la définition de décodeurs pour les sources de journaux de fichiers journaux, voir Groupes [de décodeurs de fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd)texte.

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
   <td colname="col2"> Identifiant de la source du fichier journal. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chemins du journal </td> 
   <td colname="col2"> <p>Répertoires dans lesquels les fichiers journaux sont stockés. L’emplacement par défaut est le répertoire Journaux. Un chemin relatif fait référence au répertoire d’installation du serveur de l’outil de données. </p> <p> Vous pouvez utiliser des caractères génériques pour spécifier les fichiers journaux à traiter : 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * correspond à n’importe quel nombre de caractères. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? correspond à un caractère unique. </li> 
     </ul> </p> <p> Par exemple, le chemin d'accès au journal <span class="filepath"> Journaux\*.log</span> correspond à tout fichier du répertoire Journaux se terminant par <span class="filepath"> .log</span>. </p> <p> Si vous souhaitez rechercher tous les sous-répertoires du chemin d’accès spécifié, vous devez définir le paramètre Recursive sur true. </p> <p> Si les fichiers doivent être lus à partir de l’unité <span class="wintitle"> du serveur de fichiers d’un serveur</span>de l’outil de données, vous devez entrer les URI appropriés dans le paramètre Chemins du journal. Par exemple, <span class="filepath"> URI/Logs/*.log</span> correspond à n’importe quel <span class="filepath"> fichier .log</span> du répertoire Logs. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité</a>de serveur de fichiers Insight Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur de journalisation </td> 
   <td colname="col2"> Informations (adresse, nom, port, etc.) nécessaires à la connexion à un serveur de fichiers. S’il existe une entrée dans le paramètre Serveur de journaux, les chemins <span class="wintitle"></span> de journal sont interprétés comme des URI. Sinon, elles sont interprétées comme des chemins locaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité</a>de serveur de fichiers Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressé </td> 
   <td colname="col2"> True ou false. Cette valeur doit être définie sur true si les fichiers journaux à lire par le serveur de l’outil de données sont des fichiers gzip compressés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de décodeurs </td> 
   <td colname="col2"> nom du groupe de décodeurs de fichiers texte à appliquer à la source du journal des fichiers journaux. Ce nom doit correspondre exactement au nom du groupe de décodeurs de fichiers texte correspondant spécifié dans le fichier Inclure <span class="wintitle"> le jeu de données de traitement du</span> journal. Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Groupes</a>de décodeurs de fichiers texte. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID source du journal </td> 
   <td colname="col2"> <p>La valeur de ce paramètre peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce paramètre vous permet de différencier les entrées de journal des différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné par une valeur identifiant la source du journal pour chaque entrée du journal. Par exemple, si vous souhaitez identifier les entrées de journal d’une source de fichier journal nommée LogFile01, vous pouvez saisir <span class="filepath"> depuis LogFile01</span>, et cette chaîne sera transmise au champ x-log-source-id pour chaque entrée de journal de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir Champs <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> d’enregistrement des données d’</a>événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle de masque </td> 
   <td colname="col2"> <p>Expression régulière avec un seul sous-modèle capturant qui extrait un nom cohérent utilisé pour identifier la source d’une série de fichiers journaux. Seul le nom de fichier est pris en compte. Le chemin et l’extension ne sont pas pris en compte pour la correspondance de l’expression régulière. Si vous ne spécifiez pas de modèle <span class="wintitle"> de</span>masque, un masque est généré automatiquement. </p> <p> Pour les fichiers <span class="filepath"> \010105server1.log</span> et <span class="filepath"> Logs\010105server2.log</span>, le modèle <span class="wintitle"></span> de masque serait [0-9]{6}(.*). Ce modèle extrait la chaîne "server1" ou "server2" des noms de fichier ci-dessus. </p> <p> Voir Expressions <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"></a>régulières. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rursif </td> 
   <td colname="col2"> True ou false. Si ce paramètre est défini sur true, tous les sous-répertoires de chaque chemin d’accès spécifié dans Chemins <span class="wintitle"></span> du journal sont recherchés pour les fichiers correspondant au nom de fichier spécifié ou au modèle de caractères génériques. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeter le fichier </td> 
   <td colname="col2"> chemin d’accès et nom de fichier du fichier contenant les entrées du journal qui ne remplissent pas les conditions du décodeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser les heures de début/fin </td> 
   <td colname="col2"> <p>True ou false. Si ce paramètre est défini sur true et que l’heure de début ou l’heure de fin est spécifiée, tous les fichiers de cette source de journal doivent avoir des noms de fichier commençant par des dates au format ISO (AAAAMMJJ). On suppose que chaque fichier contient des données pour un jour GMT (par exemple, la période commençant à 0000 GMT le jour même et se terminant à 0000 GMT le jour suivant). Si les noms des fichiers de sources de journaux ne commencent pas par des dates ISO ou si les fichiers contiennent des données qui ne correspondent pas à un jour GMT, ce paramètre doit être défini sur false pour éviter des résultats incorrects. </p> <p> <p>Remarque :  Si les exigences de nommage et de plage de temps décrites ci-dessus sont satisfaites pour les fichiers journaux et que vous définissez ce paramètre sur true, le groupe de décodeurs de fichiers texte spécifié limite les fichiers lus à ceux dont les noms comportent des dates ISO comprises entre l’heure de début et l’heure de fin spécifiées. Si vous définissez ce paramètre sur false, le serveur de l’outil de données lit tous les fichiers journaux pendant le traitement du journal pour déterminer les fichiers qui contiennent des données dans la plage Heure de début et Heure de fin. </p> </p> <p> Pour plus d’informations sur les paramètres Heure de début et Heure de fin, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres</a>de données. </p> </td> 
  </tr> 
 </tbody> 
</table>

Dans cet exemple, le jeu de données est construit à partir de deux types de sources de journal.

La source de journal 0 spécifie les fichiers journaux générés à partir des données d&#39;événement capturées par [!DNL Sensor]. Cette source de données pointe vers un répertoire appelé Journaux et vers tous les fichiers de ce répertoire avec une extension de nom de [!DNL .vsl] fichier.

Source du journal 1 pointe vers tous les fichiers du répertoire Journaux avec une extension de nom de [!DNL .txt] fichier. Le groupe de décodeurs pour cette source de journal est appelé &quot;Journaux de texte&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Vous ne devez pas supprimer ni déplacer les fichiers journaux une fois que les sources de données d’un jeu de données ont été définies. Seuls les fichiers journaux nouvellement créés doivent être ajoutés au répertoire des sources de données.

<!--
c_xml_log_sources.xml
-->

Le fichier contenant les données d’événement doit répondre aux exigences suivantes :

* Les données d’événement doivent être incluses dans un fichier XML correctement formaté avec les relations parent-enfant appropriées.
* Un groupe de décodeurs unique doit exister pour chaque format de fichier XML. Pour plus d’informations sur la création d’un groupe de décodeurs, voir Groupes [de décodeurs](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)XML.
* Chaque enregistrement de visiteur dans le fichier doit contenir :

   * Un ID de suivi
   * Horodatage

* Pour spécifier les heures de début et de fin du traitement des données, chaque nom de fichier doit se présenter sous la forme

[!DNL YYYYMMDD-SOURCE.log]

où *AAAAMMJJ* est le jour GMT (Heure de Greenwich) de toutes les données du fichier, et *SOURCE* est une variable identifiant la source des données contenues dans le fichier.

Pour obtenir un exemple de fichier XML répondant à ces exigences, voir Groupes [de décodeurs](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)XML.

>[!NOTE]
>
>Contactez les services de conseil Adobe pour obtenir une révision des fichiers journaux XML que vous prévoyez d’incorporer dans le jeu de données.

## Paramètres {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Pour les sources de journaux XML, les paramètres du tableau suivant sont disponibles.

>[!NOTE]
>
>Le traitement des sources de journaux XML requiert des paramètres supplémentaires définis dans un [!DNL Log Processing Dataset Include] fichier, qui contient un sous-ensemble des paramètres inclus dans un [!DNL Log Processing.cfg] fichier, ainsi que des paramètres spéciaux pour la définition de décodeurs pour l’extraction de données du fichier XML. Pour plus d’informations sur la définition de décodeurs pour les sources de journaux XML, voir Groupes [de décodeurs](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)XML.

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
   <td colname="col2"> Identifiant de la source du journal XML. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chemins du journal </td> 
   <td colname="col2"> <p>Répertoires dans lesquels sont stockées les sources du journal XML. L’emplacement par défaut est le répertoire Journaux. Un chemin relatif fait référence au répertoire d’installation du serveur de l’outil de données. </p> <p> Vous pouvez utiliser des caractères génériques pour spécifier les sources de journaux XML à traiter : 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * correspond à n’importe quel nombre de caractères </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? correspond à un caractère unique </li> 
     </ul> </p> <p>Par exemple, le chemin d’accès au journal <span class="filepath"> Journaux\*.xml</span> correspond à n’importe quel fichier du répertoire Journaux se terminant par <span class="filepath"> .xml</span>. </p> <p> Si vous souhaitez rechercher tous les sous-répertoires du chemin d’accès spécifié, vous devez définir le champ <span class="wintitle"> Récursif</span> sur true. </p> <p> <p>Remarque : Si les fichiers doivent être lus à partir de l’unité <span class="wintitle"> du serveur de fichiers d’un serveur</span>de données Workbench, vous devez saisir l’URI approprié dans le champ Chemins <span class="wintitle"> du</span> journal. Par exemple, <span class="filepath"> URI/Logs/*.xml</span> correspond à n’importe quel fichier <span class="filepath"> .xml</span> du répertoire Logs. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité</a>de serveur de fichiers Insight Server. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur de journalisation </td> 
   <td colname="col2"> Informations (adresse, nom, port, etc.) nécessaires à la connexion à un serveur de fichiers. S’il existe une entrée dans le champ Serveur <span class="wintitle"> de journal, les chemins</span> de <span class="wintitle"></span> journal sont interprétés comme des URI. Sinon, elles sont interprétées comme des chemins locaux. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuration d’une unité</a>de serveur de fichiers Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressé </td> 
   <td colname="col2"> True ou false. Cette valeur doit être définie sur true si les sources du journal XML à lire par le serveur de l’outil de données sont des fichiers gzip compressés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de décodeurs </td> 
   <td colname="col2"> Nom du groupe de décodeurs XML à appliquer à la source du journal XML. Ce nom doit correspondre exactement au nom du groupe de décodeurs XML correspondant spécifié dans le fichier <span class="wintitle"> Log Processing Dataset Include</span> . Voir Groupes <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> de décodeurs</a>XML. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID source du journal </td> 
   <td colname="col2"> <p>La valeur de ce champ peut être n’importe quelle chaîne. Si une valeur est spécifiée, ce champ vous permet de différencier les entrées de journal des différentes sources de journal pour l’identification de la source ou le traitement ciblé. Le champ x-log-source-id est renseigné par une valeur identifiant la source du journal pour chaque entrée du journal. Si, par exemple, vous souhaitez identifier les entrées de journal d’une source de fichier journal nommée XMLFile01, vous pouvez saisir <span class="filepath"> des données de XMLFile01</span>et cette chaîne sera transmise au champ x-log-source-id pour chaque entrée de journal de cette source. </p> <p> Pour plus d’informations sur le champ x-log-source-id, voir Champs <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> d’enregistrement des données d’</a>événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle de masque </td> 
   <td colname="col2"> <p>Expression régulière avec un seul sous-modèle capturant qui extrait un nom cohérent utilisé pour identifier la source d’une série de fichiers journaux. Seul le nom de fichier est pris en compte. Le chemin et l’extension ne sont pas pris en compte pour la correspondance de l’expression régulière. Si vous ne spécifiez pas de modèle <span class="wintitle"> de</span>masque, un masque est généré automatiquement. </p> <p> Pour les fichiers <span class="filepath"> \010105server1.xml</span> et <span class="filepath"> Logs\010105server2.xml</span>, le modèle de masque serait [0-9]{6}(.*). Ce modèle extrait la chaîne "server1" ou "server2" des noms de fichier ci-dessus. </p> <p> Voir Expressions <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"></a>régulières. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rursif </td> 
   <td colname="col2"> True ou false. Si ce paramètre est défini sur true, tous les sous-répertoires de chaque chemin d’accès spécifié dans Chemins <span class="wintitle"></span> du journal sont recherchés pour les fichiers correspondant au nom de fichier spécifié ou au modèle de caractères génériques. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeter le fichier </td> 
   <td colname="col2"> chemin d’accès et nom de fichier du fichier contenant les entrées du journal qui ne remplissent pas les conditions du décodeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser les heures de début/fin </td> 
   <td colname="col2"> <p>True ou false. Si ce paramètre est défini sur true et que l’heure de début ou l’heure de fin est spécifiée, tous les fichiers de cette source de journal doivent avoir des noms de fichier commençant par des dates au format ISO (AAAAMMJJ). On suppose que chaque fichier contient des données pour un jour GMT (par exemple, la période commençant à 0000 GMT le jour même et se terminant à 0000 GMT le jour suivant). Si les noms des fichiers de sources de journaux ne commencent pas par des dates ISO ou si les fichiers contiennent des données qui ne correspondent pas à un jour GMT, ce paramètre doit être défini sur false pour éviter des résultats incorrects. </p> <p> <p>Remarque :  Si les exigences de nommage et de plage de temps décrites ci-dessus sont satisfaites pour les fichiers XML et que vous définissez ce paramètre sur true, le groupe de décodeurs XML spécifié limite les fichiers lus à ceux dont les noms comportent des dates ISO comprises entre l’heure de début et l’heure de fin spécifiées. Si vous définissez ce paramètre sur false, le serveur de l’outil de données lit tous les fichiers XML pendant le traitement du journal afin de déterminer quels fichiers contiennent des données dans la plage Heure de début et Heure de fin. </p> </p> <p> Pour plus d’informations sur les paramètres Heure de début et Heure de fin, voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres</a>de données. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Vous ne devez pas supprimer ni déplacer les sources de journaux XML une fois que les sources de données d’un jeu de données ont été définies. Seuls les fichiers XML nouvellement créés doivent être ajoutés au répertoire des sources de données.

<!--
AVRO-log-file.xml
-->

Le flux de données Avro fournit une méthode plus efficace d’intégration des données dans les outils de données :

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro fournit un format source unique pour les données de trafic et de commerce.
* Le flux Avro est constitué de données compressées de plusieurs blocs source fournis par jour. Il ne contient que des champs renseignés et fournit des fonctionnalités de surveillance et de notification, l’accès aux données historiques et la récupération automatique.
* Le schéma, une disposition auto-définie des fichiers journaux Avro, est inclus au début de chaque fichier.
* De nouveaux champs sont ajoutés avec les informations de prise en charge pour assimiler les données des outils de données sans aucune modification requise du décodeur. Notamment : 

   * eVars : 1-250 (auparavant : 1-75)
   * Evénements personnalisés : 1-1000 (par rapport à 1-100)
   * Accès aux variables de solution pour les données mobiles, sociales et vidéo

>[!NOTE]
>
>En outre, l’utilisation du flux Avro permet d’accéder immédiatement à tous les nouveaux champs du flux sans arrêt, ce qui permet de mettre à jour les champs sans nécessiter d’heure de service.

Le flux de données Avro est configuré dans des fichiers distincts :

* Un fichier **journal** Avro : Il s’agit du format de journal Avro généré à partir du décodeur pour formater les données de trafic et de commerce.
* Un fichier **de décodage** Avro : Ce fichier vous permet de mapper des valeurs dans le nouveau format Avro. Vous pouvez configurer le décodeur à l’aide de l’assistant Avro Decoder.

## Avro Decoder Wizard {#section-9a824b4c3d5549e7952a7111232035b2}

Cet assistant configure le fichier journal du décodeur Avro.

Pour ouvrir, cliquez avec le bouton droit de la souris dans un espace de travail et sélectionnez **Admin** > **Assistants** > **Avro Decoder Wizard**.

**Étape 1 :** **Sélectionnez un fichier** journal Avro.

Au cours de cette étape, vous pouvez sélectionner un fichier source pour le schéma Avro. Les schémas sont accessibles à partir d’un fichier journal (.log) ou d’un fichier de décodeur existant (.avro). Les schémas peuvent être extraits de l’un ou l’autre des fichiers.

| **Fichier journal Avro ** | Cliquez sur pour ouvrir un fichier journal (.log) afin d’afficher le schéma en haut du fichier journal et de générer le fichier décodeur. |
|---|---|
| **Fichier de décodeur Avro** | Cliquez sur pour ouvrir et modifier le schéma d’un fichier de décodeur (.avro) existant. |

**Étape 2 : Sélectionnez Champs** de saisie.

Sélectionnez les champs d’entrée à utiliser dans le jeu de données pour passer par le traitement du journal. Tous les champs du fichier s’affichent, ce qui vous permet de sélectionner les champs du flux.

>[!NOTE]
>
>Un [!DNL x-product(Generates row)] champ est fourni si un tableau est détecté dans les données. Ce champ génère de nouvelles lignes pour les données imbriquées dans un tableau en tant que champs d’entrée. Si, par exemple, vous avez une ligne Accès avec de nombreuses valeurs de produit dans un tableau, des lignes sont générées dans le fichier d’entrée pour chaque produit.

| **Sélectionner les valeurs par défaut** | Sélectionnez les champs à identifier comme jeu standard de champs par défaut. |
|---|---|
| **Sélectionner tout** | Sélectionnez tous les champs du fichier. |
| **Tout désélectionner** | Effacez tous les champs du fichier. |

**Étape 3 : Sélectionnez les champs qui sont copiés pour générer des lignes.**

Comme de nouvelles lignes peuvent être créées à partir de valeurs imbriquées dans un tableau, chaque nouvelle ligne créée doit avoir un ID de suivi et un horodatage. Cette étape vous permet de sélectionner les champs à copier vers des lignes à partir de l’enregistrement parent, comme un ID de suivi et un horodatage. Vous pouvez également sélectionner d’autres valeurs à ajouter à chaque ligne.

| **Sélectionner les valeurs par défaut** | Sélectionnez un ensemble standard de champs par défaut nécessitant l’ajout de nouvelles valeurs de colonne à chaque ligne, comme un ID de suivi et un horodatage. Par exemple, un [!DNL hit_source] champ est une valeur par défaut devant être ajoutée à chaque nouvelle ligne (elle est définie comme valeur par défaut dans la liste). Vous pouvez ajouter d’autres valeurs de colonne à chaque ligne, le cas échéant. |
|---|---|
| **Sélectionner tout** | Sélectionnez tous les champs du fichier. |
| **Tout désélectionner** | Effacez tous les champs du fichier. |

Utilisez la zone **Rechercher** pour rechercher des valeurs dans la liste.

**Etape 4 : spécification du nom du décodeur**

Attribuez un nom au groupe de champs et enregistrez-le en tant que fichier de décodeur. Le nom doit correspondre au nom du groupe Decoder spécifié dans votre source de journal.

**Étape 5 : Enregistrez le fichier de décodeur.**

Le menu Fichier s’ouvre pour nommer le fichier décodeur et l’enregistrer en tant que [!DNL .cfg] fichier dans le dossier **Journaux** .
