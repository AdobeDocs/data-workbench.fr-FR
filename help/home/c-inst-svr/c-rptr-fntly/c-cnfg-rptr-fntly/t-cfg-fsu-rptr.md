---
description: Instructions d’installation et de configuration d’un FSU de serveur Insight à utiliser avec Repeater.
title: Configuration d’un FSU de serveur Insight pour Répéteur
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Configuration d’un FSU de serveur Insight pour Répéteur{#configuring-an-insight-server-fsu-for-repeater}

Instructions d’installation et de configuration d’un FSU de serveur Insight à utiliser avec Repeater.

Exécutez les tâches suivantes dans l’ordre. Toutes les exceptions ou modifications que vous devez apporter afin que l&#39;unité de traitement des données FSU [!DNL Insight Server] puisse être utilisée comme serveur de répéteur sont notées après chaque étape.

1. Installez les fichiers de programme [!DNL Insight Server] comme décrit dans la section [Installation du serveur Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Comme l&#39;ordinateur sur lequel vous installez ces fichiers est utilisé pour exécuter Repeater, il est utile de donner au répertoire d&#39;installation un nom descriptif tel que [!DNL D:\Adobe\Repeater].

1. Installez le [!DNL Insight Server] certificat numérique comme décrit dans [Téléchargement et installation des certificats numériques](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Après vous être connecté au serveur de licences d&#39;Adobe, pensez à rechercher le nom du certificat correspondant au nom commun du serveur de l&#39;ordinateur répété désigné.

1. Vérifiez les paramètres de port dans le fichier [!DNL Communications.cfg] comme décrit dans [Vérification des paramètres de port](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Si les ports affectés (Port et Port SSL) sont utilisés par un autre processus s&#39;exécutant sur le même ordinateur, vous devez modifier les affectations de port en une paire inutilisée.

1. Si nécessaire, modifiez le répertoire des journaux pour les données [!DNL Sensor] à collecter et à stocker sur cet ordinateur. Pour obtenir des instructions, voir [Surveillance de l&#39;espace de données du Événement](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Modifiez le fichier [!DNL Access Control.cfg] pour autoriser l&#39;accès administratif à [!DNL Insight Server] à partir de [!DNL Insight], comme décrit dans [Mise à jour du fichier de Contrôle d&#39;accès](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifiez le fichier [!DNL server.address] pour définir l&#39;emplacement réseau du serveur tel que défini dans [Définition de l&#39;emplacement réseau du serveur](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Définissez les paramètres d’utilisation de la mémoire Windows.
1. Enregistrez [!DNL Insight Server] en tant que service Windows comme décrit dans [Enregistrement d’Insight Server en tant que service Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
