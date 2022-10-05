---
description: Pour utiliser le portail de rapports, vous devez installer et configurer un ensemble de pages de serveur d’applications (ASP) sur IIS.
title: Installation du portail de rapports
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Installation du portail de rapports{#installing-the-report-portal}

{{eol}}

Pour utiliser le portail de rapports, vous devez installer et configurer un ensemble de pages de serveur d’applications (ASP) sur IIS.

**Avant de commencer**

Les procédures décrites dans ce chapitre décrivent comment installer et configurer [!DNL Report Portal]. Pour effectuer ces procédures, vous devez :

* Demandez à Microsoft IIS d&#39;être installé et de connaître sa version.
* connaître les noms des jeux de rapports dont les rapports sont affichés par ; [!DNL Report Portal].
* connaître l’emplacement du répertoire dans lequel [!DNL Report Server] enregistre la sortie pour ces jeux de rapports. Assurez-vous que le serveur d’applications IIS a accès à ce répertoire.

>[!NOTE]
>
>* À afficher à l’aide de [!DNL Report Portal], les rapports doivent respecter des conventions de dénomination spécifiques. En outre, le répertoire dans lequel les rapports sont enregistrés doit respecter une structure définie. Pour une description de ces exigences, voir [Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* Les mots de passe du portail de rapports sont désormais compatibles avec AES-256 bits. Si vous passez à la version 2.0 du portail de rapports, augmentez la taille du champ Mot de passe de 50 à 150 dans la variable **users.mdb** base de données. L’augmentation de la taille du champ est requise pour s’adapter aux mots de passe avec un chiffrement mis à jour.
>* Si vous effectuez une mise à niveau vers le portail de rapports 2.0, augmentez la taille du champ pour la variable **Mot de passe** de 50 à 150 dans la base de données users.mdb. L’augmentation de la taille du champ est requise pour s’adapter aux mots de passe avec un chiffrement mis à jour.
>* Le portail de rapports propose désormais des algorithmes de hachage plus forts avec prise en charge de l’impression. Si vous effectuez une mise à niveau vers **Portail de rapports 2.1**, ajoutez un nouveau champ Texte , *PasswordSalt* avec une taille de champ de 20 caractères dans [!DNL users.mdb]base de données. Ce champ est obligatoire pour stocker le sel de mot de passe.
>

