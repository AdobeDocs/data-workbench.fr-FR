---
description: Les noms de dossiers et de fichiers inclus dans votre implémentation sont affichés sur le côté gauche de Profil Manager.
title: Gestionnaire de profil
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Gestionnaire de profil{#profile-manager}

Les noms de dossiers et de fichiers inclus dans votre implémentation sont affichés sur le côté gauche de Profil Manager.

Les profils qui composent votre application sont affichés sous forme de colonnes individuelles dans le [!DNL Profile Manager]. Ces profils comprennent plusieurs profils hérités et un seul profil de travail.

>[!NOTE]
>
>Votre profil de travail (profil de jeux de données ou profil spécifique au rôle) est le profil que vous chargez lorsque vous ouvrez le Data Workbench.

Les coches (et leurs couleurs) indiquent le ou les dossiers de profil sur le serveur Data Workbench et les ordinateurs Data Workbench sur lesquels chaque fichier réside, s&#39;il existe plusieurs copies d&#39;un fichier et si ces copies multiples ont la même date et heure de modification. Ces fichiers sont synchronisés entre le serveur Data Workbench et les ordinateurs Data Workbench pendant le téléchargement du profil.

Vous trouverez ci-dessous un exemple [!DNL Profile Manager] pour une mise en oeuvre HBX :

![](assets/client-prof.png)

Dans le menu [!DNL Profile Manager], vous pouvez ouvrir n&#39;importe lequel des autres gestionnaires (par exemple, [!DNL Dimensions Manager] ou [!DNL Reports Manager]), qui n&#39;affiche que des portions particulières de [!DNL Profile Manager]. Vous pouvez également créer de nouveaux gestionnaires de profil. Voir [Création de nouveaux gestionnaires de Profil](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Une coche en regard d’un nom de fichier dans une colonne particulière indique qu’un fichier de ce nom réside dans le dossier nommé dans cette colonne (profil). Lorsque vous vous déplacez vers la droite dans [!DNL Profile Manager], les fichiers sont prioritaires sur ceux de gauche, c&#39;est-à-dire que chaque profil hérité s&#39;appuie sur les profils de gauche dans [!DNL Profile Manager]. Par exemple, si vous avez un fichier du même nom et situé au même emplacement dans le profil [!DNL Base] (colonne) et dans le profil [!DNL User] (colonne), le fichier du profil [!DNL User] est utilisé à la place du fichier dans le profil [!DNL Base].

## Rechercher des profils {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Avec Data Workbench 5.5, un champ de recherche a été ajouté pour trouver les profils requis dans [!DNL Profile Manager].

![](assets/client-prof2.png)

Les types de colonnes suivants apparaissent dans le [!DNL Profile Manager] :

* Les colonnes *nom de profil hérité* contiennent des coches pour les fichiers qui résident dans chaque dossier de profil. Les profils hérités comprennent les profils internes fournis par l’Adobe ainsi que tous les profils spécifiques à une société ou à un rôle que vous créez et gérez. Dans l’exemple ci-dessus, les profils internes incluent Base, Trafic, Valeur, Marketing, etc. Le profil interne [!DNL Base], qui contient les blocs de construction de base et les informations de configuration nécessaires à l&#39;exécution de l&#39;application d&#39;Adobe, est fourni avec chaque implémentation. Les autres profils internes contiennent des éléments (espaces de travail, mesures, dimensions dérivées, etc.) liés à des types particuliers d’informations, tels que le trafic Web ou le marketing. L’Adobe fournit uniquement les profils appropriés au type de données que vous analysez et à votre secteur d’activité.

   >[!NOTE]
   >
   >Par défaut, les profils internes (ceux fournis par Adobe) ne peuvent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d&#39;autres profils que vous créez. Si vous créez une application et devez modifier un profil interne, vous devez modifier le paramètre Modifier les Profils internes dans le fichier [!DNL Insight.cfg]. Voir [Paramètres de configuration d’Insight](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) pour plus d’informations. Avant de procéder, contactez les Services de conseil en Adobe.

* La colonne *nom du profil de travail*, qui est toujours la colonne suivante à la dernière, contient des coches pour les fichiers qui résident dans le dossier du profil de travail actuel. Dans l’exemple ci-dessus, le profil de travail est Dataset. Votre profil de travail est soit un profil de jeu de données, soit un profil spécifique au rôle. Les fichiers de ce dossier sont prioritaires sur les fichiers portant le même nom dans tout dossier de profil hérité.
* La colonne [!DNL User], qui est toujours la dernière colonne, contient des coches pour les fichiers et les dossiers qui résident sous forme de fichiers locaux dans le dossier User\*profil name*. La structure des répertoires du dossier Utilisateur imite celle du profil de travail et chaque dossier Utilisateur\*nom du profil* contient des copies locales des espaces de travail, des mesures, des dimensions et des fichiers de configuration pour ce profil particulier. Ces copies locales ont la priorité sur les fichiers portant le même nom dans tout dossier hérité ou de profil de travail. Les fichiers de la colonne [!DNL User] ont été créés et enregistrés uniquement dans le dossier User\*profil name* ou se trouvent dans un profil interne ou de travail ainsi que dans le dossier User\*profil name*. Les fichiers de chaque dossier peuvent être identiques ou non et peuvent avoir ou non la même date et heure de modification.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Pour éviter de modifier votre jeu de données uniquement localement, le serveur de Data Workbench ignore les copies locales du fichier [!DNL profile.cfg] et les fichiers des dossiers Dataset ou Export du dossier User\*profil name*. Les fichiers ignorés sont identifiés par un arrière-plan rouge dans la colonne [!DNL User] et un avertissement &quot;Ignoré dans le répertoire utilisateur&quot; dans le menu contextuel. Pour mettre en oeuvre les modifications que vous apportez dans vos copies locales de ces fichiers, vous devez les enregistrer dans votre profil de travail afin qu’elles puissent être synchronisées avec le serveur Data Workbench. Pour savoir comment enregistrer des fichiers sur votre profil de travail, voir [Publication de fichiers sur votre Profil de travail](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
      >    
      >    
   * Un trait d’union (-) au lieu d’une coche dans une colonne identifie un fichier vide (zéro octet). Le Data Workbench considère les fichiers à zéro octet comme inexistants, ce qui vous permet de les utiliser pour masquer les fichiers inclus dans un profil à gauche. Voir [Masquage des fichiers à l’aide de fichiers vides (sur zéro octet)](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Détermination des versions de fichier {#section-225d732246b94cbe87acdfa9c881d6af}

Comme mentionné dans la section précédente, les coches de [!DNL Profile Manager] sont codées par couleur afin que vous puissiez facilement identifier l’emplacement d’un fichier et déterminer si les copies multiples d’un fichier ont été modifiées à des moments différents.

Si un fichier ou un répertoire réduit est exactement identique au fichier ou au répertoire à sa gauche, la même coche de couleur que le fichier ou le répertoire de cette colonne (profil) est cochée. Si elle diffère d’un fichier ou d’un répertoire à sa gauche ou si le fichier ou le répertoire n’existe que dans la colonne [!DNL User], la coche est blanche.

![](assets/vis_ProfMgr_LocalFiles.png)

Le [!DNL Profile Manager] illustré dans l&#39;exemple ci-dessus indique ce qui suit :

* Une coche blanche pour le fichier [!DNL A New Metric.metric] s&#39;affiche uniquement dans la colonne [!DNL User], ce qui indique que vous disposez uniquement d&#39;une copie locale de ce fichier, qui n&#39;a pas été publié (ou téléchargé) sur le serveur Data Workbench pour que d&#39;autres utilisateurs Data Workbench puissent y accéder.

* Les coches correspondant au nom de fichier [!DNL Average Score.metric] apparaissent dans les colonnes Films et [!DNL User]. La coche de la colonne [!DNL User] est de la même couleur que la coche de la colonne Films, ce qui indique que la copie locale du fichier a la même date et heure de modification que le fichier du dossier Films.

* Les coches correspondant au nom de fichier [!DNL Average Score Error.metric] apparaissent dans les colonnes Films et [!DNL User]. La coche de la colonne [!DNL User] est blanche, ce qui indique que la copie locale du fichier a une date ou une heure de modification différente de celle du fichier dans le dossier Films.

