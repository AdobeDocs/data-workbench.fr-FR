---
description: Informations sur la configuration de la grappe sur Principal Insight Server, la mise à jour du fichier de contrôle d’accès pour une grappe, etc.
title: Configuration du serveur Insight maître pour la clusterisation
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configuration du serveur Insight maître pour la clusterisation{#configuring-the-master-insight-server-for-clustering}

Informations sur la configuration de la grappe sur Principal Insight Server, la mise à jour du fichier de contrôle d’accès pour une grappe, etc.

Pour configurer la grappe, procédez comme suit sur le [!DNL Insight Server] maître :

* Ajoutez les [!DNL Insight Servers’] noms et adresses communs de traitement au fichier d&#39;adresse.
* Ajoutez tous les [!DNL Insight Servers] au groupe Serveurs de grappe dans le fichier [!DNL Access Control.cfg] .

* Mettez à jour le fichier [!DNL Synchronize.cfg] dans le répertoire Composants pour les serveurs de traitement afin qu’il pointe vers le [!DNL Insight Server] maître.

* Si nécessaire, modifiez le fichier [!DNL Disk Files.cfg] dans le répertoire Composants pour les serveurs de traitement afin de spécifier l’emplacement du fichier [!DNL temp.db] sur le fichier de traitement [!DNL Insight Servers].

Pour effectuer ces étapes, vous devez connaître les noms communs (tels que spécifiés dans les certificats numériques pour chaque [!DNL Insight Server]) et les adresses IP de chaque [!DNL Insight Server] de la grappe. Si vous ne disposez pas déjà de ces informations, obtenez-les avant de procéder.

>[!NOTE]
>
>Les procédures décrites dans cette section requièrent [!DNL Insight]. Si vous n’avez pas installé [!DNL Insight], suivez les instructions du **[!DNL Insight]Guide de l’utilisateur** avant de continuer.

## Ajout des serveurs Insight de traitement au fichier d’adresse {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Procédez comme suit pour ajouter les [!DNL Insight Servers’] noms communs et adresses IP de traitement au fichier d’adresse sur le [!DNL Insight Server] maître. (Bien que le fichier d’adresse soit conservé et géré sur le [!DNL Insight Server] maître, il est utilisé par tous les [!DNL Insight Servers] de la grappe.)

>[!NOTE]
>
>L’exemple suivant suppose que le fichier d’adresse a déjà été configuré pour le [!DNL Insight Server] maître. Si vous n’avez pas encore ajouté l’adresse IP [!DNL Insight Server’s] maître au fichier d’adresse, exécutez la procédure décrite dans [Définition de l’emplacement réseau du serveur](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) avant de commencer.

**Ajout du traitement  [!DNL Insight Servers] au fichier d’adresse**

1. Démarrez [!DNL Insight] et chargez le profil Configuration (s’il n’est pas déjà ouvert) en cliquant avec le bouton droit de la souris sur la barre de titre et en cliquant sur **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit **[!UICONTROL Insight Server]** et cliquez sur **[!UICONTROL Server Files]**.

1. Dans la balise [!DNL Server Files Manager], ouvrez le répertoire Adresses et procédez comme suit pour ouvrir le fichier d’adresse [!DNL Insight Server’s] :

   1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la coche dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez le contenu de la structure [!DNL Locations], puis développez NetworkLocation 0, Addresses et AddressDefinition.
1. Procédez comme suit pour ajouter une valeur AddressDefinition à NetworkLocation 0 pour chaque traitement [!DNL Insight Server] dans la grappe :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL AddressDefinition]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Dans le paramètre Name , indiquez le nom commun [!DNL Insight Server’s] de traitement.
   1. Dans le paramètre Address , indiquez l’adresse IP de traitement [!DNL Insight Server’s].

      Vous pouvez utiliser un astérisque comme caractère générique dans le champ Adresse , par exemple 10.10.116.*, pour simplifier la mise en grappe. Voir [Présentation des niveaux d’accès](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      L’exemple suivant définit un cluster contenant deux [!DNL Insight Servers] :

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si les serveurs sont connectés à plusieurs réseaux, répétez l’étape 6 pour ajouter le traitement [!DNL Insight Servers] aux NetworkLocations de ces réseaux.

   L’exemple suivant illustre un cluster de quatre [!DNL Insight Servers] associés à deux réseaux (&quot;Intranet de l’entreprise&quot; et &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.

## Mise à jour du fichier de contrôle d’accès pour un cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Pour utiliser [!DNL Insight Servers] dans une grappe, chaque [!DNL Insight Server] de la grappe (y compris le [!DNL Insight Server] maître) doit appartenir à la population témoin d’accès des serveurs de la grappe. Le groupe Serveurs de grappe identifie les serveurs (par adresse IP) autorisés à participer à la grappe. Bien que ce fichier soit géré sur le [!DNL Insight Server] maître, il est utilisé par tous les [!DNL Insight Servers] de la grappe.

**Pour modifier le fichier de contrôle d’accès**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], ouvrez le répertoire de contrôle d’accès.
1. Pour ouvrir le fichier [!DNL Access Control.cfg], procédez comme suit :

   1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la coche dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure Groupes de contrôle d’accès, puis développez AccessGroup (serveurs de cluster).
1. Pour chaque [!DNL Insight Server] de la grappe (y compris le [!DNL Insight Server] maître), procédez comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Members]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Indiquez l’adresse IP [!DNL Insight Server’s] (son adresse IP numérique et non son nom). Si [!DNL Insight Servers] est connecté à plusieurs réseaux, AccessGroup ne doit contenir que les adresses internes utilisées par [!DNL Insight Servers] pour la communication entre serveurs dans la grappe.

      Vous trouverez ci-dessous le groupe Access (serveurs de cluster) pour un cluster de quatre [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.

## Configuration du fichier de synchronisation {#section-d23e751771c84da6bab6a34a8db867bc}

Vous pouvez suivre la procédure suivante pour configurer la copie centrale du fichier [!DNL Synchronize.cfg]. La copie centrale de ce fichier est conservée sur le [!DNL Insight Server] maître. Le traitement [!DNL Insight Servers] de la grappe lance une communication avec le [!DNL Insight Server] maître pour récupérer une copie mise à jour de ce fichier.

Le fichier [!DNL Synchronize.cfg] spécifie l’emplacement du [!DNL Insight Server] maître. Il identifie également l’ensemble de fichiers administratifs que chacun des [!DNL Insight Servers] de traitement de la grappe récupère du [!DNL Insight Server] maître. Le traitement [!DNL Insight Servers] télécharge automatiquement ces fichiers à partir du [!DNL Insight Server] maître lorsqu’ils démarrent. Ils récupèrent également dynamiquement les copies mises à jour de ces fichiers à partir du [!DNL Insight Server] maître lorsque les fichiers changent.

>[!NOTE]
>
>Bien que vous configuriez le fichier [!DNL Synchronize.cfg] sur le [!DNL Insight Server] maître, le [!DNL Insight Server] maître lui-même n’utilise pas ce fichier. Vous mettez à jour ce fichier sur le [!DNL Insight Server] maître afin qu’il soit correctement configuré lorsque le traitement [!DNL Insight Servers] récupère le fichier.

**Pour mettre à jour le fichier Synchronize.cfg sur le gabarit[!DNL Insight Server]**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire **[!UICONTROL Components]** pour les serveurs de traitement.

1. Pour ouvrir [!DNL Synchronize.cfg], procédez comme suit :

   1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure du composant.
1. Dans le paramètre Cluster Principal Server Address , spécifiez l’adresse IP du maître (Principal) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Pour créer un journal qui enregistre chaque synchronisation entre le [!DNL Insight Server] maître et le [!DNL Insight Servers] traitement, assurez-vous que le paramètre Activer le journal de synchronisation est défini sur &quot;true&quot;.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.

## Configuration de l’emplacement du jeu de données (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Effectuez la procédure suivante si vous souhaitez que le traitement [!DNL Insight Servers] conserve [!DNL temp.db] (le jeu de données) dans un répertoire ou un lecteur différent de l’emplacement par défaut ou si vous souhaitez distribuer [!DNL temp.db] sur plusieurs lecteurs.

>[!NOTE]
>
>Comme le [!DNL Insight Servers] traitement partage tous le même [!DNL Disk Files.cfg], il doit tous prendre en charge le ou les emplacements de fichier que vous indiquez dans ce fichier. Par exemple, si vous affectez [!DNL temp.db] à E : pour chaque lecteur, chaque [!DNL Insight Server] de traitement de la grappe doit avoir une E : lecteur.

**Pour configurer l’emplacement de temp.db**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du gabarit [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le répertoire **[!UICONTROL Components for Processing Servers]**.

1. Pour ouvrir [!DNL Disk Files.cfg], procédez comme suit :

   1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit sur la coche dans la colonne [!DNL Temp]et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure DiskSpaceManagerComponent , puis développez la liste Fichiers de disque .
1. Modifiez l’entrée 0 pour modifier l’emplacement du fichier [!DNL temp.db].
1. Si vous souhaitez distribuer [!DNL temp.db] sur plusieurs lecteurs, suivez les étapes ci-dessous pour créer une entrée supplémentaire pour chaque lecteur supplémentaire.

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Dans la nouvelle entrée, indiquez l’emplacement où [!DNL temp.db] doit être écrit.
   L’exemple suivant montre [!DNL temp.db] écrit sur quatre lecteurs.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
