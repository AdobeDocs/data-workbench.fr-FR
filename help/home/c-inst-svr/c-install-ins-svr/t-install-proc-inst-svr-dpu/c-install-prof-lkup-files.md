---
description: Les profils et les fichiers de recherche développés par Adobe pour votre application particulière sont des profils internes qui fournissent les mesures, dimensions et espaces de travail qui permettent l’analyse de votre jeu de données.
solution: Insight
title: Installation des profils et des fichiers de recherche
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installation des profils et des fichiers de recherche{#installing-profiles-and-lookup-files}

Les profils et les fichiers de recherche développés par Adobe pour votre application particulière sont des profils internes qui fournissent les mesures, dimensions et espaces de travail qui permettent l’analyse de votre jeu de données.

Comme pour tous les autres profils internes fournis par Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d’autres profils que vous créez.

Adobe distribue les fichiers de profil et de recherche de votre application sous forme de [!DNL .zip] fichier. Chaque fichier zip est nommé en fonction de l’application dont le profil et les fichiers de recherche contiennent. (Par exemple, [!DNL Site52.zip] contient les fichiers de profil du site v5.2.) Le [!DNL .zip] fichier contient deux dossiers ( [!DNL Lookups] et [!DNL Profiles]).

>[!NOTE]
>
>Si vous ne disposez pas déjà du fichier d’installation contenant les profils et les fichiers de recherche de votre application, téléchargez-les depuis le site FTP Adobe avant de commencer.

Vous devez installer le profil et ses fichiers de recherche sur l’ [!DNL Insight Server] ordinateur sur lequel vous traitez et exécutez votre profil de jeu de données. Si vous exécutez une [!DNL Insight Server] grappe, vous devez installer les fichiers sur le serveur maître. Pour plus d’informations sur les profils de jeux de données, consultez le Guide *de configuration des jeux de* données.

**Pour installer des profils pour votre application Adobe**

1. Ouvrez le [!DNL Profiles] dossier à partir du [!DNL .zip] fichier fourni par Adobe.

1. Copiez tous les dossiers du [!DNL Profiles] dossier du [!DNL .zip] fichier dans le [!DNL Profiles] dossier du répertoire [!DNL Insight Server] d’installation. Vous voulez finir avec [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* des dossiers sur votre [!DNL Insight Server] site, comme illustré dans l’exemple suivant. Vos noms de profil réels peuvent différer.

   ![](assets/win_installprofiles.png)

1. Accédez au dossier [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* dans le répertoire où vous avez installé [!DNL Insight Server] et localisez le [!DNL profile.cfg] fichier dans ce répertoire.

   >[!NOTE]
   >
   >Si vous installez des profils pour la première fois, vous pouvez utiliser le profil Exemple fourni comme profil de jeu de données. Vous pouvez trouver le [!DNL profile.cfg] fichier (il peut être nommé par exemple [!DNL profile.cfg.offline]) du profil Sample dans le [!DNL Profiles\Sample] dossier du répertoire [!DNL Insight Server] d’installation.

1. Ouvrez le [!DNL profile.cfg] fichier à l’aide d’un éditeur de texte tel que le Bloc-notes, puis procédez comme suit :

   1. Ajoutez des entrées pour les profils internes dans le vecteur Répertoires. Les noms de profil correspondent aux noms des répertoires que vous avez copiés dans le [!DNL Profiles] dossier de l’ [!DNL Insight Server] ordinateur.

   1. Mettez à jour le nombre de répertoires selon vos besoins.
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
      >Le *serveurNomCommun* que vous spécifiez pour le Nom commun dans le [!DNL profile.cfg] fichier correspond au nom commun du serveur pour l’ [!DNL Insight Server] ordinateur sur lequel vous traitez et exécutez le profil du jeu de données. Pour obtenir des instructions sur la mise à jour [!DNL profile.cfg] afin que le profil du jeu de données s’exécute sur une [!DNL Insight Server] grappe, voir Clusters [de serveurs](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)Insight.

1. Enregistrez le fichier. Veillez à enregistrer le fichier comme [!DNL profile.cfg] s’il était nommé différemment.

**Pour installer les fichiers de recherche pour votre application Adobe**

1. Ouvrez le [!DNL Lookups] dossier à partir du [!DNL .zip] fichier fourni par Adobe.

1. Copiez tous les dossiers du [!DNL Lookups] dossier du [!DNL .zip] fichier dans le [!DNL Lookups] dossier du répertoire [!DNL Insight Server] d’installation. Vous voulez finir avec [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* des dossiers sur votre [!DNL Insight Server] site, comme illustré dans l’exemple suivant. Vos noms de profil réels peuvent différer.

   ![](assets/win_installLookups.png)

