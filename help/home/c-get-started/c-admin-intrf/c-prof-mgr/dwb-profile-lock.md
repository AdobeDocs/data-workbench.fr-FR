---
description: Le fichier Internal.cfg appliqué dans le Gestionnaire de profils empêche les utilisateurs de modifier vos profils personnalisés par les gestionnaires Profil, Dimensions, Rapports, Espaces de travail, Mesures et Filtres.
title: Verrouillage des profils dans la station de travail
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verrouillage des profils dans la station de travail{#locking-profiles-in-the-workstation}

Le fichier Internal.cfg appliqué dans le Gestionnaire de profils empêche les utilisateurs de modifier vos profils personnalisés par les gestionnaires Profil, Dimensions, Rapports, Espaces de travail, Mesures et Filtres.

Vous pouvez empêcher la modification et le remplacement des fichiers de profil lors de l’utilisation des gestionnaires en enregistrant le **[!DNL Internal.cfg]** fichier dans votre profil personnalisé dans le Gestionnaire de profils. Ce fichier de configuration empêche les utilisateurs d’écraser plusieurs fichiers lorsqu’ils travaillent dans les gestionnaires (accessible à partir du menu **Admin** > **Profil** ).

**Verrouillage des profils dans le Gestionnaire de profils**

1. Dans l’espace de travail, cliquez avec le bouton droit de la souris sur **Admin** > Gestionnaire de **profils**.

1. Dans le Gestionnaire **de** profils, cliquez avec le bouton droit **[!DNL Context > Internal.cfg]** et **Rendre local**.

1. Cochez la case avec le bouton droit de la souris dans la colonne **Utilisateur** et enregistrez-la dans une `<custom profile>`colonne.

![](assets/dwb_lock_profiles.png)

**Remarque**: Seules les modifications apportées aux fichiers de profil par les gestionnaires sont évitées lors de l’enregistrement **[!DNL Internal.cfg]** dans un profil personnalisé dans le Gestionnaire de profils. Vous pouvez toujours enregistrer les espaces de travail sur le serveur à partir du plan de travail à l’aide de la commande **Enregistrer sur le serveur** .
