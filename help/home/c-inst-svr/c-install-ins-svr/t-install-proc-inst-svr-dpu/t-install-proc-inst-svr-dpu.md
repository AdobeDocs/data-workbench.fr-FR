---
description: Instructions détaillées pour l’installation d’un DPU de serveur Insight et sa configuration en vue d’une utilisation administrative.
solution: Insight
title: Procédures d’installation d’un DPU de serveur Insight
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procédures d’installation d’un DPU de serveur Insight{#installation-procedures-for-an-insight-server-dpu}

Instructions détaillées pour l’installation d’un DPU de serveur Insight et sa configuration en vue d’une utilisation administrative.

Pour installer et configurer un [!DNL Insight Server] DPU, vous devez exécuter les tâches suivantes dans l’ordre :

1. Installez les fichiers [!DNL Insight Server] du programme. Voir [Installation des fichiers](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)du programme du serveur Insight.
1. Download and install the [!DNL Insight Server] digital certificate. Voir [Téléchargement et installation des certificats](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)numériques.
1. Vérifiez les paramètres du port dans le [!DNL Communications.cfg] fichier. Voir [Vérification des paramètres](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)de port.
1. Modifiez le [!DNL Access Control.cfg] fichier pour autoriser l’accès administratif à [!DNL Insight Server] depuis [!DNL Insight]. Voir [Mise à jour du fichier](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)de contrôle d’accès.
1. Modifiez le [!DNL server.address] fichier pour définir l’emplacement réseau du serveur. Voir [Définition de l’emplacement](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)réseau du serveur.
1. (Facultatif) Modifiez le [!DNL Disk Files.cfg] fichier pour indiquer l’emplacement de stockage des données traitées. Voir [Configuration de l’emplacement du jeu de données (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installez les profils et les fichiers de recherche. Voir [Installation des profils et des fichiers](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)de recherche.
1. Définissez les paramètres d’utilisation de la mémoire Microsoft Windows.
1. Enregistrez-vous [!DNL Insight Server] en tant que service Windows. Voir [Enregistrement d’Insight Server en tant que service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.
