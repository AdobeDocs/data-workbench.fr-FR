---
description: En règle générale, vous souhaitez ajouter un DPU de serveur Insight à une grappe existante lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité de la configuration actuelle de votre grappe.
solution: Insight
title: Ajout d’un DPU de serveur Insight à une grappe existante
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ajout d’un DPU de serveur Insight à une grappe existante{#adding-an-insight-server-dpu-to-an-existing-cluster}

En règle générale, vous souhaitez ajouter un DPU de serveur Insight à une grappe existante lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité de la configuration actuelle de votre grappe.

## Mise à jour des fichiers de configuration sur le serveur maître {#section-7c9a23754a994d73b722d53f999f0e82}

Dans [!DNL Insight], ouvrez le [!DNL Server Files Manager] pour votre maître [!DNL Insight Server] (généralement un [!DNL Insight Server] FSU) et procédez comme suit pour chaque unité de traitement de données que vous souhaitez ajouter à la grappe :

1. Modifiez le fichier d&#39;adresse sur le gabarit [!DNL Insight Server] pour inclure le nom et l&#39;adresse du nouveau DPU, comme décrit dans [Ajout des serveurs Processing Insight au fichier](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)d&#39;adresse. Ajoutez le nom et l’adresse du nouveau DPU au groupe dans lequel le DPU actif de votre grappe [!DNL Insight Servers] est répertorié.

1. Modifiez le fichier de contrôle d’accès sur le maître [!DNL Insight Server] pour inclure l’adresse IP du nouveau DPU, comme décrit dans [Mise à jour du fichier de contrôle d’accès pour une grappe](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installation du nouveau DPU du serveur Insight {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Cette tâche s’applique uniquement à Windows 32 bits.

1. Copiez les répertoires suivants de l’un des DPU actuels de votre grappe vers le nouveau DPU :

   * [!DNL Insight Server] répertoire d’installation/bin/
   * [!DNL Insight Server] répertoire d’installation/Certificats/
   * [!DNL Insight Server] répertoire d’installation/Composants/

1. Téléchargez et installez le certificat numérique pour le nouveau DPU, comme décrit dans [Téléchargement et installation des certificats](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)numériques.
1. Définissez les paramètres d’utilisation de la mémoire Windows sur le nouveau DPU.
1. Enregistrez-vous [!DNL Insight Server] en tant que service Windows sur le nouvel ordinateur DPU comme décrit dans [Enregistrement d’Insight Server en tant que service](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.

1. Vérifiez les journaux de suivi pour vous assurer que l’unité de traitement des données se synchronise avec l’unité de traitement principale [!DNL Insight Server].
1. Répétez les étapes 1 à 6 pour chaque DPU supplémentaire que vous ajoutez à la grappe.

## Ajout du nouveau DPU du serveur Insight aux serveurs de traitement du profil de jeu de données {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Si le nouveau DPU traite le même jeu de données que les autres DPU de la grappe, ajoutez le nom commun du nouveau DPU au [!DNL profile.cfg] fichier sur le modèle [!DNL Insight Server] comme décrit dans [Spécification des serveurs de traitement dans Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
