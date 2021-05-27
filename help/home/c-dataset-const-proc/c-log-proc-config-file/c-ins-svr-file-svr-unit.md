---
description: Informations sur les unités du serveur de fichiers Insight Server et le processus de configuration du serveur de fichiers.
title: Configuration d’une unité service de fichier serveur Data Workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
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

Vous pouvez configurer le serveur Data Workbench (InsightServer64.exe) pour qu’il s’exécute en tant qu’unité de serveur de fichiers (FSU) en renseignant les paramètres dans le noeud **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** du fichier [!DNL Log Processing.cfg]. Lorsque le serveur Data Workbench est configuré pour s’exécuter en FSU, il stocke les fichiers source ( [!DNL .vsl] fichiers, fichiers texte ou fichiers XML) accessibles rapidement par plusieurs serveurs de traitement (DPU). Lorsque les DPU d’une grappe de serveurs Data Workbench accèdent au FSU pour lire les fichiers journaux, ils les divisent et garantissent que le même fichier n’est pas traité plus d’une fois.

>[!NOTE]
>
>Lors de la configuration d’un FSU qui sert une grappe de serveurs Data Workbench composée de cinq à dix DPU, vous devez faire du serveur maître de la grappe le FSU.

Pour plus d’informations sur l’installation d’une grappe de serveurs Data Workbench, consultez le *Guide d’installation et d’administration des produits serveur*.

<!--
c_file_svr_config_proc.xml
-->

Si l’emplacement est distant, l’ordinateur serveur Data Workbench qui traite les données se connecte à l’ordinateur distant désigné pour lire les journaux.

Sur l’ordinateur serveur Data Workbench désigné pour s’exécuter en FSU, le fichier [!DNL Access Control.cfg] permet aux DPU de se connecter au FSU, et le fichier [!DNL Communications.cfg] mappe l’emplacement des fichiers de données distants. Les étapes de processus pour configurer un FSU sont les suivantes :

1. Dans le fichier [!DNL Log Processing.cfg] de votre serveur Data Workbench principal, spécifiez le type de source de données et l’emplacement de la source. Voir [Spécification de la source de données](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. Dans le fichier [!DNL Access Control.cfg] du FSU, modifiez les autorisations pour permettre aux DPU de se connecter au FSU afin de lire les données du journal. Voir [Modification des autorisations sur l’unité du serveur de fichiers](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. Dans le fichier [!DNL Communications.cfg] du FSU, modifiez les paramètres des entrées [!DNL LoggingServer] et [!DNL FileServer] pour spécifier l’emplacement des fichiers journaux. Voir [Spécification de l’emplacement des fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Si vous configurez votre profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs Data Workbench, vous devez également faire du FSU de la grappe le serveur sur lequel toutes les dimensions du profil sont construites :
(Pour les grappes de serveurs Data Workbench uniquement) Dans les fichiers [!DNL Communications.cfg] et [!DNL cluster.cfg] du FSU, ajoutez des entrées pour un &quot;serveur de normalisation&quot; afin de faire du FSU le serveur de la grappe où toutes les dimensions sont construites. Voir [Création d’un serveur de normalisation centralisé pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Pour obtenir des instructions sur la configuration d’un profil de jeu de données à traiter par une grappe de serveurs Data Workbench, consultez le *Guide d’installation et d’administration des produits serveur*.

>[!NOTE]
>
>Les instructions suivantes supposent que tous les fichiers journaux résident dans le répertoire par défaut. Si vous souhaitez stocker les journaux dans un autre répertoire ou créer plusieurs chemins d’accès aux journaux, contactez les services de conseil d’Adobe pour discuter de votre configuration spécifique.

## Spécification de la source de données {#section-d2b545db7ab142ffb4be32e040395383}

Lors de la spécification de sources de données distantes pour un jeu de données, vous devez spécifier le type de source de données et l’emplacement des fichiers journaux sur votre serveur Data Workbench principal.

**Pour spécifier la source de données et son emplacement**

1. Ouvrez le fichier [!DNL Log Processing.cfg] . Voir [Modification du fichier de configuration de traitement du journal](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. Ajoutez une source de données [!DNL Sensor], un fichier journal ou XML. Voir [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Renseignez le paramètre Chemins d’accès du journal . Voir [Fichiers de Capteur](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [Fichiers journaux](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e) ou [Sources de journal XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Veillez à spécifier un URI valide.

1. Renseignez les paramètres du serveur de journal définis dans le tableau suivant :

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
   <td colname="col2"> <p> <span class="wintitle"> Server Common </span> Namelist sur le certificat SSL du serveur de fichiers. </p> <p> Ce paramètre est facultatif si <span class="wintitle"> Utiliser SSL</span> est défini sur false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Adresse du serveur de fichiers. Peut être laissé vide si <span class="wintitle"> Name</span> correspond à <span class="wintitle"> SSL Server Common Name</span>. </p> <p> Par exemple : <span class="filepath"> visuel.mycompany.com</span> ou 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port par lequel le serveur Data Workbench communique avec le serveur de fichiers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> Nom du fichier <span class="wintitle"> certificat SSL</span> pour le serveur Data Workbench (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser SSL </td> 
   <td colname="col2"> Vrai ou faux. La valeur True indique que le serveur de fichiers utilise <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Si un serveur proxy est nécessaire pour que les DPU se connectent au FSU, vous devez effectuer les paramètres suivants :

| Paramètre | Description |
|---|---|
| Adresse du proxy | Adresse d’un serveur proxy que le serveur Data Workbench doit utiliser pour accéder au serveur de fichiers. |
| Mot de passe du proxy | Facultatif. Mot de passe du serveur proxy. |
| Port du proxy | Port du serveur proxy. La valeur par défaut est de 8080. |
| Nom d’utilisateur du proxy | Facultatif. Nom d’utilisateur du serveur proxy. |

Voici un exemple de [!DNL Log Server] défini dans le fichier [!DNL Log Processing.cfg]. Source du journal #1 est une source LogFile qui pointe vers un répertoire appelé Logs (notez l’URI spécifié dans le paramètre Chemins du journal) sur la machine nommée FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Modification des autorisations sur l’unité de serveur de fichiers {#section-b4a54b591b4e4435a728a67f194057ef}

Dans le processus précédent, vous avez configuré un profil pour un jeu de données donné afin de lire les fichiers journaux d’un FSU. Vous devez maintenant modifier les autorisations sur le FSU pour autoriser les connexions à partir des DPU qui exécutent le profil. Les étapes suivantes vous guident tout au long de la modification du fichier d’autorisations [!DNL Access Control.cfg].

**Pour modifier les autorisations sur le FSU**

1. Ouvrez la [!DNL Server Files Manager] pour l’ordinateur serveur Data Workbench que vous configurez en tant que FSU et cliquez sur **[!UICONTROL Access Control]** pour afficher son contenu.

   Pour plus d’informations sur l’ouverture et l’utilisation de [!DNL Server Files Manager], consultez le *Guide de l’utilisateur du Data Workbench*.

1. Dans la fenêtre [!DNL Server Files Manager], cliquez sur **[!UICONTROL Access Control]** pour en afficher le contenu. Le fichier [!DNL Access Control.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne nom du serveur pour [!DNL Access Control.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Access Control.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée sous la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Dans la fenêtre [!DNL Access Control], cliquez sur **[!UICONTROL Access Control Groups]** pour en afficher le contenu.

1. Cliquez avec le bouton droit de la souris sur le libellé numérique correspondant au [!DNL AccessGroup] final dans la liste et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Saisissez une [!DNL Name] pour la nouvelle [!DNL AccessGroup]. Exemple : Connexion des serveurs.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Member]** sous le nouveau [!DNL AccessGroup], puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Saisissez l’adresse IP du DPU du serveur Data Workbench qui se connecte à ce serveur de fichiers.
1. Répétez les étapes 4 et 5 pour tous les autres DPU de serveur Data Workbench qui se connectent à ce FSU, y compris les DPU de serveur Data Workbench d’une grappe qui doit accéder aux fichiers journaux.
1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Read-Only Access]** sous le nouveau [!DNL AccessGroup], puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Saisissez l’emplacement des fichiers journaux stockés sur l’ordinateur du serveur de fichiers. Utilisez des barres obliques (/) dans la spécification du chemin. L’emplacement par défaut est /Logs/.
1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la fenêtre [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Access Control.cfg] dans la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL server name]** pour enregistrer les modifications apportées localement au FSU du serveur Data Workbench.

## Spécification de l’emplacement des fichiers journaux {#section-f9a649bf1b2544feb10ad8820384edb0}

Vous devez éditer le fichier [!DNL Communications.cfg] sur le FSU pour spécifier l&#39;emplacement des fichiers journaux.

**Pour spécifier l’emplacement des fichiers journaux**

1. Dans la fenêtre [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en afficher le contenu. Le fichier [!DNL Communications.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne nom du serveur pour [!DNL Communications.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Communications.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée sous la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL component]** pour en afficher le contenu.

1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL Servers]** pour en afficher le contenu. Plusieurs serveurs peuvent apparaître : Serveurs de fichiers, serveurs de journalisation, serveurs Init, serveurs d’état, serveurs d’envoi ou serveurs de réplication.

1. (Pour les [!DNL Sensor] sources de journal uniquement) Recherchez [!DNL LoggingServer], où [!DNL Sensor] écrit ses fichiers journaux à traiter par le serveur Data Workbench, puis cliquez sur son numéro pour afficher le menu. Modifiez le paramètre Répertoire des journaux pour refléter l’emplacement souhaité des fichiers journaux. Le répertoire de journal par défaut est le dossier Logs du répertoire d’installation du serveur Data Workbench.

   Ne modifiez aucun autre paramètre de la balise [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Recherchez FileServer qui spécifie l’emplacement des fichiers journaux. Plusieurs serveurs de fichiers peuvent être répertoriés sous Serveurs. Vous devrez donc peut-être consulter le contenu de plusieurs d’entre eux (en cliquant sur le numéro de serveur) pour trouver le serveur souhaité.
1. Modifiez les paramètres [!DNL Local Path] et URI pour FileServer afin de refléter l’emplacement des fichiers journaux. L’exemple suivant montre que les fichiers journaux résident dans le dossier Logs du répertoire d’installation du serveur Data Workbench :

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Si les paramètres [!DNL Local Path] et URI sont renseignés comme indiqué, vous pouvez accéder aux fichiers journaux sur le FSU à partir de n’importe quel serveur Data Workbench en cliquant sur [!DNL Logs] dans la balise [!DNL Server Files Manager].

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre de configuration, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la fenêtre [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Communications.cfg] dans la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]*** pour enregistrer les modifications apportées localement au FSU du serveur Data Workbench.

## Création d’un serveur de normalisation centralisé pour un cluster {#section-2c1f57b683f94cc193bc069e886bba28}

Si vous configurez votre profil de jeu de données pour qu’il s’exécute sur une grappe de serveurs Data Workbench, vous devez faire du FSU de la grappe le serveur sur lequel toutes les dimensions du profil sont construites.

Adobe recommande vivement que le FSU du cluster serve de serveur maître du cluster et de serveur de normalisation centralisé.

Pour faire du FSU le serveur de normalisation centralisé, vous devez ouvrir et modifier les fichiers [!DNL Communications.cfg] et [!DNL Cluster.cfg] sur le FSU.

**Pour faire de FSU le serveur de normalisation centralisé**

1. Ajoutez une entrée [!DNL NormalizeServer] au fichier [!DNL Communications.cfg] sur le FSU.

   >[!NOTE]
   >
   >Si vous avez installé le package de mise à jour complet pour le serveur Data Workbench version 5.0 ou ultérieure, le fichier [!DNL Communications.cfg] de votre FSU doit déjà comporter une entrée [!DNL NormalizeServer]. Vous pouvez suivre les étapes ci-dessous pour confirmer que l’entrée existe.

   1. Ouvrez le fichier [!DNL Communications.cfg] dans Data Workbench comme décrit dans [Spécification de l’emplacement des fichiers journaux](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. Cliquez sur **[!UICONTROL component]** pour afficher son contenu.
   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. Dans le paramètre URI pour la balise [!DNL NormalizeServer], saisissez [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la fenêtre [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Communications.cfg] dans la colonne [!DNL Temp], puis cliquez sur le nom **[!UICONTROL Save to]** *&lt;**[!UICONTROL server]*** pour enregistrer les modifications apportées localement au FSU du serveur Data Workbench.

1. Définissez le serveur de normalisation centralisé dans le fichier [!DNL Cluster.cfg] sur le serveur maître dans votre grappe de serveurs Data Workbench.

   >[!NOTE]
   >
   >Si le FSU sur lequel vous configurez votre serveur de normalisation centralisé n’est pas le serveur Data Workbench maître de votre grappe, vous devez ajouter les adresses IP des DPU de la grappe au groupe d’accès [!DNL Cluster Servers] dans le fichier [!DNL Access Control.cfg] du FSU. Pour obtenir des instructions sur l’ajout de serveurs au groupe [!DNL Cluster Servers], reportez-vous à la section Mise à jour du fichier de contrôle d’accès pour une grappe dans le *Guide d’installation et d’administration des produits serveur.*

   1. Ouvrez la [!DNL Profile Manager] dans votre profil de jeu de données, puis cliquez sur **[!UICONTROL Dataset]** pour afficher son contenu. Le fichier [!DNL Cluster.cfg] se trouve dans ce répertoire.

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
      >Lorsque vous saisissez le nom commun de FSU pour le paramètre SSL Server Common Name, le FSU utilise son fichier [!DNL .address] pour résoudre le nom commun. Pour plus d’informations sur le fichier [!DNL .address], consultez le *Guide d’installation et d’administration des produits serveur*.

   1. Enregistrez le fichier.
   1. Dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Cluster.cfg] dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** pour enregistrer les modifications apportées localement au profil du jeu de données.
