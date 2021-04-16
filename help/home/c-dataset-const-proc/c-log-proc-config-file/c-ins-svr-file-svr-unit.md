---
description: Informations sur les unités du serveur de fichiers Insight Server et le processus de configuration du serveur de fichiers.
title: Configuration d’une unité service de fichier serveur Data Workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 1%

---

# Configuration d’une unité service de fichier serveur Data Workbench{#configuring-a-data-workbench-server-file-server-unit}

Informations sur les unités du serveur de fichiers Insight Server et le processus de configuration du serveur de fichiers.

<!--
c_abt_file_svr_units.xml
-->

Vous pouvez configurer le serveur d’outils de données (InsightServer64.exe) pour qu’il s’exécute en tant qu’unité de serveur de fichiers (FSU) en exécutant les paramètres du noeud **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** du fichier [!DNL Log Processing.cfg]. Lorsque le serveur de l&#39;outil de données est configuré pour s&#39;exécuter en tant que FSU, il stocke les fichiers source (fichiers [!DNL .vsl], fichiers texte ou fichiers XML) qui peuvent être rapidement accessibles par plusieurs serveurs de traitement (DPU). Lorsque les unités de traitement de données d&#39;une grappe de serveurs Outils de données accèdent à l&#39;unité de traitement des données pour lire les fichiers journaux, elles les divisent et garantissent que le même fichier n&#39;est pas traité plusieurs fois.

>[!NOTE]
>
>Lors de la configuration d’une unité de traitement de données qui sert une grappe de serveurs de l’outil de données composée de cinq à dix unités de traitement de données, vous devez faire du serveur maître de la grappe l’unité de traitement de données.

Pour plus d’informations sur l’installation d’une grappe de serveurs de l’outil de données, voir le *Guide d’installation et d’administration des produits serveur*.

<!--
c_file_svr_config_proc.xml
-->

Si l’emplacement est distant, l’ordinateur serveur de l’outil de données qui traite les données se connecte à l’ordinateur distant désigné pour lire les journaux.

Sur l&#39;ordinateur serveur de l&#39;outil de données désigné pour s&#39;exécuter en tant que FSU, le fichier [!DNL Access Control.cfg] permet aux unités de traitement de données de se connecter à l&#39;unité de traitement des données et le fichier [!DNL Communications.cfg] mappe l&#39;emplacement des fichiers de données distants. Les étapes du processus de configuration d&#39;un FSU sont les suivantes :

1. Dans le fichier [!DNL Log Processing.cfg] de votre serveur maître de l&#39;outil de données, spécifiez le type de source de données et l&#39;emplacement de la source. Voir [Spécification de la source de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. Dans le fichier [!DNL Access Control.cfg] de la FSU, modifiez les autorisations pour permettre aux DPU de se connecter à la FSU pour lire les données du journal. Voir [Modification des autorisations sur l’unité du serveur de fichiers](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. Dans le fichier [!DNL Communications.cfg] de la FSU, modifiez les paramètres des entrées [!DNL LoggingServer] et [!DNL FileServer] pour spécifier l&#39;emplacement des fichiers journaux. Voir [Spécification de l&#39;emplacement des fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Si vous configurez votre profil de jeux de données pour qu’il s’exécute sur une grappe de serveurs de l’outil de données, vous devez également faire de l’unité de traitement de données de la grappe le serveur sur lequel toutes les dimensions du profil sont construites :
(Pour les grappes de serveurs de l&#39;outil de données uniquement) Dans les fichiers [!DNL Communications.cfg] et [!DNL cluster.cfg] de l&#39;unité de traitement des données, ajoutez des entrées pour un &quot;serveur normalisé&quot; afin de faire de l&#39;unité de traitement des données le serveur de la grappe dans laquelle toutes les dimensions sont construites. Voir [Création d&#39;un serveur de normalisation centralisée pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Pour obtenir des instructions sur la configuration d&#39;un profil de données à traiter par une grappe de serveurs de l&#39;outil de données, consultez le *Guide d&#39;installation et d&#39;administration des produits serveur*.

>[!NOTE]
>
>Les instructions suivantes supposent que tous les fichiers journaux résident dans le répertoire par défaut. Si vous souhaitez stocker des journaux dans un autre répertoire ou créer plusieurs chemins d’accès aux journaux, contactez les services de conseil en Adobe pour discuter de votre configuration spécifique.

## Spécification de la source de données {#section-d2b545db7ab142ffb4be32e040395383}

Lors de la spécification de sources de données distantes pour un jeu de données, vous devez indiquer le type de source de données et l’emplacement des fichiers journaux sur votre serveur maître de l’outil de données.

**Pour spécifier la source de données et son emplacement**

1. Ouvrez le fichier [!DNL Log Processing.cfg]. Voir [Modification du fichier de configuration de traitement du journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. Ajoutez une source de données [!DNL Sensor], un fichier journal ou XML. Voir [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Renseignez le paramètre Chemins d&#39;accès au journal. Voir [Fichiers capteur](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e) ou [Sources de journaux XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Veillez à spécifier un URI valide.

1. Renseignez les paramètres Log Server définis dans le tableau suivant :

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Nom identifiant le serveur de fichiers distant. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom commun du serveur SSL </td> 
   <td colname="col2"> <p> <span class="wintitle"> Serveur commun de </span> noms figurant sur la liste du certificat SSL du serveur de fichiers. </p> <p> Ce paramètre est facultatif si <span class="wintitle"> Utiliser SSL</span> est défini sur false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Adresse de l’ordinateur du serveur de fichiers. Peut être laissé vide si <span class="wintitle"> Name</span> correspond à <span class="wintitle"> SSL Server Common Name</span>. </p> <p> Par exemple : <span class="filepath"> visual.mycompany.com</span> ou 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port par lequel l’ordinateur serveur de l’outil de données communique avec le serveur de fichiers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> Nom du fichier <span class="wintitle"> de certificat SSL</span> pour le serveur de l’outil de données (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser SSL </td> 
   <td colname="col2"> Vrai ou faux. True indique que le serveur de fichiers utilise <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Si un serveur proxy est nécessaire pour que les unités de traitement des données se connectent au FSU, vous devez exécuter les paramètres suivants :

| Paramètre | Description |
|---|---|
| Adresse du proxy | adresse d’un serveur proxy que le serveur de l’outil de données doit utiliser pour accéder au serveur de fichiers. |
| Mot de passe du proxy | Facultatif. Mot de passe du serveur proxy. |
| Port proxy | Port du serveur proxy. La valeur par défaut est de 8080. |
| Nom d’utilisateur du proxy | Facultatif. Nom d’utilisateur du serveur proxy. |

Voici un exemple d&#39;un [!DNL Log Server] défini dans le fichier [!DNL Log Processing.cfg]. La source de journal n°1 est une source de fichier journal qui pointe vers un répertoire appelé Logs (notez l&#39;URI spécifié dans le paramètre Log Paths) sur l&#39;ordinateur nommé FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Modification des autorisations sur l&#39;unité du serveur de fichiers {#section-b4a54b591b4e4435a728a67f194057ef}

Dans le processus précédent, vous avez configuré un profil pour un jeu de données donné afin de lire les fichiers journaux d’un FSU. Vous devez à présent modifier les autorisations sur l&#39;unité de gestion des stocks pour autoriser les connexions à partir des unités de gestion des stocks qui exécutent le profil. Les étapes suivantes vous guident tout au long de la modification du fichier d&#39;autorisations [!DNL Access Control.cfg].

**Pour modifier les autorisations sur l&#39;unité de gestion des stocks**

1. Ouvrez [!DNL Server Files Manager] pour l’ordinateur serveur de l’outil de données que vous configurez en tant que FSU et cliquez sur **[!UICONTROL Access Control]** pour en afficher le contenu.

   Pour plus d&#39;informations sur l&#39;ouverture et l&#39;utilisation de [!DNL Server Files Manager], consultez le *Guide de l&#39;utilisateur Data Workbench*.

1. Dans la fenêtre [!DNL Server Files Manager], cliquez sur **[!UICONTROL Access Control]** pour afficher son contenu. Le fichier [!DNL Access Control.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Access Control.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Access Control.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée sous la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Dans la fenêtre [!DNL Access Control], cliquez sur **[!UICONTROL Access Control Groups]** pour afficher son contenu.

1. Cliquez avec le bouton droit de la souris sur le libellé numérique de la dernière balise [!DNL AccessGroup] dans la liste et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Entrez un [!DNL Name] pour le nouveau [!DNL AccessGroup]. Exemple : Connexion de serveurs.

1. Cliquez avec le bouton droit **[!UICONTROL Member]** sous le nouveau [!DNL AccessGroup], puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Entrez l’adresse IP du DPU du serveur de l’outil de données qui se connecte à ce serveur de fichiers.
1. Répétez les étapes 4 et 5 pour tous les autres DPU de serveur de l&#39;outil de données qui se connectent à ce FSU, y compris les DPU de serveur de l&#39;outil de données d&#39;une grappe devant accéder aux fichiers journaux.
1. Cliquez avec le bouton droit **[!UICONTROL Read-Only Access]** sous le nouveau [!DNL AccessGroup], puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Indiquez l’emplacement des fichiers journaux stockés sur l’ordinateur du serveur de fichiers. Utilisez des barres obliques (/) dans la spécification de chemin. L&#39;emplacement par défaut est /Logs/.
1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la fenêtre [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Access Control.cfg] de la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL server name]** pour enregistrer les modifications apportées localement à l&#39;unité de traitement de données du serveur de l&#39;outil de données.

## Spécification de l&#39;emplacement des fichiers journaux {#section-f9a649bf1b2544feb10ad8820384edb0}

Vous devez modifier le fichier [!DNL Communications.cfg] sur l&#39;unité de gestion des stocks pour spécifier l&#39;emplacement des fichiers journaux.

**Pour spécifier l’emplacement des fichiers journaux**

1. Dans la fenêtre [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le fichier [!DNL Communications.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Communications.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Communications.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée sous la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL component]** pour afficher son contenu.

1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL Servers]** pour afficher son contenu. Plusieurs serveurs peuvent apparaître : Serveurs de fichiers, serveurs de journalisation, serveurs d’initialisation, serveurs d’état, serveurs d’envoi ou serveurs de réplication.

1. (Pour [!DNL Sensor] sources de journaux uniquement) Recherchez [!DNL LoggingServer], où [!DNL Sensor] écrit ses fichiers journaux pour qu’ils soient traités par le serveur de l’outil de données, puis cliquez sur son numéro pour vue au menu. Modifiez le paramètre Répertoire de journaux pour refléter l’emplacement souhaité des fichiers journaux. Le répertoire de journalisation par défaut est le dossier Journaux du répertoire d’installation du serveur de l’outil de données.

   Ne modifiez aucun autre paramètre pour le [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Recherchez le serveur de fichiers qui spécifie l’emplacement des fichiers journaux. Il peut y avoir plusieurs serveurs de fichiers répertoriés sous Serveurs, vous devrez peut-être en vue le contenu pour plusieurs d&#39;entre eux (en cliquant sur le numéro de serveur) pour trouver le serveur de votre choix.
1. Modifiez les paramètres [!DNL Local Path] et URI pour FileServer afin de refléter l’emplacement des fichiers journaux. L’exemple suivant montre que les fichiers journaux résident dans le dossier Journaux du répertoire d’installation du serveur de l’outil de données :

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Si les paramètres [!DNL Local Path] et URI sont renseignés comme indiqué, vous pouvez accéder aux fichiers journaux de l&#39;unité de traitement des données à partir de n&#39;importe quel serveur de l&#39;outil de données en cliquant sur [!DNL Logs] dans la [!DNL Server Files Manager].

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre de configuration, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la fenêtre [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Communications.cfg] dans la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]*** pour enregistrer les modifications apportées localement au FSU du serveur de l&#39;outil de données.

## Création d&#39;un serveur de normalisation centralisé pour une grappe {#section-2c1f57b683f94cc193bc069e886bba28}

Si vous configurez votre profil de jeux de données pour qu’il s’exécute sur une grappe de serveurs de l’outil de données, vous devez faire du FSU de la grappe le serveur sur lequel toutes les dimensions du profil sont construites.

L’Adobe recommande vivement que l’unité d’analyse de la grappe serve de serveur maître de la grappe et de serveur de normalisation centralisé.

Pour faire de l&#39;UFS le serveur de normalisation centralisé, vous devez ouvrir et modifier les fichiers [!DNL Communications.cfg] et [!DNL Cluster.cfg] sur l&#39;unité de gestion financière.

**Pour faire de la FSU le serveur de normalisation centralisé**

1. Ajoutez une entrée [!DNL NormalizeServer] dans le fichier [!DNL Communications.cfg] de la FSU.

   >[!NOTE]
   >
   >Si vous avez installé le package de version complet pour le serveur de données Workbench version 5.0 ou ultérieure, le fichier [!DNL Communications.cfg] de votre FSU doit déjà comporter une entrée [!DNL NormalizeServer]. Vous pouvez suivre les étapes ci-dessous pour confirmer que l’entrée existe.

   1. Ouvrez le fichier [!DNL Communications.cfg] dans l&#39;outil de données comme décrit dans [Spécification de l&#39;emplacement des fichiers journaux](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. Cliquez sur **[!UICONTROL component]** pour afficher son contenu.
   1. Cliquez avec le bouton droit **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. Dans le paramètre URI pour [!DNL NormalizeServer], saisissez [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la fenêtre [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Communications.cfg] de la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > *&lt; &lt;a5/&quot;* nom pour enregistrer les modifications apportées localement au FSU du serveur de l&#39;outil de données.**[!UICONTROL server]**

1. Définissez le serveur de normalisation centralisé dans le fichier [!DNL Cluster.cfg] du serveur maître de votre grappe de serveurs de outils de données.

   >[!NOTE]
   >
   >Si l&#39;unité de traitement de données sur laquelle vous configurez votre serveur de normalisation centralisé n&#39;est pas le serveur maître des outils de données de votre grappe, vous devez ajouter les adresses IP des unités de traitement de données de la grappe au groupe d&#39;accès [!DNL Cluster Servers] dans le fichier [!DNL Access Control.cfg] de l&#39;unité de traitement de données financière. Pour obtenir des instructions sur l&#39;ajout de serveurs au groupe [!DNL Cluster Servers], consultez la section Mise à jour du fichier de Contrôle d&#39;accès d&#39;une grappe dans le *Guide d&#39;installation et d&#39;administration des produits serveur.*

   1. Ouvrez [!DNL Profile Manager] dans votre profil de jeux de données, puis cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu. Le fichier [!DNL Cluster.cfg] se trouve dans ce répertoire.

   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Cluster.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].

   1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. Ajoutez le texte mis en surbrillance dans le fragment de fichier suivant :

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >Lorsque vous saisissez le nom commun de l&#39;unité de gestion des stocks pour le paramètre SSL Server Common Name, l&#39;unité de gestion des stocks utilise son fichier [!DNL .address] pour résoudre le nom commun. Pour plus d&#39;informations sur le fichier [!DNL .address], consultez le *Server Products Installation and Administration Guide*.

   1. Enregistrez le fichier.
   1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Cluster.cfg] de la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** pour enregistrer les modifications apportées localement au profil de données.
