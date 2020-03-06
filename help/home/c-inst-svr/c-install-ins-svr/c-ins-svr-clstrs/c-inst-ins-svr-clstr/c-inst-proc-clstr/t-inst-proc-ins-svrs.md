---
description: Un serveur Insight de traitement est identique à un serveur maître Insight, à l’exception du contenu de son répertoire Composants.
solution: Insight
title: Installation et configuration des serveurs Processing Insight
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installation et configuration des serveurs Processing Insight{#installing-and-configuring-the-processing-insight-servers}

Un serveur Insight de traitement est identique à un serveur maître Insight, à l’exception du contenu de son répertoire Composants.

Le répertoire Composants d’un traitement [!DNL Insight Server] contient un ensemble spécial de fichiers spécifiquement configurés pour le traitement [!DNL Insight Servers]. Ces fichiers sont dérivés du répertoire Composants pour les serveurs de traitement sur le répertoire maître [!DNL Insight Server].

Lorsque vous installez un traitement [!DNL Insight Server], procédez comme suit pour configurer son répertoire Composants :

1. Supprimez le répertoire Composants d’origine sur le traitement [!DNL Insight Server].
1. Renommez le répertoire Composants du répertoire Serveurs de traitement en Composants.
1. Modifiez la [!DNL Synchronize.cfg] section du répertoire Composants pour qu’elle pointe vers le gabarit [!DNL Insight Server].

**Pour installer et configurer un traitement[!DNL Insight Server]**

1. Installez les fichiers du [!DNL Insight Server] programme comme décrit dans [Installation des fichiers](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)du programme du serveur Insight. Veillez à dupliquer la structure de répertoires utilisée sur le gabarit [!DNL Insight Server]. Par exemple, si [!DNL Insight Server] est installé dans [!DNL C:\Adobe\Server] le maître [!DNL Insight Server], vous devez l’installer dans [!DNL C:\Adobe\Server] le traitement [!DNL Insight Servers] également.
1. Installez le certificat numérique émis par Adobe pour ce traitement particulier [!DNL Insight Server]. Voir [Téléchargement et installation des certificats](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) numériques pour obtenir des instructions.
1. A l’aide de l’Explorateur Windows, procédez comme suit sur le traitement [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. Renommez le [!DNL Components for Processing Servers] dossier en Composants.

1. A l’aide d’un éditeur de texte tel que le Bloc-notes, ouvrez le [!DNL Synchronize.cfg] fichier dans le répertoire Composants du traitement [!DNL Insight Server].
1. Ajoutez l’adresse IP du maître (principal) [!DNL Insight Server] à la deuxième ligne de ce fichier, comme illustré dans le fragment de fichier suivant. Ne modifiez rien d’autre dans ce fichier.

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
1. Démarrez le [!DNL Insight Server] comme décrit dans [Enregistrement d’Insight Server en tant que service](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.

   Vous avez maintenant terminé l’installation de votre [!DNL Insight Server] grappe. Ensuite, configurez le profil du jeu de données pour qu’il s’exécute sur la grappe, comme décrit dans la section suivante.

