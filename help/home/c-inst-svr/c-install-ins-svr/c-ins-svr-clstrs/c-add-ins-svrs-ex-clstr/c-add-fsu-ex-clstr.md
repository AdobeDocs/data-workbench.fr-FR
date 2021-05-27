---
description: Vous pouvez ajouter un FSU de serveur Insight à une grappe existante si vous souhaitez stocker des données source sur un serveur de fichiers supplémentaire ou si vous souhaitez configurer une sauvegarde pour votre serveur Insight maître.
title: Ajout d’un FSU de serveur Insight à un cluster existant
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Ajout d’un FSU de serveur Insight à un cluster existant{#adding-an-insight-server-fsu-to-an-existing-cluster}

Vous pouvez ajouter un FSU de serveur Insight à une grappe existante si vous souhaitez stocker des données source sur un serveur de fichiers supplémentaire ou si vous souhaitez configurer une sauvegarde pour votre serveur Insight maître.

Pour ajouter un FSU [!DNL Insight Server] à une grappe existante, vous devez effectuer les procédures suivantes :

1. [Mise à jour des fichiers de configuration sur le serveur Principal](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Installation du FSU du nouveau serveur Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configuration du FSU du nouveau serveur Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Mise à jour des fichiers de configuration sur le serveur Principal {#section-b5f21f2edb35493da4475de2cdeefca1}

Dans [!DNL Insight], ouvrez le [!DNL Server Files Manager] correspondant à votre [!DNL Insight Server] maître (généralement un FSU [!DNL Insight Server]) et procédez comme suit pour chaque FSU que vous souhaitez ajouter à la grappe :

1. Modifiez le fichier d’adresse sur le [!DNL Insight Server] maître afin d’inclure le nom et l’adresse du nouveau FSU, comme décrit dans la section [Ajout des serveurs Insight de traitement au fichier d’adresse](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Ajoutez le nom et l’adresse du nouveau FSU au groupe dans lequel sont répertoriées les [!DNL Insight Servers] actuels de votre grappe.

1. Modifiez le fichier de contrôle d’accès sur le [!DNL Insight Server] maître afin d’inclure l’adresse IP du nouveau FSU, comme décrit dans la section [Mise à jour du fichier de contrôle d’accès pour une grappe](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installation du FSU du nouveau serveur Insight {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Sur votre FSU actuel, effectuez un fichier zip du répertoire d’installation [!DNL Insight Server] et copiez le fichier dans le nouveau FSU.
1. Décompressez le fichier à l’emplacement où vous souhaitez placer le logiciel [!DNL Insight Server].
1. Téléchargez et installez le certificat numérique pour le nouveau FSU, comme décrit dans la section [Téléchargement et installation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Définissez les paramètres d’utilisation de la mémoire Windows sur le nouveau FSU.
1. Modifiez le nom du fichier [!DNL .address] afin de refléter le nom du FSU, comme décrit dans la section [Définition de l’emplacement réseau du serveur](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Si la structure du lecteur sur le nouveau FSU est différente de celle du Principal FSU, vous devez modifier le fichier [!DNL Disk Files.cfg].

   1. Ouvrez le fichier [!DNL Disk Files.cfg] sur le nouveau FSU.
   1. Mettez à jour les paramètres pour qu’ils correspondent aux lecteurs de l’Principal FSU, comme décrit dans la section [Surveillance de l’espace des données du jeu de données](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Enregistrez le fichier en local et sur le serveur.

1. Enregistrez [!DNL Insight Server] en tant que service Windows sur la nouvelle machine FSU, comme décrit dans [Enregistrement du serveur Insight en tant que service Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Répétez les étapes 1 à 6 pour chaque FSU supplémentaire que vous ajoutez à la grappe.

## Configuration du FSU du nouveau serveur Insight {#section-c39334c5bd754d5b98d41ad094333108}

Les procédures suivantes fournissent des instructions pour des tâches de configuration spécifiques. Suivez les instructions appropriées à votre mise en oeuvre du nouveau FSU.

**Configuration du FSU pour le stockage des données source**

Si le nouveau FSU stocke des données source supplémentaires pour le jeu de données s’exécutant sur la grappe, vous devez terminer le processus de configuration du serveur de fichiers comme décrit dans la section Configuration d’une [!DNL Insight Server] unité de serveur de fichiers du chapitre Fichier de configuration de traitement du journal du *Guide de configuration du jeu de données*.

**Pour que le FSU maître effectue la sauvegarde pour le FSU maître  [!DNL Insight Server]**

Si vous souhaitez que le nouveau FSU soit la sauvegarde du maître [!DNL Insight Server] (qui sert de FSU pour la grappe), vous devez modifier le fichier de synchronisation sur le nouveau FSU (de sauvegarde) afin qu&#39;il se synchronise avec le FSU maître.

1. Sur le FSU de sauvegarde [!DNL Insight Server], utilisez [!DNL Server Files Manager] pour copier le fichier [!DNL Synchronize.cfg] du dossier [!DNL Components for Processing Servers] dans le dossier [!DNL Components].

1. Ouvrez le fichier [!DNL Synchronize.cfg] (dans le dossier [!DNL Components]) dans [!DNL Insight].

1. Recherchez le paramètre SynchronizeDir qui spécifie l’emplacement du répertoire Composants. Plusieurs répertoires de synchronisation peuvent être répertoriés sous Répertoires. Vous devrez peut-être donc afficher le contenu de plusieurs d’entre eux (en cliquant sur le numéro de serveur) pour trouver le serveur souhaité.
1. Modifiez l’entrée SynchronizeDir et ajoutez une seconde entrée SynchronizeDir comme illustré dans l’exemple ci-dessous.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Enregistrez le fichier modifié sous un nouveau nom, tel que [!DNL FSU_Synchronize.cfg], afin de ne pas le confondre avec les fichiers [!DNL Synchronize.cfg] sur les DPU de la grappe.

1. Utilisez [!DNL Server Files Manager] pour enregistrer la copie locale du fichier renommé sur le serveur. Le FSU de sauvegarde télécharge les fichiers dans les répertoires identifiés à partir du FSU maître [!DNL Insight Server] et récupère dynamiquement les copies mises à jour de ces fichiers à partir du FSU maître [!DNL Insight Server] lorsqu’ils changent.
