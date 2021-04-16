---
description: Pour utiliser Report Portal, vous devez installer et configurer un ensemble de pages de serveur d’applications (ASP) sur IIS.
title: Installation du portail de rapports
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Installation du portail de rapports{#installing-the-report-portal}

Pour utiliser Report Portal, vous devez installer et configurer un ensemble de pages de serveur d’applications (ASP) sur IIS.

**Avant de commencer**

Les procédures décrites dans ce chapitre décrivent comment installer et configurer [!DNL Report Portal]. Pour effectuer ces procédures, vous devez :

* Microsoft IIS est installé et connaît sa version.
* connaître les noms des jeux de rapports dont les rapports sont affichés par [!DNL Report Portal].
* connaître l&#39;emplacement du répertoire dans lequel [!DNL Report Server] enregistre la sortie pour ces jeux de rapports. Assurez-vous que le serveur d’applications IIS a accès à ce répertoire.

>[!NOTE]
>
>* Pour être visualisés à l’aide de [!DNL Report Portal], les rapports doivent respecter des conventions d’affectation de nom spécifiques. En outre, le répertoire dans lequel les rapports sont enregistrés doit respecter une structure prescrite. Pour obtenir une description de ces exigences, voir [Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Les mots de passe du portail de rapports sont désormais conformes à la norme AES-256 bits. Si vous effectuez une mise à niveau vers Report Portal 2.0, augmentez la taille du champ Mot de passe de 50 à 150 dans la base de données **users.mdb**. L’augmentation de la taille du champ est nécessaire pour contenir les mots de passe avec un chiffrement mis à jour.
>* Si vous effectuez une mise à niveau vers Report Portal 2.0, augmentez la taille du champ **Mot de passe** de 50 à 150 dans la base de données users.mdb. L’augmentation de la taille du champ est nécessaire pour contenir les mots de passe avec un chiffrement mis à jour.
>* Le portail de rapports propose désormais des algorithmes de hachage plus puissants, avec prise en charge de l’annonce. Si vous effectuez une mise à niveau vers **Report Portal 2.1**, ajoutez un nouveau champ de texte, *PasswordSalt*, dont la taille du champ est de 20 caractères dans la base de données [!DNL users.mdb]. Ce champ est obligatoire pour stocker le mot de passe sel.

>


