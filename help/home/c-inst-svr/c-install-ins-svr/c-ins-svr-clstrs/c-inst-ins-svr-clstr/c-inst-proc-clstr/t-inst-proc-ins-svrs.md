---
description: Un serveur Insight de traitement est identique à un serveur Insight maître, à l’exception du contenu de son répertoire Composants.
title: Installation et configuration des serveurs Insight de traitement
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installation et configuration des serveurs Insight de traitement{#installing-and-configuring-the-processing-insight-servers}

Un serveur Insight de traitement est identique à un serveur Insight maître, à l’exception du contenu de son répertoire Composants.

Le répertoire Composants d’un traitement [!DNL Insight Server] contient un ensemble spécial de fichiers qui sont spécifiquement configurés pour le traitement [!DNL Insight Servers]. Ces fichiers sont dérivés du répertoire Composants pour les serveurs de traitement sur le [!DNL Insight Server] maître.

Lorsque vous installez un traitement [!DNL Insight Server], procédez comme suit pour configurer son répertoire Composants :

1. Supprimez le répertoire Composants d’origine sur le [!DNL Insight Server] traitement.
1. Renommez le répertoire Composants du serveur de traitement en Composants.
1. Modifiez la balise [!DNL Synchronize.cfg] du répertoire Composants pour qu’elle pointe vers la balise [!DNL Insight Server] maître.

**Pour installer et configurer un traitement[!DNL Insight Server]**

1. Installez les fichiers de programme [!DNL Insight Server] comme décrit dans la section [Installation des fichiers de programme du serveur Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Veillez à dupliquer la structure de répertoire utilisée sur le [!DNL Insight Server] maître. Par exemple, si [!DNL Insight Server] est installé dans [!DNL C:\Adobe\Server] sur le [!DNL Insight Server] maître, vous devez également l’installer dans [!DNL C:\Adobe\Server] sur le [!DNL Insight Servers] traitement.
1. Installez le certificat numérique émis par Adobe pour ce traitement particulier [!DNL Insight Server]. Voir [Téléchargement et installation des certificats numériques](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) pour obtenir des instructions.
1. À l’aide de l’Explorateur Windows, effectuez les opérations suivantes sur le traitement [!DNL Insight Server] :

   1. Supprimez le dossier **[!UICONTROL Components]**.
   1. Renommez le dossier [!DNL Components for Processing Servers] en Composants.

1. À l’aide d’un éditeur de texte tel que le Bloc-notes, ouvrez le fichier [!DNL Synchronize.cfg] dans le répertoire Composants du [!DNL Insight Server] traitement.
1. Ajoutez l’adresse IP du gabarit (Principal) [!DNL Insight Server] à la deuxième ligne de ce fichier, comme illustré dans le fragment de fichier suivant. Ne modifiez rien d’autre dans ce fichier.

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
1. Démarrez [!DNL Insight Server] comme décrit dans [Enregistrement du serveur Insight en tant que service Windows](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Vous avez maintenant terminé l’installation de votre grappe [!DNL Insight Server]. Ensuite, configurez le profil du jeu de données pour qu’il s’exécute sur la grappe, comme décrit dans la section suivante.
