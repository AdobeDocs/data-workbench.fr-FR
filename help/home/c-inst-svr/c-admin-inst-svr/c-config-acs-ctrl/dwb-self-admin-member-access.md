---
description: Les administrateurs peuvent permettre aux utilisateurs de la station de travail de gérer de manière partielle le contrôle d’accès des groupes personnalisés.
title: Administration utilisateur de l’accès des membres du groupe
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# User Administration of Group Member Access{#user-administration-of-group-member-access}

Les administrateurs peuvent permettre aux utilisateurs de la station de travail de gérer de manière partielle le contrôle d’accès des groupes personnalisés.

**L’auto-administration de l’accès** aux membres du groupe donne aux non-administrateurs les droits d’ajouter et de supprimer des membres dans un groupe personnalisé. L’administrateur crée un fichier Liste **des** utilisateurs et configure l’accès des groupes dans le fichier [Access Control.cfg](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) pour les nouveaux membres du groupe.

**Accès au Gestionnaire de serveurs**

La configuration du **[!DNL User List]** fichier et sa synchronisation avec le **[!DNL Communications.cfg]** fichier sont effectuées dans l’espace de travail **Servers Manager** .

1. Sur le plan de travail, cliquez sur l’onglet **Admin** > **Jeu de données et profil** .

1. Ouvrez l’espace de travail **Servers Manager** .
1. Cliquez avec le bouton droit de la souris >*votre nom* de serveur > dans le diagramme et sélectionnez **Fichiers**.

   Les fichiers du serveur s’ouvrent dans un tableau avec des colonnes *Fichier*, *`<server name>`* et *Temp*.

1. **Pour rendre Local** , cliquez avec le bouton droit de la souris dans la colonne serveur d’un fichier serveur (pour cette fonctionnalité **[!DNL Access Control]** et **[!DNL Components/Communications.cfg)]**.

   Une coche blanche apparaît dans la colonne **Temp** . Vous pouvez le modifier dans le dossier Temp. Cliquez ensuite avec le bouton droit de la souris sur la coche et **enregistrez sur** le serveur. (Il devient rouge lors de la synchronisation avec le serveur).

## Création d’un fichier User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

L’administrateur doit créer un **[!DNL User List.cfg]** fichier dans le **[!DNL Access Control]** dossier.

1. Cliquez avec le bouton droit de la souris sur la ligne Contrôle d’accès*** dans la colonne **Temp** et sélectionnez **Ouvrir** > **Dossier**. ![](assets/6_4_workstation_groups_3.png)

   Le dossier Access Control du dossier **Temp** s’ouvre et répertorie un seul **[!DNL Access Control.cfg]** fichier.

1. Ajoutez un autre fichier texte à ce dossier et nommez-le **[!DNL User List.cfg]** (en regard du **[!DNL Access Control.cfg]**).

1. Add the following parameters to the **[!DNL User List.cfg]** file.

Le fichier de liste d’utilisateurs doit contenir un vecteur d’objets **AccessGroup** et chaque objet **AccessGroup** doit avoir un nom et un vecteur de chaînes appelés **Membres**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Vous pouvez ensuite modifier et ajouter les utilisateurs dans la vue Station de travail du fichier **[!DNL User List.cfg]**s.

![](assets/6_4_workstation_groups_4.png)

Voici les paramètres de base à ajouter au **[!DNL User List.cfg]** fichier. Les membres peuvent ensuite être ajoutés dans la vue Station de travail.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Comme pour tout **[!DNL .cfg]** fichier que vous modifiez manuellement, veillez à utiliser des espaces au lieu de tabulations et à prêter une attention particulière à l’espace blanc et à la syntaxe. Une erreur dans ce fichier entraînera l’ignorance du fichier de liste des utilisateurs par *Adobe Insight Server* .

Le champ **Nom** de chaque groupe **d&#39;** accès est référencé dans le [!DNL Access Control.cfg] fichier.

>[!NOTE]
>
>Seuls les membres valides avec des préfixes de service d’annuaire, tels que **CN :** ou **OU :** sont acceptées et ne peuvent pas contenir de caractère générique (*).

## Configuration du fichier Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Pour activer cette fonctionnalité, un administrateur doit d’abord ouvrir le fichier **[!DNL Components]>[!DNL Communications.cfg]**et ajouter une nouvelle clé portant le nom **[!DNL Access Control User List File]**. La valeur de chaîne de cette clé est le chemin d’accès à ce nouveau fichier.

1. Dans les fichiers du serveur, cliquez sur **Composants** , puis cliquez avec le bouton droit de la souris sur la coche dans la colonne du serveur. Cliquez sur **Rendre local**.

   Une coche blanche apparaît dans la colonne **Temp** .

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne **Temp** et sélectionnez **Ouvrir** > **dans Workstation**.

1. Dans le fichier **Communication.cfg** , cliquez avec le bouton droit sur **le composant** et sélectionnez **Ajouter une clé personnalisée.** ![](assets/6_4_workstation_groups.png)

1. Tapez le **Nom** comme Fichier *de liste des utilisateurs du contrôle d&#39;* accès et définissez **De type** comme *Chaîne.*

   >[!NOTE]
   Vous ne pouvez pas créer le nouveau fichier de liste en tant que chemin d’accès. Pour y remédier, vous devez enregistrer le fichier, l’ouvrir dans un éditeur (Bloc-notes) et remplacer &quot;Chaîne&quot; par &quot;Chemin&quot; :

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

1. Enregistrez le **[!DNL Communications.cfg]** fichier et (si nécessaire) enregistrez-le sur le serveur. Cela redémarrera les composants du serveur pour vous assurer que vous n’avez commis aucune erreur susceptible d’empêcher l’analyse du **[!DNL Communications.cfg]** fichier.
1. Si votre système comprend des serveurs de traitement, modifiez le fichier de configuration dans le **[!DNL Components for Processing Servers.cfg]** fichier.
1. Cliquez avec le bouton droit **[!DNL Communications.cfg]** et enregistrez sur le serveur.

L’administrateur des outils de données peut désormais confirmer que les utilisateurs prévus ont accès au fichier de liste d’utilisateurs et permettre aux utilisateurs de gérer le groupe. Les utilisateurs pourront ouvrir le fichier de liste d&#39;utilisateurs, le modifier, ajouter et supprimer des membres CN ou OU selon les besoins.

## Synchronisation du fichier Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

L’administrateur peut alors modifier les références **[!DNL Access Control.cfg]** et insérer des références au(x) groupe(s) défini(s) par le fichier de liste *d’* utilisateurs.

Les références au(x) groupe(s) doivent être insérées comme tout autre membre, mais avec la syntaxe suivante:

```
$(Group Name)
```

Où &quot;Nom du groupe&quot; correspond à ce qui est défini dans le fichier de liste des utilisateurs, y compris les espaces blancs. ![](assets/6_4_workstation_groups_2.png)

A ce stade, l’administrateur des outils de données peut confirmer que certains utilisateurs du groupe ont accès au fichier de liste d’utilisateurs. Les utilisateurs sélectionnés peuvent alors ouvrir le **[!DNL User List.cfg]** fichier, le modifier et ajouter ou supprimer des membres CN ou OU selon les besoins.
