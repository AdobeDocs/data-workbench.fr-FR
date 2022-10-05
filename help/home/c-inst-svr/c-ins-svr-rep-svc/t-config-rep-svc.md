---
description: Vous devez configurer le ou les serveurs Insight cibles pour récupérer les données du Répéteur sur lequel les données d’événement d’origine sont stockées.
title: Configuration du service de réplication
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Configuration du service de réplication{#configuring-the-replication-service}

{{eol}}

Vous devez configurer le ou les serveurs Insight cibles pour récupérer les données du Répéteur sur lequel les données d’événement d’origine sont stockées.

Pour configurer la récupération des données à partir d’un [!DNL Repeater] à une cible [!DNL Insight Server], vous devez modifier la variable [!DNL Replicate.cfg] fourni dans la variable [!DNL Components] dossier sur la cible [!DNL Insight Server(s)] comme décrit dans la procédure suivante :

**Pour configurer la variable [!DNL Replication Service] sur la machine cible**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l&#39;icône de la cible. [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Replicate.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Replicate.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Replicate.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Le [!DNL Replicate.cfg] s’ouvre.
1. Dans le [!DNL Replicate.cfg] fenêtre, cliquez sur **[!UICONTROL Replicate.cfg]**, puis **[!UICONTROL component]** pour afficher son contenu.
1. Editez les paramètres à partir de l&#39;exemple suivant et du tableau comme guides :

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
      <td colname="col2"> <p>Les répertoires du <span class="wintitle"> Répéteur</span> qui doivent être copiés (répliqués) vers la cible <span class="keyword"> Serveur Insight</span>. Le <span class="wintitle"> Service de réplication</span> permet la réplication de plusieurs répertoires à partir d’une seule <span class="wintitle"> Répéteur</span>. </p> <p>Pour ajouter un nouveau répertoire, cliquez avec le bouton droit de la souris <span class="uicontrol"> Répertoires</span> et cliquez sur <span class="uicontrol"> Ajouter</span> &gt; <span class="uicontrol"> Répertoire</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Aplatissement des chemins </td> 
      <td colname="col2"> <p>True ou false. L’action définie par le paramètre de ce paramètre dépend du paramètre Récursif de ce fichier : 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Si l’option Récursif est définie sur false, l’option Aplatir les chemins n’a aucun effet. Seuls les fichiers situés au niveau supérieur du répertoire spécifié par le paramètre URI distant sont répliqués. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Si l’option Récursif est définie sur true et que l’option Aplatir les chemins est définie sur false, la structure de répertoires du fichier distant (<span class="wintitle"> Répéteur</span>) est dupliqué exactement dans le chemin d’accès local sur la cible. <span class="keyword"> Serveur Insight</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Si les chemins récursifs et aplatis sont tous deux vrais, aucun sous-répertoire n’est créé dans le chemin d’accès local. À la place, tous les fichiers de l’arborescence de répertoires distants sont placés au niveau supérieur du répertoire local. </li>
      </ul></p> <p> <p>Remarque : Si les chemins d’accès aplati et récursifs sont tous deux vrais et que les fichiers des différents sous-répertoires de la machine distante portent le même nom, la variable <span class="wintitle"> Service de réplication</span> peut s’arrêter ou tout autre comportement non défini peut se produire. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Chemin local </td> 
      <td colname="col2">L’emplacement de stockage des fichiers récupérés à partir de <span class="wintitle"> Répéteur</span>. Le chemin d’accès est relatif à la propriété <span class="keyword"> Serveur Insight</span> répertoire d’installation. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Récursif </td> 
      <td colname="col2"> True ou false. Si la valeur est false, seuls les fichiers situés au niveau supérieur du répertoire spécifié par le paramètre URI distant sont répliqués. Voir Aplatir les chemins dans ce tableau. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI distant </td> 
      <td colname="col2">L’URI, y compris un masque de fichier, pour accéder au <span class="wintitle"> Répéteur</span> entrepôt de fichiers. Le <span class="filepath"> Communications.cfg</span> sur le <span class="wintitle"> Répéteur</span> doit être configuré de sorte que les données d’événement soient accessibles à l’aide de cet URI. Voir <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Surveillance de l’espace des données d’événement</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Serveur </td> 
      <td colname="col2">Paramètres de la variable <span class="wintitle"> Répéteur</span> à partir de laquelle la cible <span class="keyword"> Serveur Insight</span> récupère les fichiers de données d’événement. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nom </td> 
      <td colname="col2">Facultatif. Nom permettant d’identifier la variable <span class="wintitle"> Répéteur</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nom commun du serveur SSL </td> 
      <td colname="col2">Obligatoire uniquement si l’option Use SSL est définie sur true. Nom commun de la variable <span class="wintitle"> Répéteur</span> sur laquelle les données d’événement sont stockées. Ce nom doit correspondre au nom commun répertorié dans le certificat de communication de la machine. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adresse </td> 
      <td colname="col2">Nom d’hôte ou adresse IP numérique de la variable <span class="wintitle"> Répéteur</span> sur laquelle les données d’événement sont stockées. Le nom commun du serveur n’est pas une entrée valide. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Port utilisé pour la transmission des données. Le port par défaut est le port 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificat client SSL </td> 
      <td colname="col2">Obligatoire uniquement si l’option Use SSL est définie sur true. Nom du certificat de licence utilisé pour se connecter à la variable <span class="wintitle"> Répéteur</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Utiliser SSL </td> 
      <td colname="col2"> <p>Détermine si SSL est utilisé pour la transmission des données. Les options sont true ou false, et la valeur par défaut est false. </p> <p> <p>Remarque : L’utilisation de SSL n’est pas recommandée, car elle peut avoir une incidence négative sur les performances. Notez que SSL n’est pas requis, sauf si le réseau se connecte au <span class="wintitle"> Répéteur</span> aux machines cibles n’est pas sécurisé. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de fin, Heure de début </td> 
      <td colname="col2"> <p>(Facultatif) Limite l’ensemble des fichiers de données d’événement copiés dans la cible <span class="keyword"> Serveur Insight</span> à ceux qui contiennent des données dans la plage définie par Heure de début et Heure de fin. Si l’heure de début est définie, les fichiers de données d’événement dans lesquels toutes les entrées de journal sont antérieures à l’heure de début spécifiée ne sont pas copiés. Si l’heure de fin est définie, les fichiers de données d’événement dans lesquels toutes les entrées de journal à partir de l’heure spécifiée ou ultérieure ne sont pas copiées. Si seule une partie des données d’un fichier se trouve dans la plage spécifiée, l’intégralité du fichier est copiée sur l’ordinateur cible. </p> <p>Adobe recommande d’utiliser l’un des formats suivants pour l’heure : 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1er janvier 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1er janvier 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Remarque : Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur l’heure système s’il n’est pas spécifié. Si vous souhaitez mettre en oeuvre l’heure d’été ou une stratégie similaire de changement d’heure, vous devez enregistrer la variable <span class="filepath"> .dst</span> fichier contenant les règles appropriées dans le répertoire Base\Dataset\Timezone sur le <span class="keyword"> Serveur Insight</span> machine. Pour obtenir la liste des abréviations de fuseau horaire prises en charge et des informations sur la mise en oeuvre de l’heure d’été, voir <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codes du fuseau horaire</a>. </p> </p> <p> <p>Remarque : Pour utiliser ces paramètres, les noms des fichiers de données d’événement doivent commencer par une date ISO (AAAAMMJJ), et chaque fichier doit contenir des données pour la période de 24 heures commençant à 12 h GMT à cette date. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Cet exemple illustre la manière dont les fichiers sont copiés si les paramètres Flatten Paths et Recursive sont définis sur true.

Supposons que l’URI distant soit [!DNL /RemoteRoot/] et le chemin d’accès local est [!DNL E:\LocalRoot\]. Sur la télécommande ( [!DNL Repeater]), les fichiers sont organisés comme suit :

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Une fois la réplication terminée, le répertoire local contient les fichiers suivants :

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Dans le répertoire local, aucun sous-répertoire n’est créé et tous les fichiers de l’arborescence de répertoires distants sont placés au niveau supérieur du répertoire local.

>[!NOTE]
>
>Si les fichiers des différents sous-répertoires de la machine distante partagent le même nom, la variable [!DNL Replication Service] peut s’arrêter ou tout autre comportement non défini peut se produire.
