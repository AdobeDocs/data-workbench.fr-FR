---
description: Informations sur la configuration de la grappe sur le serveur Master Insight Server, la mise à jour du fichier de  d’une grappe, etc.
solution: Insight
title: Configuration de Master Insight Server pour la mise en grappe
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# Configuration de Master Insight Server pour la mise en grappe{#configuring-the-master-insight-server-for-clustering}

Informations sur la configuration de la grappe sur le serveur Master Insight Server, la mise à jour du fichier de  d’une grappe, etc.

Pour configurer la grappe, procédez comme suit sur le modèle [!DNL Insight Server]:

* Ajouter les noms et adresses [!DNL Insight Servers’] courants dans le fichier d’adresse.
* Ajouter tous les éléments [!DNL Insight Servers] au groupe Serveurs de cluster dans le [!DNL Access Control.cfg] fichier.

* Mettez à jour le [!DNL Synchronize.cfg] fichier dans le répertoire Composants pour les serveurs de traitement afin qu’il pointe vers le fichier maître [!DNL Insight Server].

* Si nécessaire, modifiez le [!DNL Disk Files.cfg] fichier dans le répertoire Composants pour les serveurs de traitement afin de spécifier l’emplacement du [!DNL temp.db] fichier sur le traitement [!DNL Insight Servers].

Pour effectuer ces étapes, vous devez connaître les noms courants (tels qu’ils sont indiqués dans les certificats numériques de l’individu [!DNL Insight Server]) et les adresses IP de chacun [!DNL Insight Server] des éléments de la grappe. Si vous ne disposez pas déjà de ces informations, obtenez-les avant de procéder.

>[!NOTE]
>
>Les procédures décrites dans cette section exigent [!DNL Insight]. Si vous n’avez pas encore installé [!DNL Insight], suivez les instructions du **[!DNL Insight]Guide **de l’utilisateur avant de continuer.

## Ajout des serveurs Processing Insight au fichier d&#39;adresse {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Procédez comme suit pour ajouter les noms [!DNL Insight Servers’] courants de traitement et les adresses IP au fichier d’adresse sur le gabarit [!DNL Insight Server]. (Bien que le fichier d’adresse soit conservé et géré sur le maître [!DNL Insight Server], il est utilisé par tous les [!DNL Insight Servers] membres de la grappe.)

>[!NOTE]
>
>Ce qui suit suppose que le fichier d&#39;adresse a déjà été configuré pour le gabarit [!DNL Insight Server]. Si vous n&#39;avez pas encore ajouté l&#39;adresse(s) [!DNL Insight Server’s] IP principale(s) au fichier d&#39;adresse, suivez la procédure décrite à la section [Définition de l&#39;emplacement](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) réseau du serveur avant de commencer.

**Pour ajouter le traitement[!DNL Insight Servers]au fichier d’adresse**

1. [!DNL Insight] et chargez le de configuration (s’il n’est pas déjà ouvert) en cliquant avec le bouton droit sur la barre de titre et en cliquant sur **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit **[!UICONTROL Insight Server]** , puis cliquez **[!UICONTROL Server Files]**.

1. Dans la [!DNL Server Files Manager]section, ouvrez le répertoire Adresses et procédez comme suit pour ouvrir le fichier [!DNL Insight Server’s] d’adresse :

   1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur, puis cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez le contenu de la [!DNL Locations] structure, puis développez NetworkLocation 0, Addresses et AddressDefinition.
1. Procédez comme suit pour ajouter une valeur AddressDefinition à NetworkLocation 0 pour chaque traitement [!DNL Insight Server] de la grappe :

   1. Cliquez avec le bouton droit de la souris **[!UICONTROL AddressDefinition]** , puis cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Dans le paramètre Name, spécifiez le nom [!DNL Insight Server’s] commun de traitement.
   1. Dans le paramètre Address, spécifiez l’adresse [!DNL Insight Server’s] IP de traitement.

      Vous pouvez utiliser un astérisque comme caractère générique dans le champ Adresse, par exemple 10.10.116.*, pour simplifier la mise en grappe. Voir [Présentation des niveaux](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)d’accès.

      L’exemple suivant définit une grappe contenant deux [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si les serveurs sont connectés à plusieurs réseaux, répétez l’étape 6 pour ajouter le traitement [!DNL Insight Servers] aux NetworkLocations de ces réseaux.

   L’exemple suivant illustre un cluster de quatre [!DNL Insight Servers] rattachés à deux réseaux (&quot;Intranet de l’entreprise&quot; et &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Mise à jour du fichier  pour une grappe {#section-fce1367d92a445168c35e9ca506e7d6b}

Pour une utilisation [!DNL Insight Servers] dans une grappe, chaque [!DNL Insight Server] grappe (y compris le maître [!DNL Insight Server]) doit appartenir au groupe de des serveurs de cluster. Le groupe Serveurs de cluster identifie les serveurs (par adresse IP) autorisés à participer à la grappe. Bien que ce fichier soit conservé et géré sur le maître [!DNL Insight Server], il est utilisé par tous les [!DNL Insight Servers] membres de la grappe.

**Pour modifier le fichier de  du**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit [!DNL Insight Server] , puis cliquez **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire  du.
1. Procédez comme suit pour ouvrir le [!DNL Access Control.cfg] fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur, puis cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure des groupes , puis développez AccessGroup (serveurs de cluster).
1. Pour chaque [!DNL Insight Server] élément de la grappe (y compris le maître [!DNL Insight Server]), procédez comme suit :

   1. Cliquez avec le bouton droit de la souris **[!UICONTROL Members]** , puis cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Spécifiez l’adresse [!DNL Insight Server’s] IP (son adresse IP numérique et non son nom). Si le [!DNL Insight Servers] groupe AccessGroup est connecté à plusieurs réseaux, il ne doit contenir que les adresses internes [!DNL Insight Servers] utilisées pour la communication entre serveurs au sein de la grappe.

      L&#39;exemple suivant montre le groupe AccessGroup (serveurs de cluster) pour une grappe de quatre [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuration du fichier de synchronisation {#section-d23e751771c84da6bab6a34a8db867bc}

Vous pouvez suivre la procédure suivante pour configurer la copie centrale du [!DNL Synchronize.cfg] fichier. La copie centrale de ce fichier est conservée sur le gabarit [!DNL Insight Server]. Le traitement [!DNL Insight Servers] dans la grappe lance une communication avec le maître [!DNL Insight Server] pour récupérer une copie mise à jour de ce fichier.

Le [!DNL Synchronize.cfg] fichier spécifie l’emplacement du gabarit [!DNL Insight Server]. Il identifie également l’ensemble de fichiers administratifs que chaque traitement [!DNL Insight Servers] de la grappe récupère du maître [!DNL Insight Server]. Le traitement télécharge [!DNL Insight Servers] automatiquement ces fichiers du fichier maître [!DNL Insight Server] lorsqu’ils . Ils récupèrent également dynamiquement des copies mises à jour de ces fichiers à partir du fichier maître [!DNL Insight Server] lorsque les fichiers changent.

>[!NOTE]
>
>Bien que vous configuriez le [!DNL Synchronize.cfg] fichier sur le fichier maître [!DNL Insight Server], le fichier maître [!DNL Insight Server] lui-même n’utilise pas ce fichier. Vous mettez à jour ce fichier sur le fichier maître [!DNL Insight Server] afin qu’il soit correctement configuré lorsque le traitement [!DNL Insight Servers] récupère le fichier.

**Pour mettre à jour le fichier Synchronize.cfg sur le fichier maître[!DNL Insight Server]**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit [!DNL Insight Server] , puis cliquez **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire **[!UICONTROL Components]** des serveurs de traitement.

1. Procédez comme suit pour ouvrir [!DNL Synchronize.cfg]:

   1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur, puis cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la [!DNL Temp] coche, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure des composants.
1. Dans le paramètre d’adresse du serveur principal de cluster, spécifiez l’adresse IP du serveur principal (principal) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Pour créer un journal qui enregistre chaque synchronisation entre le maître [!DNL Insight Server] et le traitement [!DNL Insight Servers], assurez-vous que le paramètre Activer le journal de synchronisation est défini sur &quot;true&quot;.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager]la colonne, cliquez avec le bouton droit de la souris sur la coche du fichier, puis cliquez sur [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

## Configuration de l&#39;emplacement du jeu de données (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Procédez comme suit si vous souhaitez que le traitement [!DNL Insight Servers] conserve [!DNL temp.db] (le jeu de données) dans un répertoire ou un lecteur différent de l&#39;emplacement par défaut ou si vous souhaitez répartir [!DNL temp.db] sur plusieurs lecteurs.

>[!NOTE]
>
>Puisque le traitement [!DNL Insight Servers] est le même [!DNL Disk Files.cfg], ils doivent tous prendre en charge l’emplacement du ou des fichiers que vous spécifiez dans ce fichier. Par exemple, si vous affectez [!DNL temp.db] à E : chaque traitement [!DNL Insight Server] de la grappe doit avoir un E: lecteur.

**Pour configurer l’emplacement de temp.db**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit [!DNL Insight Server] , puis cliquez **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le **[!UICONTROL Components for Processing Servers]** répertoire.

1. Procédez comme suit pour ouvrir [!DNL Disk Files.cfg]:

   1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur, puis cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche de la [!DNL Temp]colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure DiskSpaceManagerComponent, puis développez le Disk Files.
1. Modifiez l’entrée 0 pour modifier l’emplacement du [!DNL temp.db] fichier.
1. Si vous souhaitez répartir [!DNL temp.db] sur plusieurs lecteurs, suivez les étapes ci-dessous pour créer une entrée supplémentaire pour chaque lecteur supplémentaire.

   1. Cliquez avec le bouton droit de la souris **[!UICONTROL Disk Files]** , puis cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Dans la nouvelle entrée, spécifiez l’emplacement où vous souhaitez [!DNL temp.db] écrire.
   Les illustrations suivantes sont [!DNL temp.db] écrites sur quatre lecteurs.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager]la colonne, cliquez avec le bouton droit de la souris sur la coche du fichier, puis cliquez sur [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

