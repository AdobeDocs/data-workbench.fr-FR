---
description: Un serveur Insight de traitement est identique à un serveur Insight maître, à l’exception du contenu de son répertoire Composants.
title: Installation et configuration des serveurs Insight de traitement
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installation et configuration des serveurs Insight de traitement{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

Un serveur Insight de traitement est identique à un serveur Insight maître, à l’exception du contenu de son répertoire Composants.

Répertoire Composants sur un traitement [!DNL Insight Server] contient un ensemble spécial de fichiers spécifiquement configurés pour le traitement. [!DNL Insight Servers]. Ces fichiers sont dérivés du répertoire Composants pour les serveurs de traitement sur le maître. [!DNL Insight Server].

Lors de l’installation d’un traitement [!DNL Insight Server], procédez comme suit pour configurer son répertoire Composants :

1. Supprimer le répertoire Composants d’origine dans le traitement [!DNL Insight Server].
1. Renommez le répertoire Composants du serveur de traitement en Composants.
1. Modifiez le [!DNL Synchronize.cfg] dans le répertoire Composants pour pointer vers le maître [!DNL Insight Server].

**Pour installer et configurer un traitement[!DNL Insight Server]**

1. Installez le [!DNL Insight Server] les fichiers de programme, comme décrit dans la section [Installation des fichiers de programme du serveur Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Veillez à dupliquer la structure de répertoire utilisée sur le maître. [!DNL Insight Server]. Par exemple, si [!DNL Insight Server] est installé dans [!DNL C:\Adobe\Server] sur le maître [!DNL Insight Server], vous devez l’installer dans [!DNL C:\Adobe\Server] sur le traitement [!DNL Insight Servers] ainsi que .
1. Installez le certificat numérique émis par Adobe pour ce traitement particulier. [!DNL Insight Server]. Voir [Téléchargement et installation des certificats numériques](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) pour obtenir des instructions.
1. À l’aide de l’Explorateur Windows, effectuez les opérations suivantes sur le traitement [!DNL Insight Server]:

   1. Supprimez la variable **[!UICONTROL Components]** dossier.
   1. Renommez la variable [!DNL Components for Processing Servers] vers les composants.

1. À l’aide d’un éditeur de texte tel que Bloc-notes, ouvrez la [!DNL Synchronize.cfg] dans le répertoire Composants du traitement. [!DNL Insight Server].
1. Ajout de l’adresse IP du maître (Principal) [!DNL Insight Server] à la deuxième ligne de ce fichier, comme indiqué dans le fragment de fichier suivant. Ne modifiez rien d’autre dans ce fichier.

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
1. Démarrez le [!DNL Insight Server] comme décrit dans [Enregistrement du serveur Insight en tant que service Windows](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Vous avez maintenant terminé l’installation de votre [!DNL Insight Server] grappe. Ensuite, configurez le profil du jeu de données pour qu’il s’exécute sur la grappe, comme décrit dans la section suivante.
