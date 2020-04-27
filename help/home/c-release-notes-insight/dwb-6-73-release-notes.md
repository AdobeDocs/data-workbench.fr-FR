---
description: Nouvelles fonctionnalités et correctifs des outils de données version 6.73.
title: Notes de mise à jour des outils de données version 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 9552a2f9fe4e450b1e212b38a09f77252a009419

---


# Data Workbench 6.73 Release Notes{#data-workbench-release-notes}

Nouvelles fonctionnalités et correctifs des outils de données version 6.73.

## Correctifs {#section-160baf6ea04c45a993777ee4260691ed}

* Correction d’un problème dans Workstation en raison duquel certains utilisateurs ne parvenaient pas à se connecter sur du matériel à haute résolution.
* Correction d’un problème sur le serveur en raison duquel le courrier électronique manquait dans les noms de fichier d’archive lors de l’utilisation de la connexion IMS.
* Mise à jour d’OpenSSL vers la version 1.1.0h qui inclut plusieurs correctifs de vulnérabilités et de nouveaux chiffrements SSL.
* Mise à jour des bibliothèques Open Source répertoriées ci-dessous vers les dernières versions stables

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Ajout de la journalisation des erreurs lorsque le nombre de lignes du fichier de recherche est supérieur aux 357913908 lignes prises en charge.

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* La version 6.73 de la station de travail des outils de données ne se connecte pas aux serveurs des outils de données versions 6.61 et ultérieures. La raison en est que les anciennes versions de serveur utilisent une forme de chiffrement faible qui n’est pas prise en charge dans la version 6.73. Pour activer la prise en charge des versions antérieures

   1. Remplacez le SSL Ciphers par défaut sur le serveur par un de chiffrement fort  pris en charge par OpenSSL version 1.0.1h. Pour remplacer, ajoutez la clé &quot;SSL Ciphers&quot; dans les fichiers &quot;Communications.cfg&quot; disponibles dans les répertoires &quot;Composants&quot; et &quot;Composants pour les serveurs de traitement&quot;. Par exemple : `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Assurez-vous que la clé est placée au même niveau que le port SSL. Pour plus d&#39;informations, reportez-vous aux Paramètres de configuration des [communications](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Placez le dernier fichier trust_ca_cert.pem sur les serveurs 6.61 et antérieurs. Ce paramètre s’applique à toutes les versions de Workstation 6.7x.

Voir les notes [de mise à jour](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) archivées pour Outils de données 5.3 à 5.52.
