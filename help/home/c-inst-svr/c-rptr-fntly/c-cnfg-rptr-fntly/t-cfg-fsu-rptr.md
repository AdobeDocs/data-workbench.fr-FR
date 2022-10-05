---
description: Instructions pour installer et configurer un FSU de serveur Insight à utiliser avec Répéteur.
title: Configuration d’un FSU de serveur Insight pour Répéteur
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Configuration d’un FSU de serveur Insight pour Répéteur{#configuring-an-insight-server-fsu-for-repeater}

{{eol}}

Instructions pour installer et configurer un FSU de serveur Insight à utiliser avec Répéteur.

Effectuez les tâches suivantes dans l’ordre. Toutes les exceptions ou modifications que vous devez apporter à la variable [!DNL Insight Server] Les FSU peuvent être utilisés comme serveur de répéteur sont notés après chaque étape.

1. Installez le [!DNL Insight Server] les fichiers de programme, comme décrit dans la section [Installation du serveur Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Étant donné que la machine sur laquelle vous installez ces fichiers est utilisée pour exécuter Répéteur, il est utile de donner au répertoire d’installation un nom descriptif tel que [!DNL D:\Adobe\Repeater].

1. Installez le [!DNL Insight Server] certificat numérique, comme décrit dans la section [Téléchargement et installation des certificats numériques](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Après vous être connecté au serveur de licences Adobe, pensez à rechercher le nom du certificat qui correspond au nom commun du serveur de la machine à répéteur désignée.

1. Vérifiez les paramètres du port dans le [!DNL Communications.cfg] comme décrit dans la section [Vérification des paramètres de port](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Si les ports attribués (port et port SSL) sont utilisés par un autre processus s’exécutant sur le même ordinateur, vous devez modifier les affectations de port en une paire inutilisée.

1. Si nécessaire, modifiez le répertoire des journaux pour la variable [!DNL Sensor] données à collecter et à stocker sur cette machine. Pour obtenir des instructions, voir [Surveillance de l’espace des données d’événement](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Modifiez le [!DNL Access Control.cfg] pour autoriser l’accès administrateur à [!DNL Insight Server] de [!DNL Insight] comme décrit dans [Mise à jour du fichier de contrôle d’accès](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifiez le [!DNL server.address] pour définir l’emplacement réseau du serveur, tel que défini dans [Définition de l’emplacement réseau du serveur](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Définissez les paramètres d’utilisation de la mémoire Windows.
1. Enregistrer [!DNL Insight Server] comme service Windows, comme décrit dans [Enregistrement du serveur Insight en tant que service Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
