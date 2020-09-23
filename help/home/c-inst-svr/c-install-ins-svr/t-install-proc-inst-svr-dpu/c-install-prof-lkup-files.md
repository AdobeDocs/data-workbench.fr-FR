---
description: Les profils et les fichiers de recherche développés par l'Adobe pour votre application particulière sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l'analyse de votre jeu de données.
solution: Analytics
title: Installation des profils et des fichiers Lookup
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---


# Installation des profils et des fichiers Lookup{#installing-profiles-and-lookup-files}

Les profils et les fichiers de recherche développés par l&#39;Adobe pour votre application particulière sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l&#39;analyse de votre jeu de données.

Comme pour tous les autres profils internes fournis par l&#39;Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez.

adobe distribue les fichiers de profil et de recherche de votre application sous la forme d’un [!DNL .zip] fichier. Chaque fichier zip est nommé en fonction de l’application dont le profil et les fichiers de recherche contiennent. (Par exemple, [!DNL Site52.zip] contient les fichiers de profil pour Site v5.2.) Le [!DNL .zip] fichier contient deux dossiers ( [!DNL Lookups] et [!DNL Profiles]).

>[!NOTE]
>
>Si vous ne disposez pas déjà du fichier d’installation contenant les profils et les fichiers de recherche de votre application, téléchargez-les depuis le site FTP de l’Adobe avant de commencer.

Vous devez installer le profil et ses fichiers de recherche sur l’ [!DNL Insight Server] ordinateur sur lequel vous traitez et exécutez votre profil de jeux de données. Si vous exécutez une [!DNL Insight Server] grappe, vous devez installer les fichiers sur le serveur maître. Pour plus d&#39;informations sur les profils de jeux de données, consultez le Guide *de configuration des jeux de* données.

**Pour installer des profils pour votre application d’Adobe**

1. Ouvrez le [!DNL Profiles] dossier à partir du [!DNL .zip] fichier qui vous a été fourni par Adobe.

1. Copiez tous les dossiers du [!DNL Profiles] dossier du [!DNL .zip] fichier dans le [!DNL Profiles] dossier du répertoire d’ [!DNL Insight Server] installation. Vous souhaitez obtenir  [!DNL ...\Profiles\]*des dossiers&lt;[!DNL internal profile name]>* sur votre [!DNL Insight Server] site, comme le montre l&#39;exemple suivant. Vos noms de profil réels peuvent différer.

   ![](assets/win_installprofiles.png)

1. Accédez au  [!DNL Profiles\]*dossier&lt;[!DNL dataset profile name]>* dans le répertoire où vous avez installé [!DNL Insight Server] et localisez le [!DNL profile.cfg] fichier dans ce répertoire.

   >[!NOTE]
   >
   >Si vous installez des profils pour la première fois, vous pouvez utiliser l’exemple de profil fourni comme profil de jeu de données. Vous pouvez trouver le [!DNL profile.cfg] fichier (qui peut être appelé par exemple [!DNL profile.cfg.offline]) pour l’exemple de profil dans le [!DNL Profiles\Sample] dossier du répertoire d’ [!DNL Insight Server] installation.

1. Ouvrez le [!DNL profile.cfg] fichier à l’aide d’un éditeur de texte tel que le Bloc-notes et procédez comme suit :

   1. ajoutez les entrées des profils internes dans le vecteur Répertoires. Les noms des profils correspondent aux noms des répertoires que vous avez copiés dans le [!DNL Profiles] dossier de l’ [!DNL Insight Server] ordinateur.

   1. Mettez à jour le nombre de répertoires selon les besoins.
   1. ajoutez le nom commun du serveur sur la ligne Nom commun de ce fichier, comme indiqué ci-dessous :

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
      >Le *serveurCommonName* que vous spécifiez pour le nom commun dans le [!DNL profile.cfg] fichier correspond au nom commun du serveur pour l&#39; [!DNL Insight Server] ordinateur sur lequel vous traitez et exécutez le profil de jeux de données. Pour obtenir des instructions sur la mise à jour [!DNL profile.cfg] afin que le profil de jeux de données s’exécute sur une [!DNL Insight Server] grappe, voir Clusters [de serveurs](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)Insight.

1. Enregistrez le fichier. Veillez à enregistrer le fichier comme [!DNL profile.cfg] s’il portait un nom différent.

**Pour installer les fichiers de recherche de votre application d’Adobe**

1. Ouvrez le [!DNL Lookups] dossier à partir du [!DNL .zip] fichier qui vous a été fourni par Adobe.

1. Copiez tous les dossiers du [!DNL Lookups] dossier du [!DNL .zip] fichier dans le [!DNL Lookups] dossier du répertoire d’ [!DNL Insight Server] installation. Vous souhaitez obtenir  [!DNL ...\Lookups\]*des dossiers&lt;[!DNL internal profile name]>* sur votre [!DNL Insight Server] site, comme le montre l&#39;exemple suivant. Vos noms de profil réels peuvent différer.

   ![](assets/win_installLookups.png)

