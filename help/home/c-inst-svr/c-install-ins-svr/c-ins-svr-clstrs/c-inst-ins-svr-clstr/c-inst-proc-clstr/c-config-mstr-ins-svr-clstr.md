---
description: Informations sur la configuration de la grappe sur Principal Insight Server, la mise à jour du fichier de contrôle d'accès pour une grappe, etc.
title: Configuration du serveur Insight maître pour la clusterisation
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configuration du serveur Insight maître pour la clusterisation{#configuring-the-master-insight-server-for-clustering}

Informations sur la configuration de la grappe sur Principal Insight Server, la mise à jour du fichier de contrôle d&#39;accès pour une grappe, etc.

Pour configurer la grappe, effectuez les étapes suivantes sur le modèle [!DNL Insight Server] :

* Ajoutez les noms et adresses courants [!DNL Insight Servers’] de traitement dans le fichier d&#39;adresse.
* Ajoutez tous les [!DNL Insight Servers] au groupe Serveurs de cluster dans le fichier [!DNL Access Control.cfg].

* Mettez à jour le fichier [!DNL Synchronize.cfg] dans le répertoire Composants pour les serveurs de traitement afin qu’il pointe vers le fichier maître [!DNL Insight Server].

* Si nécessaire, modifiez le fichier [!DNL Disk Files.cfg] dans le répertoire Composants pour serveurs de traitement afin de spécifier l’emplacement du fichier [!DNL temp.db] sur le traitement [!DNL Insight Servers].

Pour effectuer ces étapes, vous devez connaître les noms communs (tels que spécifiés dans les certificats numériques pour l&#39;individu [!DNL Insight Server]) et les adresses IP de chaque [!DNL Insight Server] de la grappe. Si vous ne disposez pas déjà de ces informations, obtenez-les avant de continuer.

>[!NOTE]
>
>Les procédures décrites dans cette section nécessitent [!DNL Insight]. Si vous n&#39;avez pas installé [!DNL Insight], suivez les instructions du **[!DNL Insight]Guide de l&#39;utilisateur** avant de continuer.

## Ajouter les serveurs Processing Insight au fichier d&#39;adresse {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Procédez comme suit pour ajouter les noms courants et adresses IP [!DNL Insight Servers’] de traitement au fichier d&#39;adresse sur le fichier d&#39;adresse maître [!DNL Insight Server]. (Bien que le fichier d&#39;adresse soit conservé et géré sur le fichier maître [!DNL Insight Server], il est utilisé par tous les [!DNL Insight Servers] de la grappe.)

>[!NOTE]
>
>Ce qui suit suppose que le fichier d&#39;adresse a déjà été configuré pour le fichier maître [!DNL Insight Server]. Si vous n&#39;avez pas encore ajouté l&#39;adresse IP principale [!DNL Insight Server’s] au fichier d&#39;adresse, suivez la procédure décrite dans [Définition de l&#39;emplacement réseau du serveur](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) avant de commencer.

**Pour ajouter le traitement  [!DNL Insight Servers] au fichier d&#39;adresse**

1. Début [!DNL Insight] et chargez le profil de configuration (s’il n’est pas déjà ouvert) en cliquant avec le bouton droit sur la barre de titre et en cliquant sur **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.

1. Cliquez avec le bouton droit de la souris sur l’icône du masque **[!UICONTROL Insight Server]** et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le répertoire [!DNL Server Files Manager], ouvrez le répertoire Adresses et procédez comme suit pour ouvrir le fichier d&#39;adresse [!DNL Insight Server’s] :

   1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la coche de la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez le contenu de la structure [!DNL Locations], puis développez NetworkLocation 0, Addresses et AddressDefinition.
1. Procédez comme suit pour ajouter une valeur AddressDefinition à NetworkLocation 0 pour chaque traitement [!DNL Insight Server] dans la grappe :

   1. Cliquez avec le bouton droit **[!UICONTROL AddressDefinition]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Dans le paramètre Name, spécifiez le nom commun de traitement [!DNL Insight Server’s].
   1. Dans le paramètre Address, spécifiez l&#39;adresse IP de traitement [!DNL Insight Server’s].

      Vous pouvez utiliser un astérisque comme caractère générique dans le champ Adresse, par exemple 10.10.116.*, pour simplifier la mise en grappe. Voir [Comprendre les niveaux d&#39;accès](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      L&#39;exemple suivant définit un cluster contenant deux [!DNL Insight Servers] :

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si les serveurs sont connectés à plusieurs réseaux, répétez l’étape 6 pour ajouter le traitement [!DNL Insight Servers] à NetworkLocations pour ces réseaux.

   L&#39;exemple suivant montre un cluster de quatre [!DNL Insight Servers] rattachés à deux réseaux (&quot;Intranet de l&#39;entreprise&quot; et &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Mise à jour du fichier Contrôle d&#39;accès pour une grappe {#section-fce1367d92a445168c35e9ca506e7d6b}

Pour utiliser [!DNL Insight Servers] dans un cluster, chaque [!DNL Insight Server] du cluster (y compris le maître [!DNL Insight Server]) doit appartenir au groupe de contrôles d&#39;accès Serveurs de cluster. Le groupe Serveurs de cluster identifie les serveurs (par adresse IP) autorisés à participer à la grappe. Bien que ce fichier soit conservé et géré sur le [!DNL Insight Server] maître, il est utilisé par tous les [!DNL Insight Servers] de la grappe.

**Pour modifier le fichier de contrôle d&#39;accès**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.

1. Cliquez avec le bouton droit de la souris sur l’icône du masque [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire de Contrôle d&#39;accès.
1. Pour ouvrir le fichier [!DNL Access Control.cfg], procédez comme suit :

   1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la coche de la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure Groupes de Contrôles d&#39;accès, puis le groupe Access (serveurs de cluster).
1. Pour chaque [!DNL Insight Server] de la grappe (y compris le maître [!DNL Insight Server]), procédez comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL Members]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Spécifiez l&#39;adresse IP [!DNL Insight Server’s] (son adresse IP numérique, et non son nom). Si [!DNL Insight Servers] est connecté à plusieurs réseaux, ce groupe AccessGroup ne doit contenir que les adresses internes utilisées par [!DNL Insight Servers] pour la communication entre serveurs au sein de la grappe.

      L&#39;exemple suivant montre le groupe AccessGroup (serveurs de cluster) pour un cluster de quatre [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Configuration du fichier de synchronisation {#section-d23e751771c84da6bab6a34a8db867bc}

Vous pouvez utiliser la procédure suivante pour configurer la copie centrale du fichier [!DNL Synchronize.cfg]. La copie centrale de ce fichier est conservée sur le fichier maître [!DNL Insight Server]. Le traitement [!DNL Insight Servers] dans le cluster initie la communication avec le maître [!DNL Insight Server] pour récupérer une copie mise à jour de ce fichier.

Le fichier [!DNL Synchronize.cfg] spécifie l&#39;emplacement du fichier maître [!DNL Insight Server]. Il identifie également l&#39;ensemble de fichiers administratifs que chacun des fichiers de traitement [!DNL Insight Servers] de la grappe récupère à partir de l&#39;élément maître [!DNL Insight Server]. Le traitement [!DNL Insight Servers] télécharge automatiquement ces fichiers à partir du fichier maître [!DNL Insight Server] lorsqu&#39;ils sont débuts. Ils récupèrent également de manière dynamique des copies mises à jour de ces fichiers à partir du fichier maître [!DNL Insight Server] lorsque les fichiers changent.

>[!NOTE]
>
>Bien que vous configuriez le fichier [!DNL Synchronize.cfg] sur le fichier maître [!DNL Insight Server], le fichier maître [!DNL Insight Server] lui-même n&#39;utilise pas ce fichier. Vous mettez à jour ce fichier sur le fichier maître [!DNL Insight Server] afin qu&#39;il soit correctement configuré lorsque le traitement [!DNL Insight Servers] récupère le fichier.

**Pour mettre à jour le fichier Synchronize.cfg sur le fichier maître[!DNL Insight Server]**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.

1. Cliquez avec le bouton droit de la souris sur l’icône du masque [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire **[!UICONTROL Components]** pour les serveurs de traitement.

1. Pour ouvrir [!DNL Synchronize.cfg], procédez comme suit :

   1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure des composants.
1. Dans le paramètre Cluster Principal Server Address, spécifiez l&#39;adresse IP du maître (Principal) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Pour créer un journal qui enregistre chaque fois que la synchronisation a lieu entre l&#39;élément maître [!DNL Insight Server] et l&#39;élément de traitement [!DNL Insight Servers], assurez-vous que le paramètre Activer le journal de synchronisation est défini sur &quot;true&quot;.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Configuration de l’emplacement du jeu de données (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Procédez comme suit si vous souhaitez que le traitement [!DNL Insight Servers] conserve [!DNL temp.db] (le jeu de données) dans un répertoire ou un lecteur différent de l&#39;emplacement par défaut ou si vous souhaitez distribuer [!DNL temp.db] sur plusieurs lecteurs.

>[!NOTE]
>
>Puisque le traitement [!DNL Insight Servers] partage tous le même [!DNL Disk Files.cfg], ils doivent tous prendre en charge le ou les emplacements de fichier que vous spécifiez dans ce fichier. Par exemple, si vous affectez [!DNL temp.db] à E : lecteur, chaque traitement [!DNL Insight Server] de la grappe doit comporter un E : lecteur.

**Pour configurer l’emplacement de temp.db**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.

1. Cliquez avec le bouton droit de la souris sur l’icône du masque [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire **[!UICONTROL Components for Processing Servers]**.

1. Pour ouvrir [!DNL Disk Files.cfg], procédez comme suit :

   1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la coche de la colonne [!DNL Temp]et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure DiskSpaceManagerComponent, puis développez la liste Disk Files.
1. Modifiez l&#39;entrée 0 pour modifier l&#39;emplacement du fichier [!DNL temp.db].
1. Si vous souhaitez distribuer [!DNL temp.db] sur plusieurs lecteurs, suivez les étapes ci-dessous pour créer une entrée supplémentaire pour chaque lecteur supplémentaire.

   1. Cliquez avec le bouton droit **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Dans la nouvelle entrée, spécifiez l&#39;emplacement où [!DNL temp.db] doit être écrit.
   L&#39;exemple suivant montre [!DNL temp.db] écrit sur quatre lecteurs.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
