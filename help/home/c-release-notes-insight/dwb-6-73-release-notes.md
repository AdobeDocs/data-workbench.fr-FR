---
description: Nouvelles fonctionnalités et correctifs de Data Workbench 6.73.
title: Notes de mise à jour Data Workbench 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 26%

---

# Notes de mise à jour Data Workbench 6.73{#data-workbench-release-notes}

Nouvelles fonctionnalités et correctifs de Data Workbench 6.73.

## Correctifs {#section-160baf6ea04c45a993777ee4260691ed}

* Correction d’un problème dans Workstation en raison duquel certains utilisateurs ne parvenaient pas à se connecter sur du matériel à haute résolution.
* Correction d’un problème dans le serveur en raison duquel le message électronique manquait dans les noms de fichier d’archive lors de l’utilisation de la connexion IMS.
* Mise à jour d’OpenSSL vers la version 1.1.0h qui inclut plusieurs correctifs de vulnérabilités et de nouveaux chiffrements SSL.
* Mise à jour des bibliothèques open source répertoriées ci-dessous vers les dernières versions stables

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Ajout de la journalisation des erreurs lorsque le nombre de lignes du fichier de recherche est supérieur aux 357913908 lignes prises en charge.

## Problème connu {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation version 6.73 ne se connecte pas aux serveurs Data Workbench versions 6.61 et antérieures. La raison en est que les anciennes versions du serveur utilisent une forme de chiffrement faible qui n’est pas prise en charge dans la version 6.73. Pour activer la prise en charge des anciennes versions,

   1. Remplacez la liste des filtres SSL par défaut sur le serveur par une liste de chiffrement forte prise en charge par OpenSSL version 1.0.1h. Pour le remplacer, ajoutez la clé &quot;SSL Ciphers&quot; dans les fichiers &quot;Communications.cfg&quot; disponibles dans les répertoires &quot;Composants&quot; et &quot;Composants pour les serveurs de traitement&quot;. Par exemple : `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Assurez-vous que la clé est placée au même niveau que le port SSL. Pour plus d’informations, voir [Paramètres de configuration des communications](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Placez le dernier fichier trust_ca_cert.pem sur le serveur 6.61 et les serveurs plus anciens. Ce paramètre s’applique à toutes les versions de Workstation 6.7x.

Voir [notes de mise à jour archivées](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) pour Data Workbench 5.3 à 5.52.
