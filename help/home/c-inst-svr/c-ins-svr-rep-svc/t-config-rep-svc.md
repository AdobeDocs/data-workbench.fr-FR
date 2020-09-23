---
description: Vous devez configurer le ou les serveurs cible Insight pour récupérer les données du Répéteur sur lequel les données du événement d'origine sont stockées.
solution: Analytics
title: Configuration du service de réplication
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---


# Configuration du service de réplication{#configuring-the-replication-service}

Vous devez configurer le ou les serveurs cible Insight pour récupérer les données du Répéteur sur lequel les données du événement d&#39;origine sont stockées.

Pour configurer la récupération des données d’une cible [!DNL Repeater] à une autre [!DNL Insight Server], vous devez modifier le [!DNL Replicate.cfg] fichier fourni dans le dossier [!DNL Components] [!DNL Insight Server(s)] de la cible, comme décrit dans la procédure suivante :

**Pour configurer le[!DNL Replication Service]sur l’ordinateur de cible**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l&#39;icône de la cible [!DNL Insight Server] à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en vue le contenu. Le [!DNL Replicate.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche de la colonne du nom *du* serveur [!DNL Replicate.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Replicate.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Replicate.cfg] fenêtre s&#39;ouvre.
1. Dans la [!DNL Replicate.cfg] fenêtre, cliquez sur **[!UICONTROL Replicate.cfg]**, puis **[!UICONTROL component]** pour en vue le contenu.
1. Modifiez les paramètres à l’aide de l’exemple suivant et du tableau comme guides :

   ![Infos sur l’étape](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Pour ce paramètre... </th> 
      <th colname="col2" class="entry"> Spécifiez les... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Répertoires </td> 
      <td colname="col2"> <p>Répertoires sur le <span class="wintitle"> répéteur</span> qui doivent être copiés (répliqués) sur le serveur <span class="keyword"> cible</span>Insight. Le service <span class="wintitle"></span> de réplication permet la réplication de plusieurs répertoires à partir d'un seul <span class="wintitle"> répéteur</span>. </p> <p>Pour ajouter un nouveau répertoire, cliquez avec le bouton droit sur <span class="uicontrol"> Répertoires</span> et cliquez sur <span class="uicontrol"> Ajouter un nouveau</span> &gt; <span class="uicontrol"> Répertoire</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Aplatir les chemins </td> 
      <td colname="col2"> <p>True ou false. L’action définie par le paramètre de ce paramètre dépend de la définition du paramètre Recursive dans ce fichier : 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Si la valeur Recursive est false, l’option Aplatir les chemins n’a aucun effet. Seuls les fichiers situés au niveau supérieur du répertoire spécifié par le paramètre URI distant sont répliqués. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Si l’option Recursive est définie sur true et que l’option Aplatir les chemins est définie sur false, la structure des répertoires du répertoire distant (<span class="wintitle"> Repeater</span>) est dupliquée exactement dans le chemin d’accès local sur le serveur <span class="keyword"> cible</span>Insight. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Si les chemins récursifs et aplatis sont tous deux vrais, aucun sous-répertoire n’est créé dans le chemin d’accès local. Tous les fichiers de l'arborescence des répertoires distants sont placés au niveau supérieur du répertoire local. </li>
      </ul></p> <p> <p>Remarque : Si les chemins aplatis et les chemins récursifs sont tous deux vrais et que les fichiers des différents sous-répertoires de l'ordinateur distant portent le même nom, le service <span class="wintitle"> de</span> réplication peut s'arrêter ou d'autres comportements non définis peuvent se produire. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Chemin local </td> 
      <td colname="col2">Emplacement de l’enregistrement pour les fichiers récupérés à partir de <span class="wintitle"> Repeater</span>. Le chemin d’accès dépend du répertoire d’installation d’ <span class="keyword"> Insight Server</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rursif </td> 
      <td colname="col2"> True ou false. Si la valeur est false, seuls les fichiers situés au niveau supérieur du répertoire spécifié par le paramètre URI distant sont répliqués. Voir Aplatir les chemins dans ce tableau. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI distant </td> 
      <td colname="col2">URI, y compris un masque de fichier, pour accéder au fichier de stockage de <span class="wintitle"> Repeater</span> . Le fichier <span class="filepath"> Communications.cfg</span> sur le <span class="wintitle"> répéteur</span> doit être configuré de sorte que les données du événement puissent être consultées à l’aide de cet URI. See <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoring Event Data Space</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Serveur </td> 
      <td colname="col2">Paramètres du <span class="wintitle"> répéteur</span> à partir duquel le serveur <span class="keyword"> de cible</span> Insight récupère les fichiers de données de événement. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nom </td> 
      <td colname="col2">Facultatif. Nom permettant d’identifier le <span class="wintitle"> répéteur</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nom commun du serveur SSL </td> 
      <td colname="col2">Obligatoire uniquement si l’option Utiliser SSL est définie sur true. Nom commun du <span class="wintitle"> répéteur</span> sur lequel les données du événement sont stockées. Ce nom doit correspondre au nom commun indiqué dans le certificat de communication de l'ordinateur. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adresse </td> 
      <td colname="col2">Nom d’hôte ou adresse IP numérique du <span class="wintitle"> répéteur</span> sur lequel les données du événement sont stockées. Le nom commun du serveur n’est pas une entrée valide. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Port utilisé pour la transmission des données. Le port par défaut est le port 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificat client SSL </td> 
      <td colname="col2">Obligatoire uniquement si l’option Utiliser SSL est définie sur true. Nom du certificat de licence utilisé pour la connexion au <span class="wintitle"> répéteur</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Utiliser SSL </td> 
      <td colname="col2"> <p>Détermine si SSL est utilisé pour la transmission des données. Les options sont true ou false et la valeur par défaut est false. </p> <p> <p>Remarque : L’utilisation de SSL n’est pas recommandée car elle peut avoir une incidence négative sur les performances. Notez que SSL n'est pas requis à moins que le réseau qui connecte <span class="wintitle"> Repeater</span> aux machines de cible ne soit pas sécurisé. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de fin, Heure de Début </td> 
      <td colname="col2"> <p>(Facultatif) Limite l’ensemble des fichiers de données de événement copiés sur le serveur <span class="keyword"> cible</span> Insight à ceux qui contiennent des données dans la plage définie par l’heure de Début et l’heure de fin. Si l’option Heure de Début est définie, les fichiers de données de événement dans lesquels toutes les entrées de journal proviennent d’une date antérieure à l’heure de début spécifiée ne sont pas copiés. Si l’option Heure de fin est définie, les fichiers de données de événement dans lesquels toutes les entrées de journal de l’heure spécifiée ou ultérieure ne sont pas copiées. Si une partie seulement des données d'un fichier se trouve dans la plage spécifiée, le fichier entier est copié sur l'ordinateur de la cible. </p> <p>L’Adobe recommande d’utiliser l’un des formats suivants pour l’heure : 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1er janvier 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1er janvier 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Remarque : Vous devez spécifier un fuseau horaire. Le fuseau horaire n'est pas défini par défaut sur l'heure système s'il n'est pas spécifié. Si vous souhaitez mettre en oeuvre l’heure d’été ou une stratégie similaire de changement d’horloge, vous devez enregistrer le fichier <span class="filepath"> .dst</span> contenant les règles appropriées sur l’ordinateur Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> . Pour obtenir la liste des abréviations de fuseau horaire prises en charge et des informations sur l’implémentation de l’heure d’été, voir Codes <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"></a>de fuseau horaire. </p> </p> <p> <p>Remarque :  Pour utiliser ces paramètres, les noms des fichiers de données du événement doivent commencer par une date ISO (AAAAMMJJ) et chaque fichier doit contenir des données pour la période de 24 heures commençant à 12 h GMT à cette date. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** de la souris en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Cet exemple illustre comment les fichiers sont copiés si les paramètres Chemins aplatis et Paramètres récursifs sont définis sur true.

Supposons que l’URI distant soit [!DNL /RemoteRoot/] défini et que le chemin d’accès local soit [!DNL E:\LocalRoot\]défini. Sur l’ordinateur distant ( [!DNL Repeater]), les fichiers sont organisés comme suit :

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Une fois la réplication terminée, le répertoire local contient les fichiers suivants :

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Dans le répertoire local, aucun sous-répertoire n&#39;est créé et tous les fichiers de l&#39;arborescence des répertoires distants sont placés au niveau supérieur du répertoire local.

>[!NOTE]
>
>Si les fichiers des différents sous-répertoires de l&#39;ordinateur distant portent le même nom, le [!DNL Replication Service] problème peut s&#39;arrêter ou d&#39;autres comportements non définis peuvent se produire.
