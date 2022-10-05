---
description: Le fichier Internal.cfg appliqué dans le Gestionnaire de profils empêche les modifications apportées par les utilisateurs à vos profils personnalisés par les gestionnaires Profil, Dimensions, Rapports, Espaces de travail, Mesures et Filtres.
title: Verrouillage de profils dans la station de travail
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 5%

---

# Verrouillage de profils dans la station de travail{#locking-profiles-in-the-workstation}

{{eol}}

Le fichier Internal.cfg appliqué dans le Gestionnaire de profils empêche les modifications apportées par les utilisateurs à vos profils personnalisés par les gestionnaires Profil, Dimensions, Rapports, Espaces de travail, Mesures et Filtres.

Vous pouvez empêcher la modification et le remplacement des fichiers de profil lors de l’utilisation des gestionnaires en enregistrant la variable **[!DNL Internal.cfg]** à votre profil personnalisé dans le Gestionnaire de profils. Ce fichier de configuration empêche les utilisateurs d’écraser plusieurs fichiers lorsqu’ils travaillent dans les gestionnaires (accessible à partir du **Administration** > **Profil** ).

**Verrouillage de profils dans le Gestionnaire de profils**

1. Dans l’espace de travail, cliquez avec le bouton droit de la souris **Administration** > **Gestionnaire de profil**.

1. Dans le **Gestionnaire de profil**, clic droit **[!DNL Context > Internal.cfg]** et **Rendre local**.

1. Coche contextuelle dans **Utilisateur** et enregistrez dans une `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Remarque**: Seules les modifications apportées aux fichiers de profil par les gestionnaires sont empêchées lors de l’enregistrement de la variable **[!DNL Internal.cfg]** à un profil personnalisé dans le Gestionnaire de profils. Vous pouvez tout de même enregistrer les espaces de travail sur le serveur à partir du plan de travail à l’aide du **Enregistrer sur le serveur** .
