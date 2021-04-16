---
description: Vous pouvez ajouter un FSU de serveur Insight à une grappe existante si vous souhaitez stocker des données source sur un serveur de fichiers supplémentaire ou si vous souhaitez configurer une sauvegarde pour votre serveur maître Insight Server.
title: Ajout d’un FSU de serveur Insight à un cluster existant
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Ajout d’un FSU de serveur Insight à un cluster existant{#adding-an-insight-server-fsu-to-an-existing-cluster}

Vous pouvez ajouter un FSU de serveur Insight à une grappe existante si vous souhaitez stocker des données source sur un serveur de fichiers supplémentaire ou si vous souhaitez configurer une sauvegarde pour votre serveur maître Insight Server.

Pour ajouter une unité d&#39;analyse fonctionnelle [!DNL Insight Server] à une grappe existante, vous devez effectuer les procédures suivantes :

1. [Mise à jour des fichiers de configuration sur le serveur de Principal](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Installation du nouveau FSU du serveur Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configuration de l’unité de gestion des stocks du nouveau serveur Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Mise à jour des fichiers de configuration sur le serveur de Principal {#section-b5f21f2edb35493da4475de2cdeefca1}

Dans [!DNL Insight], ouvrez le [!DNL Server Files Manager] pour votre [!DNL Insight Server] maître (généralement un [!DNL Insight Server] FSU) et effectuez les opérations suivantes pour chaque FSU que vous souhaitez ajouter à la grappe :

1. Modifiez le fichier d&#39;adresse sur le fichier maître [!DNL Insight Server] pour inclure le nom et l&#39;adresse du nouveau FSU, comme décrit dans [Ajouter les serveurs Processing Insight au fichier d&#39;adresse](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Ajoutez le nom et l’adresse du nouveau FSU au groupe dans lequel l’élément [!DNL Insight Servers] actuel de votre grappe est répertorié.

1. Modifiez le fichier de contrôle d&#39;accès sur le fichier maître [!DNL Insight Server] afin d&#39;inclure l&#39;adresse IP du nouveau FSU, comme décrit dans [Mise à jour du fichier de Contrôle d&#39;accès pour un cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installation de l’unité de gestion des stocks du nouveau serveur Insight {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Sur votre FSU actuel, créez un fichier zip du répertoire d&#39;installation [!DNL Insight Server] et copiez le fichier dans le nouveau FSU.
1. Décompressez le fichier à l&#39;emplacement où vous souhaitez placer le logiciel [!DNL Insight Server].
1. Téléchargez et installez le certificat numérique pour le nouveau FSU comme décrit dans [Téléchargement et installation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Définissez les paramètres d&#39;utilisation de la mémoire Windows sur le nouveau FSU.
1. Modifiez le nom du fichier [!DNL .address] pour refléter le nom du FSU, comme décrit dans la section [Définition de l&#39;emplacement réseau du serveur](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Si la structure du lecteur sur le nouveau FSU est différente de celle de l&#39;Principal FSU, vous devez modifier le fichier [!DNL Disk Files.cfg].

   1. Ouvrez le fichier [!DNL Disk Files.cfg] sur le nouveau FSU.
   1. Mettez à jour les paramètres pour qu&#39;ils correspondent aux lecteurs du FSU Principal, comme décrit dans [Surveillance de l&#39;espace de données des ensembles de données](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Enregistrez le fichier localement et sur le serveur.

1. Enregistrez [!DNL Insight Server] en tant que service Windows sur le nouvel ordinateur FSU comme décrit dans [Enregistrement d’Insight Server en tant que service Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Répétez les étapes 1 à 6 pour chaque unité d’exécution de service (FSU) supplémentaire que vous ajoutez à la grappe.

## Configuration de la FSU du nouveau serveur Insight {#section-c39334c5bd754d5b98d41ad094333108}

Les procédures suivantes fournissent des instructions pour des tâches de configuration spécifiques. Suivez les instructions appropriées à votre mise en oeuvre du nouveau FSU.

**Pour configurer l&#39;unité de traitement des données source pour l&#39;enregistrement de données**

Si le nouvel UFS stocke des données source supplémentaires pour le jeu de données s&#39;exécutant sur la grappe, vous devez terminer le processus de configuration du serveur de fichiers comme décrit dans la section Configuration d&#39;une unité de serveur de fichiers [!DNL Insight Server] du chapitre Fichier de configuration de traitement du journal du *Guide de configuration des jeux de données*.

**Pour faire de la nouvelle unité de sauvegarde la sauvegarde de la  [!DNL Insight Server] unité de sauvegarde principale**

Si vous souhaitez faire de la nouvelle FSU la sauvegarde de l&#39;unité de sauvegarde principale [!DNL Insight Server] (qui sert d&#39;unité de sauvegarde pour la grappe), vous devez modifier le fichier de synchronisation sur la nouvelle unité de sauvegarde (FSU) afin qu&#39;elle se synchronise avec l&#39;unité de sauvegarde principale.

1. Dans l&#39;unité de sauvegarde [!DNL Insight Server] FSU, utilisez [!DNL Server Files Manager] pour copier le fichier [!DNL Synchronize.cfg] du dossier [!DNL Components for Processing Servers] dans le dossier [!DNL Components].

1. Ouvrez le fichier [!DNL Synchronize.cfg] (dans le dossier [!DNL Components]) dans [!DNL Insight].

1. Recherchez le paramètre SynchronizeDir qui spécifie l’emplacement du répertoire Composants. Il peut y avoir plusieurs répertoires de synchronisation répertoriés sous Répertoires, vous devrez peut-être en vue le contenu pour plusieurs d&#39;entre eux (en cliquant sur le numéro de serveur) pour trouver le serveur souhaité.
1. Modifiez l&#39;entrée SynchronizeDir et ajoutez une seconde entrée SynchronizeDir, comme illustré dans l&#39;exemple ci-dessous.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Enregistrez le fichier modifié sous un nouveau nom tel que [!DNL FSU_Synchronize.cfg] afin de ne pas le confondre avec les fichiers [!DNL Synchronize.cfg] des unités de traitement de données de la grappe.

1. Utilisez [!DNL Server Files Manager] pour enregistrer la copie locale du fichier renommé sur le serveur. Le FSU de sauvegarde télécharge les fichiers des répertoires identifiés à partir du FSU maître [!DNL Insight Server] et récupère dynamiquement des copies mises à jour de ces fichiers à partir du FSU maître [!DNL Insight Server] lorsqu&#39;ils changent.
