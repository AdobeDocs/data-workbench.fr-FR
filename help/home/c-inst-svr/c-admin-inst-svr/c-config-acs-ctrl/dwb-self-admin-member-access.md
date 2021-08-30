---
description: Les administrateurs peuvent permettre aux utilisateurs de la station de travail de gérer de manière partielle le contrôle d’accès des groupes personnalisés.
title: Administration des utilisateurs de l’accès aux membres des groupes
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Administration des utilisateurs de l’accès aux membres des groupes{#user-administration-of-group-member-access}

Les administrateurs peuvent permettre aux utilisateurs de la station de travail de gérer de manière partielle le contrôle d’accès des groupes personnalisés.

**L’auto-administration de l’** accès aux membres des groupes donne aux non-administrateurs les droits d’ajouter et de supprimer des membres dans un groupe personnalisé. L’administrateur crée un fichier **User List** et configure l’accès au groupe dans le fichier [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) pour les nouveaux membres du groupe.

**Accès au gestionnaire des serveurs**

La configuration du fichier **[!DNL User List]** et sa synchronisation avec le fichier **[!DNL Communications.cfg]** sont effectuées dans l’espace de travail **Gestionnaire de serveurs**.

1. Sur le plan de travail, cliquez sur l’onglet **Admin** > **Jeu de données et profil** .

1. Ouvrez l’espace de travail **Gestionnaire de serveurs** .
1. Cliquez avec le bouton droit de la souris dans le diagramme avec le bouton droit de la souris >*nom de votre serveur* et sélectionnez **Fichiers**.

   Les fichiers du serveur s’ouvrent dans une table avec les colonnes *Fichier*, *`<server name>`* et *Temp*.

1. **Effectuez un clic** droit sur Localby dans la colonne serveur d’un fichier serveur (pour cette fonctionnalité  **[!DNL Access Control]** et  **[!DNL Components/Communications.cfg)]**).

   Une coche blanche apparaît dans la colonne **Temp**. Vous pouvez les modifier dans le dossier Temp . Cliquez ensuite avec le bouton droit de la souris sur la coche et **enregistrez sur** le serveur. (Il devient rouge lors de la synchronisation avec le serveur).

## Création d’un fichier User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

L’administrateur doit créer un fichier **[!DNL User List.cfg]** dans le dossier **[!DNL Access Control]**.

1. Cliquez avec le bouton droit de la souris sur la ligne ** Contrôle d’accès** dans la colonne **Temp** et sélectionnez **Ouvrir** > **Dossier**. ![](assets/6_4_workstation_groups_3.png)

   Le dossier Contrôle d’accès du dossier **Temp** s’ouvre, répertoriant un seul fichier **[!DNL Access Control.cfg]**.

1. Ajoutez un autre fichier texte à ce dossier et nommez-le **[!DNL User List.cfg]** (en regard de **[!DNL Access Control.cfg]**).

1. Ajoutez les paramètres suivants au fichier **[!DNL User List.cfg]**.

Le fichier User List doit contenir un vecteur d’objets **AccessGroup**, et chaque objet **AccessGroup** doit avoir un nom et un vecteur de chaînes appelé **Members**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Vous pouvez ensuite modifier et ajouter les utilisateurs dans la vue Workstation du fichier **[!DNL User List.cfg]**.

![](assets/6_4_workstation_groups_4.png)

Voici les paramètres les plus élémentaires à ajouter au fichier **[!DNL User List.cfg]**. Les membres peuvent ensuite être ajoutés dans la vue de la station de travail.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Comme pour tout fichier **[!DNL .cfg]** que vous modifiez manuellement, veillez à utiliser des espaces plutôt que des onglets et à prêter une attention particulière à l’espace blanc et à la syntaxe. Une erreur dans ce fichier entraînera l’exclusion du fichier de liste d’utilisateurs de *Adobe Insight Server*.

Le champ **Nom** de chaque **Groupe d’accès** sera référencé dans le fichier [!DNL Access Control.cfg].

>[!NOTE]
>
>Seuls les membres valides avec des préfixes de service d’annuaire, tels que **CN:** ou **OU:**, sont acceptés et ne peuvent pas contenir de caractère générique (*).

## Configuration du fichier Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Un administrateur active d’abord cette fonctionnalité en ouvrant le fichier **[!DNL Components]>[!DNL Communications.cfg]** et en ajoutant une nouvelle clé nommée **[!DNL Access Control User List File]**. La valeur string de cette clé est le chemin d’accès à ce nouveau fichier.

1. Dans les fichiers du serveur, cliquez sur **Composants** et cliquez avec le bouton droit de la souris sur la coche dans la colonne du serveur. Cliquez sur **Rendre local**.

   Une coche blanche apparaît dans la colonne **Temp**.

1. Cliquez avec le bouton droit sur la coche dans la colonne **Temp** et sélectionnez **Ouvrir** > **dans la station de travail**.

1. Dans le fichier **Communication.cfg**, cliquez avec le bouton droit de la souris sur **component** et sélectionnez **Ajouter une clé personnalisée.** ![](assets/6_4_workstation_groups.png)

1. Saisissez le **Nom** *Fichier de liste d’utilisateurs du contrôle d’accès* et définissez **De type** comme *Chaîne*.

   >[!NOTE]
   Vous ne pouvez pas créer de fichier de liste sous la forme d’un chemin d’accès. Pour remédier à ce problème, vous devez enregistrer le fichier, l’ouvrir dans un éditeur (Bloc-notes) et remplacer &quot;Chaîne&quot; par &quot;Chemin&quot; :

   Avant que les valeurs de:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   Après:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. Enregistrez le fichier **[!DNL Communications.cfg]** et (si nécessaire) enregistrez-le sur le serveur. Cela redémarrera les composants dans le serveur pour vous assurer que vous n’avez commis aucune erreur pouvant empêcher l’analyse du fichier **[!DNL Communications.cfg]**.
1. Si votre système comprend des serveurs de traitement, modifiez le fichier de configuration dans le fichier **[!DNL Components for Processing Servers.cfg]**.
1. Cliquez avec le bouton droit de la souris sur **[!DNL Communications.cfg]** et enregistrez-le sur le serveur.

L’administrateur du Data Workbench peut maintenant confirmer que le ou les utilisateurs prévus ont accès au fichier de liste d’utilisateurs et permettre aux utilisateurs de gérer le groupe. Les utilisateurs pourront ouvrir le fichier User List, le modifier, ajouter et supprimer des membres CN ou OU si nécessaire.

## Synchronisation du fichier Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

L&#39;administrateur peut ensuite modifier la balise **[!DNL Access Control.cfg]** et insérer des références au(x) groupe(s) défini(s) par le fichier *User List* .

Les références au ou aux groupes doivent être insérées comme tout autre membre, mais avec la syntaxe suivante :

```
$(Group Name)
```

Où &quot;Nom de groupe&quot; correspond à ce qui est défini dans le fichier de liste d’utilisateurs, y compris les espaces blancs. ![](assets/6_4_workstation_groups_2.png)

À ce stade, l’administrateur du Data Workbench peut confirmer que certains utilisateurs du groupe ont accès au fichier de liste d’utilisateurs. Les utilisateurs sélectionnés peuvent alors ouvrir le fichier **[!DNL User List.cfg]**, le modifier, ajouter et supprimer des membres CN ou OU si nécessaire.
