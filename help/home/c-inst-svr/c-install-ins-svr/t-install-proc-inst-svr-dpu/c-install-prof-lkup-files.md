---
description: Les profils et les fichiers de recherche développés par l'Adobe pour votre application particulière sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l'analyse de votre jeu de données.
title: Installation des profils et des fichiers Lookup
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Installation des profils et des fichiers Lookup{#installing-profiles-and-lookup-files}

Les profils et les fichiers de recherche développés par l&#39;Adobe pour votre application particulière sont des profils internes qui fournissent les mesures, les dimensions et les espaces de travail qui permettent l&#39;analyse de votre jeu de données.

Comme pour tous les autres profils internes fournis par l&#39;Adobe, ces profils ne doivent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez.

Adobe distribue les fichiers de profil et de recherche pour votre application sous la forme d&#39;un fichier [!DNL .zip]. Chaque fichier zip est nommé en fonction de l’application dont le profil et les fichiers de recherche contiennent. (Par exemple, [!DNL Site52.zip] contient les fichiers de profil du site v5.2.) Le fichier [!DNL .zip] contient deux dossiers ( [!DNL Lookups] et [!DNL Profiles]).

>[!NOTE]
>
>Si vous ne disposez pas déjà du fichier d’installation contenant les profils et les fichiers de recherche de votre application, téléchargez-les depuis le site FTP de l’Adobe avant de commencer.

Vous devez installer le profil et ses fichiers de recherche sur l&#39;ordinateur [!DNL Insight Server] sur lequel vous traitez et exécutez votre profil de jeux de données. Si vous exécutez une grappe [!DNL Insight Server], vous devez installer les fichiers sur le serveur maître. Pour plus d&#39;informations sur les profils des jeux de données, consultez le *Guide de configuration des jeux de données*.

**Pour installer des profils pour votre application d’Adobe**

1. Ouvrez le dossier [!DNL Profiles] à partir du fichier [!DNL .zip] qui vous a été fourni par Adobe.

1. Copiez tous les dossiers du dossier [!DNL Profiles] du fichier [!DNL .zip] dans le dossier [!DNL Profiles] de votre répertoire d&#39;installation [!DNL Insight Server]. Vous souhaitez finir avec les dossiers  [!DNL ...\Profiles\]*&lt; &lt;a1/&quot;* sur votre [!DNL Insight Server] comme indiqué dans l&#39;exemple suivant. [!DNL internal profile name] Vos noms de profil réels peuvent différer.

   ![](assets/win_installprofiles.png)

1. Accédez au dossier  [!DNL Profiles\]*&lt; &lt;a1/&quot;* dans le répertoire où vous avez installé [!DNL Insight Server] et localisez le fichier [!DNL profile.cfg] dans ce répertoire.[!DNL dataset profile name]

   >[!NOTE]
   >
   >Si vous installez des profils pour la première fois, vous pouvez utiliser l’exemple de profil fourni comme profil de jeu de données. Vous pouvez trouver le fichier [!DNL profile.cfg] (il peut être nommé par exemple [!DNL profile.cfg.offline]) pour l’profil d’exemple dans le dossier [!DNL Profiles\Sample] de votre répertoire d’installation [!DNL Insight Server].

1. Ouvrez le fichier [!DNL profile.cfg] à l’aide d’un éditeur de texte tel que le Bloc-notes et procédez comme suit :

   1. Ajoutez les entrées des profils internes dans le vecteur Répertoires. Les noms de profil correspondent aux noms des répertoires que vous avez copiés dans le dossier [!DNL Profiles] de l&#39;ordinateur [!DNL Insight Server].

   1. Mettez à jour le nombre de répertoires selon les besoins.
   1. Ajoutez le nom commun du serveur sur la ligne Nom commun de ce fichier, comme indiqué ci-dessous :

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
      >Le *nomCommunServeur* que vous spécifiez pour le nom commun dans le fichier [!DNL profile.cfg] correspond au nom commun du serveur de l&#39;ordinateur [!DNL Insight Server] sur lequel vous traitez et exécutez le profil de jeux de données. Pour obtenir des instructions sur la mise à jour de [!DNL profile.cfg] afin que le profil de jeux de données s’exécute sur un cluster [!DNL Insight Server], voir [Grappes de serveurs Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Enregistrez le fichier. Veillez à enregistrer le fichier sous [!DNL profile.cfg] s’il a été nommé différemment.

**Pour installer les fichiers de recherche de votre application d’Adobe**

1. Ouvrez le dossier [!DNL Lookups] à partir du fichier [!DNL .zip] qui vous a été fourni par Adobe.

1. Copiez tous les dossiers du dossier [!DNL Lookups] du fichier [!DNL .zip] dans le dossier [!DNL Lookups] de votre répertoire d&#39;installation [!DNL Insight Server]. Vous souhaitez finir avec les dossiers  [!DNL ...\Lookups\]*&lt; &lt;a1/&quot;* sur votre [!DNL Insight Server] comme indiqué dans l&#39;exemple suivant. [!DNL internal profile name] Vos noms de profil réels peuvent différer.

   ![](assets/win_installLookups.png)
