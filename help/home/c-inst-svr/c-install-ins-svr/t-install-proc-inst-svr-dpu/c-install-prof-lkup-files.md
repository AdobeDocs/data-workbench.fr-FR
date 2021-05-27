---
description: Les profils et les fichiers de recherche développés par Adobe pour votre application spécifique sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l’analyse de votre jeu de données.
title: Installation des profils et des fichiers Lookup
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Installation des profils et des fichiers Lookup{#installing-profiles-and-lookup-files}

Les profils et les fichiers de recherche développés par Adobe pour votre application spécifique sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l’analyse de votre jeu de données.

Comme pour tous les autres profils internes fournis par Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans les profils spécifiques à un rôle ou dans d’autres profils que vous créez.

Adobe distribue les fichiers de profil et de recherche pour votre application sous la forme d’un fichier [!DNL .zip]. Chaque fichier zip est nommé en fonction de l’application dont le profil et les fichiers de recherche qu’il contient. (Par exemple, [!DNL Site52.zip] contient les fichiers de profil pour le site v5.2.) Le fichier [!DNL .zip] contient deux dossiers ( [!DNL Lookups] et [!DNL Profiles]).

>[!NOTE]
>
>Si vous ne disposez pas déjà du fichier d’installation contenant les profils et les fichiers de recherche de votre application, téléchargez-les sur le site FTP Adobe avant de commencer.

Vous devez installer le profil et ses fichiers de recherche sur la machine [!DNL Insight Server] sur laquelle vous traitez et exécutez votre profil de jeu de données. Si vous exécutez une grappe [!DNL Insight Server], vous devez installer les fichiers sur le serveur maître. Pour plus d’informations sur les profils de jeux de données, consultez le *Guide de configuration des jeux de données*.

**Pour installer des profils pour votre application Adobe**

1. Ouvrez le dossier [!DNL Profiles] à partir du fichier [!DNL .zip] fourni par Adobe.

1. Copiez tous les dossiers du dossier [!DNL Profiles] du fichier [!DNL .zip] dans le dossier [!DNL Profiles] de votre répertoire d’installation [!DNL Insight Server]. Vous souhaitez obtenir des dossiers  [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]* sur vos [!DNL Insight Server] comme illustré dans l’exemple suivant. Les noms réels de vos profils peuvent différer.

   ![](assets/win_installprofiles.png)

1. Accédez au dossier  [!DNL Profiles\]*&lt; [!DNL dataset profile name]* dans le répertoire où vous avez installé [!DNL Insight Server] et localisez le fichier [!DNL profile.cfg] dans ce répertoire.

   >[!NOTE]
   >
   >Si vous installez des profils pour la première fois, vous pouvez utiliser l’ exemple de profil fourni comme profil de jeu de données. Vous pouvez trouver le fichier [!DNL profile.cfg] (qui peut être appelé par exemple [!DNL profile.cfg.offline]) pour le profil d’exemple dans le dossier [!DNL Profiles\Sample] de votre répertoire d’installation [!DNL Insight Server].

1. Ouvrez le fichier [!DNL profile.cfg] à l’aide d’un éditeur de texte tel que le Bloc-notes et procédez comme suit :

   1. Ajoutez des entrées pour les profils internes dans le vecteur Répertoires . Les noms des profils correspondent aux noms des répertoires que vous avez copiés dans le dossier [!DNL Profiles] de la machine [!DNL Insight Server].

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
      >La valeur *serverCommonName* que vous indiquez pour le nom commun dans le fichier [!DNL profile.cfg] correspond au nom commun du serveur pour la machine [!DNL Insight Server] sur laquelle vous traitez et exécutez le profil du jeu de données. Pour obtenir des instructions sur la mise à jour de [!DNL profile.cfg] afin que le profil du jeu de données s’exécute sur une grappe [!DNL Insight Server], voir [Clusters de serveur Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Enregistrez le fichier. Veillez à enregistrer le fichier sous la forme [!DNL profile.cfg] s’il a été nommé différemment.

**Pour installer les fichiers de recherche pour votre application Adobe**

1. Ouvrez le dossier [!DNL Lookups] à partir du fichier [!DNL .zip] fourni par Adobe.

1. Copiez tous les dossiers du dossier [!DNL Lookups] du fichier [!DNL .zip] dans le dossier [!DNL Lookups] de votre répertoire d’installation [!DNL Insight Server]. Vous souhaitez obtenir des dossiers  [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]* sur vos [!DNL Insight Server] comme illustré dans l’exemple suivant. Les noms réels de vos profils peuvent différer.

   ![](assets/win_installLookups.png)
