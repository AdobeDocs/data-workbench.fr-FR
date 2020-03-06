---
description: Instructions d’installation et de configuration d’un FSU de serveur Insight à utiliser avec Repeater.
solution: Insight
title: Configuration d’un FSU de serveur Insight pour Repeater
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration d’un FSU de serveur Insight pour Repeater{#configuring-an-insight-server-fsu-for-repeater}

Instructions d’installation et de configuration d’un FSU de serveur Insight à utiliser avec Repeater.

Exécutez les tâches suivantes dans l’ordre. Toutes les exceptions ou modifications que vous devez apporter afin que le [!DNL Insight Server] FSU puisse être utilisé comme serveur de répétition sont notées après chaque étape.

1. Installez les fichiers du [!DNL Insight Server] programme comme décrit dans [Installation du serveur](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)Insight.

   Comme l’ordinateur sur lequel vous installez ces fichiers est utilisé pour exécuter Repeater, il est utile de donner au répertoire d’installation un nom explicite, tel que [!DNL D:\Adobe\Repeater].

1. Installez le certificat [!DNL Insight Server] numérique comme décrit dans [Téléchargement et installation des certificats](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)numériques.

   Après vous être connecté au serveur Adobe License Server, pensez à rechercher le nom du certificat correspondant au nom commun du serveur de l’ordinateur répété désigné.

1. Vérifiez les paramètres du port dans le [!DNL Communications.cfg] fichier, comme décrit dans [Vérification des paramètres](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)du port.

   Si les ports affectés (Port et Port SSL) sont utilisés par un autre processus s’exécutant sur le même ordinateur, vous devez modifier les affectations de port en une paire inutilisée.

1. Si nécessaire, modifiez le répertoire des journaux pour que les [!DNL Sensor] données soient collectées et stockées sur cet ordinateur. Pour plus d’informations, voir [Surveillance de l’espace](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)de données d’événement.
1. Modifiez le [!DNL Access Control.cfg] fichier afin d’autoriser l’accès administratif à [!DNL Insight Server] depuis [!DNL Insight] comme décrit dans la section [Mise à jour du fichier](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)de contrôle d’accès.
1. Modifiez le [!DNL server.address] fichier pour définir l’emplacement réseau du serveur, comme défini dans [Définition de l’emplacement](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)réseau du serveur.
1. Définissez les paramètres d’utilisation de la mémoire Windows.
1. Enregistrez-vous [!DNL Insight Server] en tant que service Windows comme décrit dans [Enregistrement d’Insight Server en tant que service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.
