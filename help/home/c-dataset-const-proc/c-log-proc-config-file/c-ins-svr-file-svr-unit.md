---
description: Informations sur les unités du serveur de fichiers Insight Server et le processus de configuration du serveur de fichiers.
solution: Analytics
title: Configuration d’une unité de serveur de fichiers de Outils de données
topic: Data workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Configuration d’une unité de serveur de fichiers de Outils de données{#configuring-a-data-workbench-server-file-server-unit}

Informations sur les unités du serveur de fichiers Insight Server et le processus de configuration du serveur de fichiers.

<!--
c_abt_file_svr_units.xml
-->

Vous pouvez configurer le serveur de l’outil de données (InsightServer64.exe) pour qu’il s’exécute en tant qu’unité de serveur de fichiers (FSU) en remplissant les paramètres du noeud **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** du [!DNL Log Processing.cfg] fichier. Lorsque le serveur de l’outil de données est configuré pour s’exécuter en tant que FSU, il stocke des fichiers source ( [!DNL .vsl] fichiers, fichiers texte ou fichiers XML) accessibles rapidement par plusieurs serveurs de traitement (DPU). Lorsque les unités de traitement de données d’une grappe de serveurs de outils de données accèdent à l’unité de traitement des données pour lire les fichiers journaux, elles les divisent et garantissent que le même fichier n’est pas traité plus d’une fois.

>[!NOTE]
>
>Lors de la configuration d’une unité de traitement de données qui sert une grappe de serveurs de outils de données composée de cinq à dix unités de traitement de données, vous devez faire du serveur maître de la grappe l’unité de traitement de données.

Pour plus d’informations sur l’installation d’une grappe de serveurs de outils de données, voir le Guide *d’installation et d’administration des produits* serveur.

<!--
c_file_svr_config_proc.xml
-->

Si l’emplacement est distant, l’ordinateur serveur de l’outil de données qui traite les données se connecte à l’ordinateur distant désigné pour lire les journaux.

Sur l’ordinateur serveur de l’outil de données désigné pour s’exécuter en tant que FSU, le [!DNL Access Control.cfg] fichier permet aux DPU de se connecter au FSU et le [!DNL Communications.cfg] fichier mappe l’emplacement des fichiers de données distants. Les étapes du processus de configuration d’un FSU sont les suivantes :

1. Dans le [!DNL Log Processing.cfg] fichier de votre serveur maître de l’outil de données, spécifiez le type de source de données et l’emplacement de la source. Voir [Spécification de la source](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383)de données.

1. Dans le [!DNL Access Control.cfg] fichier sur le FSU, modifiez les autorisations pour permettre aux DPU de se connecter au FSU de lire les données du journal. Voir [Modification des autorisations sur l’unité](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef)du serveur de fichiers.

1. Dans le [!DNL Communications.cfg] fichier FSU, modifiez les paramètres des entrées [!DNL LoggingServer] et [!DNL FileServer] pour spécifier l’emplacement des fichiers journaux. Voir [Spécification de l’emplacement des fichiers](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0)journaux.

1. Si vous configurez votre profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs de l’outil de données, vous devez également faire du FSU de la grappe le serveur sur lequel sont construites toutes les dimensions du profil :
(Pour les grappes de serveurs de l’outil de données uniquement) Dans les fichiers [!DNL Communications.cfg] et [!DNL cluster.cfg] sur le FSU, ajoutez des entrées pour un &quot;serveur de normalisation&quot; afin de faire du FSU le serveur de la grappe dans laquelle toutes les dimensions sont construites. Voir [Création d’un serveur de normalisation centralisé pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Pour obtenir des instructions sur la configuration d’un profil de jeu de données à traiter par une grappe de serveurs de outils de données, consultez le Guide *d’installation et d’administration des produits* serveur.

>[!NOTE]
>
>Les instructions suivantes supposent que tous les fichiers journaux résident dans le répertoire par défaut. Si vous souhaitez stocker des journaux dans un autre répertoire ou créer plusieurs chemins d’accès aux journaux, contactez les services de conseil Adobe pour discuter de votre configuration spécifique.

## Spécification de la source de données {#section-d2b545db7ab142ffb4be32e040395383}

Lors de la spécification de sources de données distantes pour un jeu de données, vous devez spécifier le type de source de données et l’emplacement des fichiers journaux sur votre serveur maître de l’outil de données.

**Pour spécifier la source de données et son emplacement**

1. Open the [!DNL Log Processing.cfg] file. Voir [Modification du fichier](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuration de traitement du journal.

1. Ajoutez une source de données [!DNL Sensor], un fichier journal ou XML. See [Log Files](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Renseignez le paramètre Chemins du journal. Voir Fichiers [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)Sensor, Fichiers [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)journaux ou Sources [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)XML Log. Veillez à spécifier un URI valide.

1. Renseignez les paramètres du serveur de journaux définis dans le tableau suivant :

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
   <td colname="col2"> <p> <span class="wintitle"> Nom</span> commun du serveur répertorié dans le certificat SSL du serveur de fichiers. </p> <p> Ce paramètre est facultatif si <span class="wintitle"> Use SSL</span> est défini sur false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Adresse du serveur de fichiers. Peut être laissé vide si <span class="wintitle"> Name</span> correspond à <span class="wintitle"> SSL Server Common Name</span>. </p> <p> Par exemple : <span class="filepath"> visuel.masociété.com</span> ou 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port par lequel l’ordinateur du serveur de l’outil de données communique avec le serveur de fichiers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> Nom du fichier de certificat <span class="wintitle"></span> SSL pour le serveur de l’outil de données (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser SSL </td> 
   <td colname="col2"> True ou false. True indique que le serveur de fichiers utilise <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Si un serveur proxy est nécessaire pour que les DPU se connectent au FSU, vous devez exécuter les paramètres suivants :

| Paramètre | Description |
|---|---|
| Adresse du proxy | adresse d’un serveur proxy que le serveur de outils de données doit utiliser pour accéder au serveur de fichiers. |
| Mot de passe du proxy | Facultatif. mot de passe du serveur proxy. |
| Port du proxy | port du serveur proxy. La valeur par défaut est de 8080. |
| Nom d’utilisateur du proxy | Facultatif. Nom d’utilisateur du serveur proxy. |

Voici un exemple de définition [!DNL Log Server] dans le [!DNL Log Processing.cfg] fichier. La source de journal n° 1 est une source de fichier journal qui pointe vers un répertoire appelé Logs (notez l&#39;URI spécifié dans le paramètre Chemins de journal) sur l&#39;ordinateur nommé FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Modification des autorisations sur l’unité du serveur de fichiers {#section-b4a54b591b4e4435a728a67f194057ef}

Dans le processus précédent, vous avez configuré un profil pour un jeu de données donné afin de lire les fichiers journaux d’un FSU. Vous devez maintenant modifier les autorisations sur le FSU pour autoriser les connexions à partir des DPU qui exécutent le profil. Les étapes suivantes vous guident tout au long de la modification du fichier d’autorisations [!DNL Access Control.cfg].

**Pour modifier les autorisations sur le FSU**

1. Ouvrez le serveur [!DNL Server Files Manager] de l’outil de données que vous configurez en tant que FSU et cliquez sur **[!UICONTROL Access Control]** pour en afficher le contenu.

   Pour plus d’informations sur l’ouverture et l’utilisation de [!DNL Server Files Manager]Data Workbench, consultez le Guide *de l’utilisateur des outils de* données.

1. Dans la [!DNL Server Files Manager] fenêtre, cliquez **[!UICONTROL Access Control]** pour afficher son contenu. Le [!DNL Access Control.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Access Control.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Access Control.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée sous la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Dans la [!DNL Access Control] fenêtre, cliquez **[!UICONTROL Access Control Groups]** pour afficher son contenu.

1. Cliquez avec le bouton droit de la souris sur l’étiquette numérique de la dernière [!DNL AccessGroup] dans la liste et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Entrez un [!DNL Name] pour le nouveau [!DNL AccessGroup]. Exemple : Connexion des serveurs.

1. Cliquez avec le bouton droit **[!UICONTROL Member]** sous le nouveau [!DNL AccessGroup], puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Entrez l’adresse IP du DPU du serveur de l’outil de données qui se connecte à ce serveur de fichiers.
1. Répétez les étapes 4 et 5 pour tous les autres fichiers DPU de serveur de l’outil de données qui se connectent à ce FSU, y compris les fichiers DPU de serveur de l’outil de données d’une grappe devant accéder aux fichiers journaux.
1. Cliquez avec le bouton droit **[!UICONTROL Read-Only Access]** sous le nouveau [!DNL AccessGroup], puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Indiquez l’emplacement des fichiers journaux stockés sur l’ordinateur du serveur de fichiers. Utilisez des barres obliques (/) dans la spécification du chemin. L’emplacement par défaut est /Logs/.
1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la [!DNL Server Files Manager] fenêtre, cliquez avec le bouton droit de la souris sur la coche [!DNL Access Control.cfg] de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL server name]** pour enregistrer les modifications apportées localement au FSU du serveur de l’outil de données.

## Spécification de l&#39;emplacement des fichiers journaux {#section-f9a649bf1b2544feb10ad8820384edb0}

Vous devez modifier le [!DNL Communications.cfg] fichier sur le FSU pour spécifier l’emplacement des fichiers journaux.

**Pour spécifier l’emplacement des fichiers journaux**

1. Dans la [!DNL Server Files Manager] fenêtre, cliquez **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Communications.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Communications.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Communications.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée sous la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Dans la [!DNL Communications.cfg] fenêtre, cliquez **[!UICONTROL component]** pour afficher son contenu.

1. Dans la [!DNL Communications.cfg] fenêtre, cliquez **[!UICONTROL Servers]** pour afficher son contenu. Plusieurs serveurs peuvent apparaître : Serveurs de fichiers, serveurs de journalisation, serveurs d’initialisation, serveurs d’état, serveurs d’envoi ou serveurs de réplication.

1. (Pour [!DNL Sensor] les sources de journal uniquement) Recherchez [!DNL LoggingServer], où [!DNL Sensor] écrivent ses fichiers journaux à traiter par le serveur de l’outil de données, puis cliquez sur son numéro pour afficher le menu. Modifiez le paramètre Répertoire journal pour refléter l’emplacement souhaité des fichiers journaux. Le répertoire de journal par défaut est le dossier Journaux du répertoire d’installation du serveur de l’outil de données.

   Ne modifiez aucun autre paramètre pour le [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Recherchez le serveur de fichiers qui spécifie l’emplacement des fichiers journaux. Plusieurs serveurs de fichiers peuvent être répertoriés sous Serveurs. Vous devrez peut-être consulter le contenu de plusieurs d’entre eux (en cliquant sur le numéro de serveur) pour trouver le serveur souhaité.
1. Modifiez les paramètres [!DNL Local Path] et URI du serveur de fichiers afin de refléter l’emplacement des fichiers journaux. L’exemple suivant montre que les fichiers journaux résident dans le dossier Journaux du répertoire d’installation du serveur de l’outil de données :

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Si les paramètres [!DNL Local Path] et URI sont renseignés comme indiqué, vous pouvez accéder aux fichiers journaux du FSU à partir de n’importe quel serveur de l’outil de données en cliquant [!DNL Logs] dans le [!DNL Server Files Manager].

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre de configuration, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la [!DNL Server Files Manager] fenêtre, cliquez avec le bouton droit de la souris sur la coche [!DNL Communications.cfg] de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL server name]*** pour enregistrer les modifications apportées localement au FSU du serveur de l’outil de données.

## Création d’un serveur de normalisation centralisé pour une grappe {#section-2c1f57b683f94cc193bc069e886bba28}

Si vous configurez votre profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs de l’outil de données, vous devez faire du FSU de la grappe le serveur sur lequel sont construites toutes les dimensions du profil.

Adobe recommande vivement que l’unité d’exécution de la grappe serve de serveur maître de la grappe et de serveur de normalisation centralisé.

Pour faire du FSU le serveur de normalisation centralisé, vous devez ouvrir et modifier les fichiers [!DNL Communications.cfg] et [!DNL Cluster.cfg] les fichiers sur le FSU.

**Pour faire du FSU le serveur de normalisation centralisé**

1. Ajoutez une [!DNL NormalizeServer] entrée au [!DNL Communications.cfg] fichier sur le FSU.

   >[!NOTE]
   >
   >Si vous avez installé le package de version complet pour le serveur de l’outil de données version 5.0 ou ultérieure, le [!DNL Communications.cfg] fichier de votre FSU doit déjà comporter une [!DNL NormalizeServer] entrée. Vous pouvez suivre les étapes ci-dessous pour confirmer l’existence de l’entrée.

   1. Ouvrez le [!DNL Communications.cfg] fichier dans l’outil de données, comme décrit dans [Spécification de l’emplacement des fichiers](#section-f9a649bf1b2544feb10ad8820384edb0)journaux.

   1. Cliquez sur **[!UICONTROL component]** pour afficher son contenu.
   1. Cliquez avec le bouton droit de la souris **[!UICONTROL Servers]** , puis cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. Dans le paramètre URI du [!DNL NormalizeServer], saisissez [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager] fenêtre, cliquez avec le bouton droit de la souris sur la coche [!DNL Communications.cfg] de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL server]*** nom pour enregistrer les modifications apportées localement au serveur FSU du Outils de données.

1. Définissez le serveur de normalisation centralisé dans le [!DNL Cluster.cfg] fichier sur le serveur maître dans votre grappe de serveurs de outils de données.

   >[!NOTE]
   >
   >Si le serveur FSU sur lequel vous configurez votre serveur de normalisation centralisé n’est pas le serveur maître des outils de données de votre grappe, vous devez ajouter les adresses IP des DPU de la grappe au groupe d’ [!DNL Cluster Servers] accès du [!DNL Access Control.cfg] fichier FSU. Pour plus d’informations sur l’ajout de serveurs au [!DNL Cluster Servers] groupe, voir Mise à jour du fichier de contrôle d’accès pour une grappe dans le Guide d’installation et d’administration des produits *serveur.*

   1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données, puis cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu. Le [!DNL Cluster.cfg] fichier se trouve dans ce répertoire.

   1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Cluster.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.

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
      >Lorsque vous saisissez le nom commun de FSU pour le paramètre Nom commun du serveur SSL, le FSU utilise son [!DNL .address] fichier pour résoudre le nom commun. Pour plus d’informations sur le [!DNL .address] fichier, consultez le Guide *d’installation et d’administration des produits* serveur.

   1. Enregistrez le fichier.
   1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Cluster.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** pour enregistrer les modifications apportées localement au profil du jeu de données.
