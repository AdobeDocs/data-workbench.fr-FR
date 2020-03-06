---
description: Vous devez configurer le ou les serveurs Target Insight pour récupérer les données du répéteur sur lequel les données d’événement d’origine sont stockées.
solution: Insight
title: Configuration du service de réplication
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration du service de réplication{#configuring-the-replication-service}

Vous devez configurer le ou les serveurs Target Insight pour récupérer les données du répéteur sur lequel les données d’événement d’origine sont stockées.

Pour configurer la récupération des données d’une cible [!DNL Repeater] vers une cible [!DNL Insight Server], vous devez modifier le [!DNL Replicate.cfg] fichier fourni dans le [!DNL Components] dossier sur la cible [!DNL Insight Server(s)] comme décrit dans la procédure suivante :

**Pour configurer le[!DNL Replication Service]sur l’ordinateur cible**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône de la cible [!DNL Insight Server] à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Replicate.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur [!DNL Replicate.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Replicate.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Replicate.cfg] fenêtre s&#39;ouvre.
1. Dans la [!DNL Replicate.cfg] fenêtre, cliquez sur **[!UICONTROL Replicate.cfg]**, puis **[!UICONTROL component]** affichez son contenu.
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
      <td colname="col2"> <p>Les répertoires du <span class="wintitle"> Répéteur</span> qui doivent être copiés (répliqués) sur le serveur <span class="keyword"> Insight cible</span>. Le service <span class="wintitle"> de</span> réplication permet la réplication de plusieurs répertoires à partir d’un seul <span class="wintitle"> répéteur</span>. </p> <p>Pour ajouter un nouveau répertoire, cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Répertoires</span> et cliquez sur <span class="uicontrol"> Ajouter un nouveau</span> &gt; <span class="uicontrol"> Répertoire</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Aplatir les chemins </td> 
      <td colname="col2"> <p>True ou false. L’action définie par le paramètre de ce paramètre dépend de la définition du paramètre récursif dans ce fichier : 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Si l’option Récursive est définie sur false, l’option Aplatir les chemins n’a aucun effet. Seuls les fichiers du niveau supérieur du répertoire spécifié par le paramètre URI distant sont répliqués. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Si l’option Récursive est définie sur true et que l’option Aplatir les chemins est définie sur false, la structure de répertoires du répertoire distant (<span class="wintitle"> Repeater</span>) est dupliquée exactement dans le chemin local sur le serveur <span class="keyword"> cible</span>Insight. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Si les chemins récursifs et aplatis sont tous deux vrais, aucun sous-répertoire n’est créé dans le chemin d’accès local. Tous les fichiers de l’arborescence du répertoire distant sont placés au niveau supérieur du répertoire local. </li>
      </ul></p> <p> <p>Remarque : Si les chemins aplatis et récursifs sont tous deux vrais et que les fichiers des différents sous-répertoires de l'ordinateur distant portent le même nom, le service <span class="wintitle"></span> de réplication peut s'arrêter ou un autre comportement non défini peut se produire. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Chemin local </td> 
      <td colname="col2">Emplacement de stockage des fichiers récupérés à partir de <span class="wintitle"> Repeater</span>. Le chemin d’accès est relatif au répertoire d’installation du serveur <span class="keyword"></span> Insight. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rursif </td> 
      <td colname="col2"> True ou false. Si la valeur est false, seuls les fichiers situés au niveau supérieur du répertoire spécifié par le paramètre URI distant sont répliqués. Voir Aplatissement des chemins dans ce tableau. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI distant </td> 
      <td colname="col2">URI, y compris un masque de fichier, pour accéder au magasin de fichiers de <span class="wintitle"> Repeater</span> . Le fichier <span class="filepath"> Communications.cfg</span> sur le <span class="wintitle"> répéteur</span> doit être configuré de manière à ce que les données d’événement soient accessibles à l’aide de cet URI. Voir <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Surveillance de l’espace</a>de données d’événement. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Serveur </td> 
      <td colname="col2">Paramètres du <span class="wintitle"> répéteur</span> à partir duquel le serveur <span class="keyword"> cible</span> Insight récupère les fichiers de données d’événement. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nom </td> 
      <td colname="col2">Facultatif. Nom permettant d’identifier le <span class="wintitle"> répéteur</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nom commun du serveur SSL </td> 
      <td colname="col2">Obligatoire uniquement si Use SSL est défini sur true. Nom commun du <span class="wintitle"> répéteur</span> sur lequel les données d’événement sont stockées. Ce nom doit correspondre au nom commun indiqué dans le certificat de communication de l'ordinateur. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adresse </td> 
      <td colname="col2">Nom d’hôte ou adresse IP numérique du <span class="wintitle"> répéteur</span> sur lequel les données d’événement sont stockées. Le nom commun du serveur n’est pas une entrée valide. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Port utilisé pour la transmission des données. Le port par défaut est le port 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificat client SSL </td> 
      <td colname="col2">Obligatoire uniquement si Use SSL est défini sur true. Nom du certificat de licence utilisé pour la connexion au <span class="wintitle"> répéteur</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Utiliser SSL </td> 
      <td colname="col2"> <p>Détermine si SSL est utilisé pour la transmission des données. Les options sont true ou false et la valeur par défaut est false. </p> <p> <p>Remarque : L’utilisation de SSL n’est pas recommandée, car elle peut avoir une incidence négative sur les performances. Notez que SSL n’est pas requis, sauf si le réseau qui connecte <span class="wintitle"> Repeater</span> aux ordinateurs cible n’est pas sécurisé. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de fin, Heure de début </td> 
      <td colname="col2"> <p>(Facultatif) Limite l’ensemble des fichiers de données d’événement copiés sur le serveur <span class="keyword"></span> d’aperçu cible à ceux qui contiennent des données dans la plage définie par Heure de début et Heure de fin. Si l’option Heure de début est définie, les fichiers de données d’événement dans lesquels toutes les entrées du journal proviennent d’une date antérieure à l’heure de début spécifiée ne sont pas copiés. Si l’option Heure de fin est définie, les fichiers de données d’événement dans lesquels toutes les entrées du journal à partir de l’heure spécifiée ou ultérieure ne sont pas copiées. Si seule une partie des données d’un fichier se trouve dans la plage spécifiée, le fichier entier est copié sur l’ordinateur cible. </p> <p>Adobe recommande d’utiliser l’un des formats suivants pour l’instant : 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1er janvier 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1er janvier 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Remarque : Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur l’heure du système s’il n’est pas spécifié. Si vous souhaitez mettre en oeuvre l’heure d’été ou une stratégie similaire de changement d’horloge, vous devez enregistrer le fichier <span class="filepath"> .dst</span> contenant les règles appropriées sur l’Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> . Pour obtenir la liste des abréviations de fuseau horaire prises en charge et des informations sur la mise en oeuvre de l’heure d’été, voir Codes <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"></a>de fuseau horaire. </p> </p> <p> <p>Remarque :  Pour utiliser ces paramètres, les noms des fichiers de données d’événement doivent commencer par une date ISO (AAAAMMJJ) et chaque fichier doit contenir des données pour la période de 24 heures commençant à 12 heures GMT à cette date. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Cet exemple illustre la manière dont les fichiers sont copiés si les paramètres Aplatir les chemins et Récursif sont définis sur true.

Supposons que l’URI distant soit [!DNL /RemoteRoot/] et que le chemin d’accès local soit [!DNL E:\LocalRoot\]. Sur l’ordinateur distant ( [!DNL Repeater]), les fichiers sont organisés comme suit :

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Une fois la réplication terminée, le répertoire local contient les fichiers suivants :

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Dans le répertoire local, aucun sous-répertoire n’est créé et tous les fichiers de l’arborescence des répertoires distants sont placés au niveau supérieur du répertoire local.

>[!NOTE]
>
>Si les fichiers des différents sous-répertoires de l&#39;ordinateur distant portent le même nom, cela [!DNL Replication Service] peut se produire ou si d&#39;autres comportements non définis peuvent se produire.
