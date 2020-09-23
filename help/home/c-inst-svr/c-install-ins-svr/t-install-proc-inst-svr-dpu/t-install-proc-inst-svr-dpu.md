---
description: Instructions détaillées pour l’installation d’une unité de traitement de données Insight Server et sa configuration en vue d’une utilisation administrative.
solution: Analytics
title: Procédures d’installation d’un DPU de serveur Insight
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---


# Procédures d’installation d’un DPU de serveur Insight{#installation-procedures-for-an-insight-server-dpu}

Instructions détaillées pour l’installation d’une unité de traitement de données Insight Server et sa configuration en vue d’une utilisation administrative.

Pour installer et configurer un [!DNL Insight Server] DPU, vous devez exécuter les tâches suivantes dans l’ordre :

1. Installez les fichiers du [!DNL Insight Server] programme. See [Installing the Insight Server Program Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Download and install the [!DNL Insight Server] digital certificate. See [Downloading and Installing the Digital Certificates](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Vérifiez les paramètres du port dans le [!DNL Communications.cfg] fichier. See [Checking the Port Settings](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifiez le [!DNL Access Control.cfg] fichier pour autoriser l’accès administratif à [!DNL Insight Server] depuis [!DNL Insight]. See [Updating the Access Control File](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifiez le [!DNL server.address] fichier pour définir l’emplacement réseau du serveur. See [Defining the Server&#39;s Network Location](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Facultatif) Modifiez le [!DNL Disk Files.cfg] fichier pour indiquer l’emplacement de stockage des données traitées. See [Configuring the Location of the Dataset (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installez les profils et les fichiers de recherche. See [Installing Profiles and Lookup Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Définissez les paramètres d’utilisation de la mémoire Microsoft Windows.
1. Enregistrez-vous [!DNL Insight Server] en tant que service Windows. See [Registering Insight Server as a Windows Service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
