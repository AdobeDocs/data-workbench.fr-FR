---
description: Ce guide rapide décrit les étapes minimales requises pour valider la configuration FTP interne et externe.
title: Validation des serveurs FTP internes et externes
uuid: bc381c1d-df27-4009-920b-1a804b36c204
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Validation des serveurs FTP internes et externes{#validation-of-internal-and-external-ftp-servers}

Ce guide rapide décrit les étapes minimales requises pour valider la configuration FTP interne et externe.

Un FTP interne est utilisé lorsqu’un consultant/architecte interne d’Adobe doit se connecter au site FTP pour le téléchargement ou le téléchargement de fichiers, tandis qu’un FTP externe est principalement destiné à vous, en tant qu’utilisateur, pour le transfert des fichiers de données requis.

Pour plus d’informations sur la configuration des serveurs FTP, voir Protocole [de transfert de](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html)fichiers.

## Étapes de validation - FTP externe {#section-24428111b5c542ce81a765cd63424b97}

1. Ouvrez une invite de commande. (Windows+R et saisissez cmd)
1. Type ftp `<ftp server>`
1. Indiquez le nom d’utilisateur et le mot de passe. ![](assets/dwb_impl_ftp1.png)

1. Modifiez le répertoire local à partir duquel un fichier peut être déplacé. Utilisez cette commande :

[!DNL ftp> lcd C:\Users\andixit\Desktop]

répertoire local maintenant [!DNL C:\Users\andixit\Desktop].

1. Copiez le fichier depuis l’emplacement local vers l’emplacement distant. ![](assets/dwb_impl_ftp2.png)

1. Déconnectez-vous du serveur distant. (Utiliser sous la commande)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Une autre façon de valider le FTP est d&#39;utiliser Filezilla. Indiquez le nom d’hôte, le nom d’utilisateur, le mot de passe et le port. Le côté droit du panneau est le site distant et le côté gauche est le site local. Pour valider le protocole FTP, faites glisser et déposez les fichiers du site local vers le site distant et vers la version v.v.

![](assets/dwb_impl_ftp3.png)

## Étapes de validation - FTP interne {#section-b1f7a789ad6848cf9027f7953d81066e}

Les étapes ci-dessus peuvent être suivies pour valider le fichier ftp interne à partir de n’importe quel serveur Adobe.
