---
description: Un serveur de traitement Insight Server est identique à un serveur maître Insight, à l’exception du contenu de son répertoire Composants.
solution: Analytics
title: Installation et configuration des serveurs Insight de traitement
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---


# Installation et configuration des serveurs Insight de traitement{#installing-and-configuring-the-processing-insight-servers}

Un serveur de traitement Insight Server est identique à un serveur maître Insight, à l’exception du contenu de son répertoire Composants.

Le répertoire Composants d’un traitement [!DNL Insight Server] contient un ensemble spécial de fichiers qui sont spécifiquement configurés pour le traitement [!DNL Insight Servers]. Ces fichiers sont dérivés du répertoire Composants pour les serveurs de traitement sur le répertoire maître [!DNL Insight Server].

Lorsque vous installez un traitement [!DNL Insight Server], vous procédez comme suit pour configurer son répertoire Composants :

1. Supprimez le répertoire Composants d’origine sur le traitement [!DNL Insight Server].
1. Renommez le répertoire Composants pour les serveurs de traitement en Composants.
1. Modifiez la [!DNL Synchronize.cfg] section du répertoire Composants pour qu’elle pointe vers le gabarit [!DNL Insight Server].

**Pour installer et configurer un traitement[!DNL Insight Server]**

1. Installez les fichiers de [!DNL Insight Server] programme comme décrit dans la section [Installation des fichiers](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)de Programme du serveur Insight. Veillez à duplicata la structure de répertoires utilisée sur le maître [!DNL Insight Server]. Par exemple, si [!DNL Insight Server] est installé dans [!DNL C:\Adobe\Server] le maître [!DNL Insight Server], vous devez l’installer dans [!DNL C:\Adobe\Server] le traitement [!DNL Insight Servers] également.
1. Installez le certificat numérique que l’Adobe a émis pour ce traitement particulier [!DNL Insight Server]. Voir [Téléchargement et installation des certificats](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) numériques pour obtenir des instructions.
1. A l’aide de l’Explorateur Windows, effectuez les opérations suivantes sur le traitement [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. Renommez le [!DNL Components for Processing Servers] dossier en Composants.

1. A l’aide d’un éditeur de texte tel que le Bloc-notes, ouvrez le [!DNL Synchronize.cfg] fichier dans le répertoire Composants du traitement [!DNL Insight Server].
1. ajoutez l’adresse IP du maître (Principal) [!DNL Insight Server] à la deuxième ligne de ce fichier, comme illustré dans le fragment de fichier suivant. Ne modifiez rien d&#39;autre dans ce fichier.

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
1. Début la [!DNL Insight Server] comme décrit dans [Enregistrement d’Insight Server en tant que service](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.

   Vous avez maintenant terminé l’installation de votre [!DNL Insight Server] grappe. Ensuite, configurez le profil de jeux de données pour qu’il s’exécute sur la grappe, comme décrit dans la section suivante.

