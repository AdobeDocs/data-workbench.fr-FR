---
description: Les profils et les fichiers de recherche développés par Adobe pour votre application spécifique sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l’analyse de votre jeu de données.
title: Installation des profils et des fichiers Lookup
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# Installation des profils et des fichiers Lookup{#installing-profiles-and-lookup-files}

{{eol}}

Les profils et les fichiers de recherche développés par Adobe pour votre application spécifique sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l’analyse de votre jeu de données.

Comme pour tous les autres profils internes fournis par Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Adobe distribue le profil et les fichiers de recherche de votre application sous la forme d’une [!DNL .zip] fichier . Chaque fichier zip est nommé en fonction de l’application dont le profil et les fichiers de recherche qu’il contient. (Par exemple, [!DNL Site52.zip] contient les fichiers de profil pour le site v5.2.) Le [!DNL .zip] Le fichier contient deux dossiers ( [!DNL Lookups] et [!DNL Profiles]).

>[!NOTE]
>
>Si vous ne disposez pas déjà du fichier d’installation contenant les profils et les fichiers de recherche de votre application, téléchargez-les sur le site FTP Adobe avant de commencer.

Vous devez installer le profil et ses fichiers de recherche sur le [!DNL Insight Server] machine sur laquelle vous traitez et exécutez votre profil de jeu de données. Si vous exécutez une [!DNL Insight Server] , vous devez installer les fichiers sur le serveur maître. Pour plus d’informations sur les profils de jeux de données, voir *Guide de configuration des jeux de données*.

**Pour installer des profils pour votre application Adobe**

1. Ouvrez le [!DNL Profiles] à partir du dossier [!DNL .zip] fichier fourni par Adobe.

1. Copiez tous les dossiers dans le [!DNL Profiles] dans le dossier [!DNL .zip] vers le fichier [!DNL Profiles] dans votre dossier [!DNL Insight Server] répertoire d’installation. Vous voulez finir avec [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>* dans vos dossiers [!DNL Insight Server] comme illustré dans l’exemple suivant. Les noms réels de vos profils peuvent différer.

   ![](assets/win_installprofiles.png)

1. Accédez au  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* dans le répertoire où vous avez installé [!DNL Insight Server] et recherchez la variable [!DNL profile.cfg] dans ce répertoire.

   >[!NOTE]
   >
   >Si vous installez des profils pour la première fois, vous pouvez utiliser l’ exemple de profil fourni comme profil de jeu de données. Vous trouverez la variable [!DNL profile.cfg] fichier (il peut être nommé de la manière suivante : [!DNL profile.cfg.offline]) pour l’ exemple de profil dans le [!DNL Profiles\Sample] dans votre dossier [!DNL Insight Server] répertoire d’installation.

1. Ouvrez le [!DNL profile.cfg] à l’aide d’un éditeur de texte, tel que le Bloc-notes, et procédez comme suit :

   1. Ajoutez des entrées pour les profils internes dans le vecteur Répertoires . Les noms des profils correspondent aux noms des répertoires que vous avez copiés dans le [!DNL Profiles] sur le dossier [!DNL Insight Server] machine.

   1. Mettez à jour le nombre de répertoires à votre convenance.
   1. Ajoutez le nom commun du serveur à la ligne Nom commun de ce fichier, comme indiqué ci-dessous :

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >Le *serverCommonName* que vous spécifiez pour le Nom commun dans la variable [!DNL profile.cfg] correspond au nom commun du serveur pour la variable [!DNL Insight Server] machine sur laquelle vous traitez et exécutez le profil du jeu de données. Pour obtenir des instructions sur la mise à jour [!DNL profile.cfg] afin que le profil du jeu de données s’exécute sur une [!DNL Insight Server] grappe, voir [Clusters de serveur Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Enregistrez le fichier. Veillez à enregistrer le fichier en tant que [!DNL profile.cfg] s’il a été nommé différemment.

**Pour installer les fichiers de recherche pour votre application Adobe**

1. Ouvrez le [!DNL Lookups] à partir du dossier [!DNL .zip] fichier fourni par Adobe.

1. Copiez tous les dossiers dans le [!DNL Lookups] dans le dossier [!DNL .zip] vers le fichier [!DNL Lookups] dans votre dossier [!DNL Insight Server] répertoire d’installation. Vous voulez finir avec [!DNL ...\Recherches\]*&lt; [!DNL internal profile name]>* dans vos dossiers [!DNL Insight Server] comme illustré dans l’exemple suivant. Les noms réels de vos profils peuvent différer.

   ![](assets/win_installLookups.png)
