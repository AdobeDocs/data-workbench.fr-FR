---
description: Informations sur la configuration de la grappe sur Principal Insight Server, la mise à jour du fichier de contrôle d’accès pour une grappe, etc.
title: Configuration du serveur Insight maître pour la clusterisation
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configuration du serveur Insight maître pour la clusterisation{#configuring-the-master-insight-server-for-clustering}

{{eol}}

Informations sur la configuration de la grappe sur Principal Insight Server, la mise à jour du fichier de contrôle d’accès pour une grappe, etc.

Pour configurer la grappe, procédez comme suit sur le maître [!DNL Insight Server]:

* Ajouter le traitement [!DNL Insight Servers’] noms et adresses courants dans le fichier d’adresse.
* Ajoutez tous les [!DNL Insight Servers] au groupe Serveurs de grappe dans la variable [!DNL Access Control.cfg] fichier .

* Mettez à jour le [!DNL Synchronize.cfg] dans le répertoire Composants des serveurs de traitement pour qu’il pointe vers le maître. [!DNL Insight Server].

* Si nécessaire, modifiez la variable [!DNL Disk Files.cfg] dans le répertoire Composants pour les serveurs de traitement afin de spécifier l’emplacement de la variable [!DNL temp.db] sur le traitement [!DNL Insight Servers].

Pour effectuer ces étapes, vous devez connaître les noms communs (tels que spécifiés dans les certificats numériques de la personne [!DNL Insight Server]) et les adresses IP de chaque [!DNL Insight Server] dans la grappe. Si vous ne disposez pas déjà de ces informations, obtenez-les avant de procéder.

>[!NOTE]
>
>Les procédures décrites dans cette section nécessitent [!DNL Insight]. Si vous n’avez pas installé [!DNL Insight], suivez les instructions de la section **[!DNL Insight]Guide de l’utilisateur** avant de poursuivre.

## Ajout des serveurs Insight de traitement au fichier d’adresse {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Procédez comme suit pour ajouter le traitement [!DNL Insight Servers’] noms communs et adresses IP au fichier d’adresse sur le gabarit [!DNL Insight Server]. (Bien que le fichier d’adresse soit conservé et géré sur le gabarit [!DNL Insight Server], il est utilisé par tous les [!DNL Insight Servers] dans la grappe.)

>[!NOTE]
>
>L’exemple suivant suppose que le fichier d’adresse a déjà été configuré pour le maître. [!DNL Insight Server]. Si vous n’avez pas déjà ajouté le maître [!DNL Insight Server’s] Adresses IP du fichier d’adresse, procédez comme décrit dans la section [Définition de l’emplacement réseau du serveur](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) avant de commencer.

**Pour ajouter le traitement [!DNL Insight Servers] au fichier d’adresse**

1. Début [!DNL Insight] et chargez le profil Configuration (s’il n’est pas déjà ouvert) en cliquant avec le bouton droit de la souris sur la barre de titre, puis en cliquant sur **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .

1. Cliquez avec le bouton droit sur l’icône du gabarit **[!UICONTROL Insight Server]** et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], ouvrez le répertoire Adresses et procédez comme suit pour ouvrir le [!DNL Insight Server’s] fichier d’adresse :

   1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez le contenu de la variable [!DNL Locations] structure, puis développez NetworkLocation 0, Addresses et AddressDefinition.
1. Procédez comme suit pour ajouter une définition d’adresse à NetworkLocation 0 pour chaque traitement. [!DNL Insight Server] dans la grappe :

   1. Clic droit **[!UICONTROL AddressDefinition]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Dans le paramètre Name , spécifiez le traitement. [!DNL Insight Server’s] nom commun.
   1. Dans le paramètre Address (Adresse), spécifiez le traitement. [!DNL Insight Server’s] Adresse IP.

      Vous pouvez utiliser un astérisque comme caractère générique dans le champ Adresse , par exemple 10.10.116.&#42;, afin de simplifier la mise en grappe. Voir [Présentation des niveaux d’accès](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      L’exemple suivant définit un cluster contenant deux [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si les serveurs sont connectés à plusieurs réseaux, répétez l’étape 6 pour ajouter le traitement. [!DNL Insight Servers] à NetworkLocations pour ces réseaux.

   L’exemple suivant illustre une grappe de quatre [!DNL Insight Servers] joint à deux réseaux (&quot;Intranet de l&#39;entreprise&quot; et &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Mise à jour du fichier de contrôle d’accès pour une grappe {#section-fce1367d92a445168c35e9ca506e7d6b}

Pour utiliser [!DNL Insight Servers] dans une grappe, chaque [!DNL Insight Server] dans la grappe (y compris le maître [!DNL Insight Server]) doit appartenir à la population témoin d’accès des serveurs de cluster. Le groupe Serveurs de grappe identifie les serveurs (par adresse IP) autorisés à participer à la grappe. Bien que ce fichier soit conservé et géré sur le maître [!DNL Insight Server], il est utilisé par tous les [!DNL Insight Servers] dans la grappe.

**Pour modifier le fichier de contrôle d’accès**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .

1. Cliquez avec le bouton droit sur l’icône du gabarit [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], ouvrez le répertoire de contrôle d’accès.
1. Procédez comme suit pour ouvrir le [!DNL Access Control.cfg] fichier :

   1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure Groupes de contrôle d’accès, puis développez AccessGroup (serveurs de cluster).
1. Pour chaque [!DNL Insight Server] dans la grappe (y compris le maître [!DNL Insight Server]), procédez comme suit :

   1. Clic droit **[!UICONTROL Members]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Spécifiez la variable [!DNL Insight Server’s] Adresse IP (son adresse IP numérique, pas son nom). Si la variable [!DNL Insight Servers] sont connectés à plusieurs réseaux, ce AccessGroup ne doit contenir que les adresses internes que la variable [!DNL Insight Servers] pour la communication entre les serveurs dans la grappe.

      L’exemple suivant montre AccessGroup (serveurs de grappe) pour une grappe de quatre [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuration du fichier de synchronisation {#section-d23e751771c84da6bab6a34a8db867bc}

Vous pouvez utiliser la procédure suivante pour configurer la copie centrale de la [!DNL Synchronize.cfg] fichier . La copie centrale de ce fichier est conservée sur le maître. [!DNL Insight Server]. Le traitement [!DNL Insight Servers] dans la grappe, lancez la communication avec le maître [!DNL Insight Server] pour récupérer une copie mise à jour de ce fichier.

Le [!DNL Synchronize.cfg] spécifie l’emplacement du maître [!DNL Insight Server]. Il identifie également l’ensemble de fichiers administratifs que chacun des traitements [!DNL Insight Servers] dans la grappe récupère du maître [!DNL Insight Server]. Le traitement [!DNL Insight Servers] télécharger automatiquement ces fichiers à partir du maître [!DNL Insight Server] lorsqu’elles commencent. Ils récupèrent également dynamiquement les copies mises à jour de ces fichiers à partir du maître. [!DNL Insight Server] lorsque les fichiers changent.

>[!NOTE]
>
>Bien que vous configuriez la variable [!DNL Synchronize.cfg] sur le maître [!DNL Insight Server], le maître [!DNL Insight Server] lui-même n’utilise pas ce fichier. Vous mettez à jour ce fichier sur le maître. [!DNL Insight Server] afin qu’il soit correctement configuré lors du traitement [!DNL Insight Servers] récupérez le fichier .

**Pour mettre à jour le fichier Synchronize.cfg sur le gabarit[!DNL Insight Server]**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .

1. Cliquez avec le bouton droit sur l’icône du gabarit [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans [!DNL Server Files Manager], ouvrez le **[!UICONTROL Components]** pour le répertoire des serveurs de traitement.

1. Procédez comme suit pour ouvrir [!DNL Synchronize.cfg]:

   1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur le [!DNL Temp] coche et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure du composant.
1. Dans le paramètre Cluster Principal Server Address , spécifiez l’adresse IP du maître (Principal). **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Pour créer un journal qui enregistre chaque synchronisation entre le maître [!DNL Insight Server] et le traitement [!DNL Insight Servers], assurez-vous que le paramètre Activer le journal de synchronisation est défini sur &quot;true&quot;.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuration de l’emplacement du jeu de données (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Procédez comme suit si vous souhaitez que le traitement [!DNL Insight Servers] pour maintenir [!DNL temp.db] (le jeu de données) dans un répertoire ou un lecteur différent de l’emplacement par défaut ou si vous souhaitez distribuer [!DNL temp.db] sur plusieurs lecteurs.

>[!NOTE]
>
>Parce que le traitement [!DNL Insight Servers] tous partagent la même [!DNL Disk Files.cfg], ils doivent tous prendre en charge le ou les emplacements de fichier que vous indiquez dans ce fichier. Par exemple, si vous affectez [!DNL temp.db] à l&#39;E : lecteur, chaque traitement [!DNL Insight Server] dans la grappe doit comporter un E : lecteur.

**Pour configurer l’emplacement de temp.db**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .

1. Cliquez avec le bouton droit sur l’icône du gabarit [!DNL Insight Server] et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], ouvrez le **[!UICONTROL Components for Processing Servers]** répertoire .

1. Procédez comme suit pour ouvrir [!DNL Disk Files.cfg]:

   1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* et cliquez sur **[!UICONTROL Make Local]**.

   1. Cliquez avec le bouton droit de la souris sur la coche dans la [!DNL Temp]et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Développez la structure DiskSpaceManagerComponent , puis développez la liste Fichiers de disque .
1. Modifier l’entrée 0 pour modifier l’emplacement de la variable [!DNL temp.db] fichier .
1. Si vous souhaitez distribuer [!DNL temp.db] sur plusieurs lecteurs, suivez les étapes ci-dessous pour créer une entrée supplémentaire pour chaque lecteur supplémentaire.

   1. Clic droit **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Dans la nouvelle entrée, indiquez l’emplacement de votre choix. [!DNL temp.db] écrit.
   Les illustrations suivantes [!DNL temp.db] écrit sur quatre lecteurs.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
