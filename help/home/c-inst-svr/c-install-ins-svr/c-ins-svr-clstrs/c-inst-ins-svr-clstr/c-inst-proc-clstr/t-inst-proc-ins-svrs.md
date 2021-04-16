---
description: Un serveur de traitement Insight Server est identique à un serveur maître Insight, à l’exception du contenu de son répertoire Composants.
title: Installation et configuration des serveurs Insight de traitement
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installation et configuration des serveurs Insight de traitement{#installing-and-configuring-the-processing-insight-servers}

Un serveur de traitement Insight Server est identique à un serveur maître Insight, à l’exception du contenu de son répertoire Composants.

Le répertoire Composants d&#39;un traitement [!DNL Insight Server] contient un ensemble spécial de fichiers qui sont spécifiquement configurés pour le traitement [!DNL Insight Servers]. Ces fichiers sont dérivés du répertoire Composants pour les serveurs de traitement sur le répertoire maître [!DNL Insight Server].

Lorsque vous installez un traitement [!DNL Insight Server], procédez comme suit pour configurer son répertoire Composants :

1. Supprimez le répertoire Composants d&#39;origine sur le traitement [!DNL Insight Server].
1. Renommez le répertoire Composants pour les serveurs de traitement en Composants.
1. Modifiez l&#39;élément [!DNL Synchronize.cfg] du répertoire Composants pour qu&#39;il pointe vers l&#39;élément maître [!DNL Insight Server].

**Pour installer et configurer un traitement[!DNL Insight Server]**

1. Installez les fichiers de programme [!DNL Insight Server] comme décrit dans la section [Installation des fichiers de Programme du serveur Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Veillez à duplicata la structure de répertoires utilisée sur le maître [!DNL Insight Server]. Par exemple, si [!DNL Insight Server] est installé dans [!DNL C:\Adobe\Server] sur le maître [!DNL Insight Server], vous devez l&#39;installer également dans [!DNL C:\Adobe\Server] sur le traitement [!DNL Insight Servers].
1. Installez le certificat numérique que l’Adobe a émis pour ce traitement particulier [!DNL Insight Server]. Voir [Téléchargement et installation des certificats numériques](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) pour obtenir des instructions.
1. A l’aide de l’Explorateur Windows, effectuez les opérations suivantes sur le traitement [!DNL Insight Server] :

   1. Supprimez le dossier **[!UICONTROL Components]**.
   1. Renommez le dossier [!DNL Components for Processing Servers] en Composants.

1. A l’aide d’un éditeur de texte tel que Notepad, ouvrez le fichier [!DNL Synchronize.cfg] dans le répertoire Composants du traitement [!DNL Insight Server].
1. Ajoutez l’adresse IP du maître (Principal) [!DNL Insight Server] sur la deuxième ligne de ce fichier, comme illustré dans le fragment de fichier suivant. Ne modifiez rien d&#39;autre dans ce fichier.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Enregistrez le fichier.
1. Début le [!DNL Insight Server] comme décrit dans [Enregistrement d’Insight Server en tant que service Windows](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Vous avez maintenant terminé l&#39;installation de votre grappe [!DNL Insight Server]. Ensuite, configurez le profil de jeux de données pour qu’il s’exécute sur la grappe, comme décrit dans la section suivante.
