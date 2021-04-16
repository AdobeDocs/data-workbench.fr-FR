---
description: Instructions détaillées pour l’installation d’une unité de traitement de données Insight Server et sa configuration en vue d’une utilisation administrative.
title: Procédures d’installation d’un DPU de serveur Insight
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Procédures d’installation d’un DPU de serveur Insight{#installation-procedures-for-an-insight-server-dpu}

Instructions détaillées pour l’installation d’une unité de traitement de données Insight Server et sa configuration en vue d’une utilisation administrative.

Pour installer et configurer un [!DNL Insight Server] DPU, vous devez exécuter les tâches suivantes dans l&#39;ordre :

1. Installez les fichiers de programme [!DNL Insight Server]. Voir [Installation des fichiers de Programme du serveur Insight](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Téléchargez et installez le certificat numérique [!DNL Insight Server]. Voir [Téléchargement et installation des certificats numériques](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Vérifiez les paramètres de port dans le fichier [!DNL Communications.cfg]. Voir [Vérification des paramètres de port](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifiez le fichier [!DNL Access Control.cfg] pour autoriser l&#39;accès administratif à [!DNL Insight Server] à partir de [!DNL Insight]. Voir [Mise à jour du fichier de Contrôle d&#39;accès](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifiez le fichier [!DNL server.address] pour définir l’emplacement réseau du serveur. Voir [Définition de l&#39;emplacement réseau du serveur](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Facultatif) Modifiez le fichier [!DNL Disk Files.cfg] pour spécifier l’emplacement de stockage des données traitées. Voir [Configuration de l&#39;emplacement du jeu de données (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installez les profils et les fichiers de recherche. Voir [Installation des Profils et des fichiers de recherche](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Définissez les paramètres d’utilisation de la mémoire Microsoft Windows.
1. Enregistrez [!DNL Insight Server] en tant que service Windows. Voir [Enregistrement d’Insight Server en tant que service Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
