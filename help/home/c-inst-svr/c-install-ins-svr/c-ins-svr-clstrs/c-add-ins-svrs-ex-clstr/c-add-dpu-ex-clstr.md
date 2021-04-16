---
description: En règle générale, vous souhaitez ajouter une unité de traitement de données Insight Server à une grappe existante lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité de la configuration actuelle de la grappe.
title: Ajout d’un DPU de serveur Insight à un cluster existant
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# Ajout d’un DPU de serveur Insight à un cluster existant{#adding-an-insight-server-dpu-to-an-existing-cluster}

En règle générale, vous souhaitez ajouter une unité de traitement de données Insight Server à une grappe existante lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité de la configuration actuelle de la grappe.

## Mise à jour des fichiers de configuration sur le serveur de Principal {#section-7c9a23754a994d73b722d53f999f0e82}

Dans [!DNL Insight], ouvrez le [!DNL Server Files Manager] pour votre [!DNL Insight Server] maître (généralement un FSU [!DNL Insight Server]) et effectuez les opérations suivantes pour chaque DPU à ajouter à la grappe :

1. Modifiez le fichier d&#39;adresse sur le [!DNL Insight Server] maître afin d&#39;inclure le nom et l&#39;adresse du nouveau DPU, comme décrit dans [Ajouter les serveurs Processing Insight au fichier d&#39;adresse](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Ajoutez le nom et l’adresse du nouveau DPU au groupe dans lequel le [!DNL Insight Servers] actuel de votre grappe est répertorié.

1. Modifiez le fichier de contrôle d&#39;accès sur le fichier maître [!DNL Insight Server] pour inclure l&#39;adresse IP du nouveau DPU, comme décrit dans [Mise à jour du fichier de Contrôle d&#39;accès pour une grappe](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installation du nouveau DPU du serveur Insight {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Cette tâche s&#39;applique uniquement à Windows 32 bits.

1. Copiez les répertoires suivants de l’un des DPU actuels de votre grappe vers le nouveau DPU :

   * [!DNL Insight Server] répertoire d’installation/bin/
   * [!DNL Insight Server] répertoire d’installation/Certificats/
   * [!DNL Insight Server] répertoire d’installation/Composants/

1. Téléchargez et installez le certificat numérique pour le nouveau DPU comme décrit dans [Téléchargement et installation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Définissez les paramètres d&#39;utilisation de la mémoire Windows sur le nouveau DPU.
1. Enregistrez [!DNL Insight Server] en tant que service Windows sur le nouvel ordinateur DPU comme décrit dans [Enregistrement d’Insight Server en tant que service Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Vérifiez les journaux de suivi pour vous assurer que l&#39;unité de traitement des données se synchronise avec le [!DNL Insight Server] maître.
1. Répétez les étapes 1 à 6 pour chaque unité de traitement de données supplémentaire que vous ajoutez à la grappe.

## Ajouter l’unité de traitement DPU du nouveau serveur Insight sur les serveurs de traitement du Profil de données {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Si le nouveau DPU traite le même jeu de données que les autres DPU de la grappe, ajoutez le nom commun du nouveau DPU au fichier [!DNL profile.cfg] sur le fichier maître [!DNL Insight Server] comme décrit dans [Spécification des serveurs de traitement dans Profil.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
