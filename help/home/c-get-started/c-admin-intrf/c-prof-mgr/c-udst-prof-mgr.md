---
description: Les noms de dossier et de fichier inclus dans votre implémentation sont affichés sur le côté gauche du Gestionnaire de profils.
solution: Analytics
title: Gestionnaire de profils
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gestionnaire de profils{#profile-manager}

Les noms de dossier et de fichier inclus dans votre implémentation sont affichés sur le côté gauche du Gestionnaire de profils.

Les profils qui constituent votre application s’affichent sous forme de colonnes individuelles dans la [!DNL Profile Manager]. Ces profils comprennent plusieurs profils hérités et un profil de travail unique.

>[!NOTE]
>
>Votre profil de travail (un profil de jeu de données ou un profil spécifique au rôle) est le profil que vous chargez lorsque vous ouvrez Outils de données.

Les coches (et leurs couleurs) indiquent le ou les dossiers de profil sur les ordinateurs du serveur Outils de données et des outils de données sur lesquels réside chaque fichier, s’il existe plusieurs copies d’un fichier et si ces copies multiples ont la même date et heure de modification. Ces fichiers sont synchronisés entre le serveur Outils de données et les ordinateurs Outils de données au cours du téléchargement du profil.

Voici un exemple [!DNL Profile Manager] d’implémentation HBX :

![](assets/client-prof.png)

Dans le [!DNL Profile Manager] menu, vous pouvez ouvrir n’importe quel autre gestionnaire (par exemple, le [!DNL Dimensions Manager] ou [!DNL Reports Manager]), qui affiche uniquement certaines parties de [!DNL Profile Manager]. Vous pouvez également créer de nouveaux gestionnaires de profil. Voir [Création de nouveaux gestionnaires](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)de profil.

Une coche en regard d’un nom de fichier dans une colonne particulière indique qu’un fichier portant ce nom réside dans le dossier nommé dans cette colonne (profil). Au fur et à mesure que vous vous déplacez vers la droite dans [!DNL Profile Manager], les fichiers sont prioritaires sur ceux de gauche, c’est-à-dire que chaque profil hérité est basé sur les profils à sa gauche dans le [!DNL Profile Manager]. Par exemple, si vous disposez d’un fichier du même nom et situé au même emplacement dans le [!DNL Base] profil (colonne) et dans le [!DNL User] profil (colonne), le fichier du [!DNL User] profil est utilisé à la place du fichier du [!DNL Base] profil.

## Rechercher des profils {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Avec Outils de données version 5.5, un champ de recherche a été ajouté pour trouver les profils requis dans la [!DNL Profile Manager].

![](assets/client-prof2.png)

Les types de colonnes suivants s’affichent dans [!DNL Profile Manager]:

* Les colonnes de nom *de profil* héritées contiennent des coches pour les fichiers qui résident dans chaque dossier de profil. Les profils hérités incluent les profils internes fournis par Adobe, ainsi que tous les profils spécifiques à une entreprise ou à un rôle que vous créez et gérez. Dans l’exemple ci-dessus, les profils internes incluent Base, Trafic, Valeur, Marketing, etc. Le [!DNL Base] profil interne, qui contient les blocs de création de base et les informations de configuration nécessaires à l’exécution de votre application Adobe, est fourni avec chaque implémentation. Les autres profils internes contiennent des éléments (espaces de travail, mesures, dimensions dérivées, etc.) liés à des types particuliers d’informations, tels que le trafic Web ou le marketing. Adobe fournit uniquement les profils adaptés au type de données que vous analysez et à votre secteur d’activité.

   >[!NOTE]
   >
   >Par défaut, les profils internes (fournis par Adobe) ne peuvent pas être modifiés. Toute personnalisation doit se produire dans votre jeu de données, dans vos profils spécifiques au rôle ou dans d’autres profils que vous créez. Si vous créez une nouvelle application et devez modifier un profil interne, vous devez modifier le paramètre Modifier les profils internes dans le [!DNL Insight.cfg] fichier. Pour plus d’informations, voir Paramètres [de configuration](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) Insight. Avant de procéder, contactez les services de conseil Adobe.

* La colonne du nom *du profil de* travail, qui est toujours la dernière colonne, contient des coches pour les fichiers qui résident dans le dossier du profil de travail actuel. Dans l’exemple ci-dessus, le profil de travail est Dataset. Votre profil de travail est soit un profil de jeu de données, soit un profil spécifique au rôle. Les fichiers de ce dossier sont prioritaires sur les fichiers portant le même nom dans tout dossier de profil hérité.
* La [!DNL User] colonne, qui est toujours la dernière colonne, contient des coches pour les fichiers et les dossiers qui résident sous forme de fichiers locaux dans le dossier User\*profile name*. La structure de répertoires du dossier Utilisateur imite celle du profil de travail et chaque dossier User\*nom du profil* contient des copies locales des espaces de travail, des mesures, des dimensions et des fichiers de configuration de ce profil particulier. Ces copies locales ont la priorité sur les fichiers portant le même nom dans tout dossier de profil hérité ou de profil de travail. Les fichiers de la [!DNL User] colonne ont été créés et enregistrés uniquement dans le dossier User\*profile name*, ou ils résident dans un profil interne ou de travail, ainsi que dans le dossier User\*profile name*. Les fichiers de chaque dossier peuvent être identiques ou non et peuvent avoir la même date et heure de modification.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Pour éviter de modifier votre jeu de données uniquement localement, le serveur Outils de données ignore les copies locales du [!DNL profile.cfg] fichier et les fichiers des dossiers Jeu de données ou Exportation du dossier Utilisateur\*nom du profil*. Les fichiers ignorés sont identifiés par un arrière-plan rouge dans la [!DNL User] colonne et un avertissement &quot;Ignoré dans le répertoire utilisateur&quot; dans le menu contextuel. Pour mettre en oeuvre les modifications que vous apportez dans vos copies locales de ces fichiers, vous devez les enregistrer dans votre profil de travail afin qu’ils puissent être synchronisés avec le serveur Outils de données. Pour savoir comment enregistrer des fichiers dans votre profil de travail, voir [Publication de fichiers dans votre profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de travail.
      >    
      >    
   * Un trait d’union (-) au lieu d’une coche dans une colonne identifie un fichier vide (zéro octet). Les outils de données traitent les fichiers sans octet comme inexistants, ce qui vous permet de les utiliser pour masquer les fichiers inclus dans un profil vers la gauche. Voir [Masquage de fichiers à l’aide de fichiers](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)vides (zéro octet).


## Détermination des versions des fichiers {#section-225d732246b94cbe87acdfa9c881d6af}

Comme mentionné dans la section précédente, les coches de la [!DNL Profile Manager] section sont codées par couleur afin que vous puissiez facilement identifier l’emplacement d’un fichier et déterminer si les copies multiples d’un fichier ont été modifiées à différents moments.

Si un fichier ou un répertoire réduit est exactement le même que le fichier ou le répertoire à sa gauche, il a la même coche de couleur que le fichier ou le répertoire de cette colonne (profil). S’il est différent d’un fichier ou d’un répertoire à sa gauche ou si le fichier ou le répertoire n’existe que dans la [!DNL User] colonne, la coche est blanche.

![](assets/vis_ProfMgr_LocalFiles.png)

L’ [!DNL Profile Manager] exemple ci-dessus indique ce qui suit :

* Une coche blanche pour le [!DNL A New Metric.metric] fichier apparaît uniquement dans la [!DNL User] colonne, ce qui indique que vous n’avez qu’une copie locale de ce fichier : il n’a pas été publié (ou téléchargé) sur le serveur Outils de données pour que d’autres utilisateurs puissent y accéder.

* Les cases à cocher correspondant au nom du [!DNL Average Score.metric] fichier apparaissent dans les films et les [!DNL User] colonnes. La coche de la [!DNL User] colonne est de la même couleur que la coche de la colonne Films, ce qui indique que la copie locale du fichier a la même date et heure de modification que le fichier du dossier Films.

* Les cases à cocher correspondant au nom du [!DNL Average Score Error.metric] fichier apparaissent dans les films et les [!DNL User] colonnes. La coche de la [!DNL User] colonne est blanche, ce qui indique que la copie locale du fichier a une date ou une heure de modification différente de celle du fichier dans le dossier Films.

