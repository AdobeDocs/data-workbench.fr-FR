---
description: Nouvelles fonctionnalités, correctifs et problèmes connus dans les outils de données version 6.7.
title: Notes de mise à jour des outils de données version 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.7 Release Notes{#data-workbench-release-notes}

Nouvelles fonctionnalités, correctifs et problèmes connus dans les outils de données version 6.7.

## Data Workbench 6.7 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad}

Nouvelles fonctionnalités, correctifs et problèmes connus dans les outils de données version 6.7.

## Nouvelles fonctionnalités de la version 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Nouveau modèle d’authentification pour Data Workbench Workstation (intégration IMS)**

Data Workbench Workstation prend maintenant en charge l’authentification des utilisateurs par nom d’utilisateur et mot de passe. Grâce à cette nouvelle méthode, les administrateurs peuvent créer et gérer leurs propres comptes d’utilisateur, ce qui leur évite d’avoir à contacter l’assistance clientèle.

Pour en savoir plus, voir [Self-Provisioning of Users](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html) (Habilitation en libre-service des utilisateurs).

**Recherche de fichiers plats**

Data Workbench Workstation prend maintenant en charge l’authentification des utilisateurs par nom d’utilisateur et mot de passe. Grâce à cette nouvelle méthode, les administrateurs peuvent créer et gérer leurs propres comptes d’utilisateur, ce qui leur évite d’avoir à contacter l’assistance clientèle.

Auparavant, la recherche de fichiers plats chargeait le fichier complet dans les tampons en mémoire, ce qui encombrait l’utilisation de la mémoire et nuisait aux performances d’autres sous-systèmes. Les fichiers peuvent maintenant être mappés en mémoire et mis en cache dans Windows, ce qui permet d’optimiser l’utilisation de la mémoire en définissant le paramètre *Memory Mapped Lookup Files* sur true dans [!DNL MemorySettings.cfg].

Pour en savoir plus, voir [Self-Provisioning of Users](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html) (Habilitation en libre-service des utilisateurs).

**Utilisation de la mémoire**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. Pour en savoir plus, voir [Surveillance de l’utilisation de la mémoire](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html).

**Chiffrements de sécurité**

Ajout de la prise en charge d’ECDHE et de DHE.

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. Pour en savoir plus, voir [Administration utilisateur des membres de groupe](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html).

**Menu Aide**

Le menu d’aide présente maintenant un raccourci vers le répertoire Ouvrir les certificats.

**`TargetBulkUpload`exporter **

Les URL seront fournies à la fin du fichier de trace d’exportation et du fichier `targetbulkuploadexportname.log.completed` afin d’effectuer le suivi de l’enregistrement des lots bloqués.

Un nouveau fichier, [!DNL TargetBulkUpload.cfg], est fourni afin de configurer l’intervalle de temporisation maximal (en minutes). Le fichier se trouve dans [!DNL Server\Admin\Export\].

## Correctifs {#section-160baf6ea04c45a993777ee4260691ed}

* Correction d’un problème en raison duquel la dimension Clics publicitaires de campagne affichait des valeurs exagérées.
* Correction d’un problème lié à la génération de fichiers Excel à partir du serveur de rapports.
* Le chiffrement RC4 est désormais désactivé par défaut.
* Correction d’un problème en raison duquel le poste de travail Outils de données se bloquait lors de l’ajout d’un élément de dimension à un tableau de légende de valeur.
* Correction d’un problème lié aux exportations des outils de données vers AAM qui provoquait des dépassements de délai.
* Correction d’un problème en raison duquel le poste de travail Outils de données se bloquait lorsqu’un utilisateur sans niveau d’accès suffisant enregistrait l’espace de travail sur le serveur.
* Correction d’un problème en raison duquel le format de date [!DNL report.cfg] était incorrect ou non localisé.
* Correction d’un problème en raison duquel les lignes de produit et de mobile dans le flux AVRO affichaient des informations confuses.
* Correction d’un problème qui empêchait l’ordre des `*.1cd` fichiers et `*.1ad` des fichiers [!DNL order.txt].

* L’option Envoyer au serveur a été désactivée pour l’algorithme Optimisation de l’attente lors de l’exécution de la mise en grappe.
* Correction d’un problème en raison duquel le `TargetBulkUpload` fichier exécutable se bloquait et ne fonctionnait pas complètement.

## Problèmes connus {#section-d76322bdac5043f087ab303dc68b8fff}

* Lors de la déconnexion, le [!DNL user cache.db] fichier est nettoyé.
* Les adresses électroniques utilisateur IMS contenant des caractères &quot;+&quot; ou &quot;%&quot; ne sont pas prises en charge.
* L’utilisateur ne peut pas se déconnecter en cas d’erreur dans l’état de la connexion. Pour pallier ce problème, déconnectez-vous en mode hors ligne.
* La fenêtre de connexion IMS ne s’affiche pas correctement sur certains matériels avec une résolution élevée et une résolution élevée. Pour pallier ce problème, cliquez avec le bouton droit de la souris sur [!DNL Insight.exe] et accédez à **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, puis cochez la case **[!UICONTROL Override high DPI scaling behavior]**.

## Conditions requises pour la mise à niveau {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Mise à jour [!DNL trust_ca_cert.pem] sur les serveurs Insight qui fait partie du pack de création.
1. Mettez à jour le certificat du serveur de rapports et du serveur de rapports en téléchargeant de nouveaux certificats à partir de [https://aap.adobe.com](https://aap.adobe.com).
1. Pour mettre automatiquement à jour Workstation et Report Server, effectuez une mise à jour manuelle [!DNL trust_ca_cert.pem] des deux en les téléchargeant depuis le serveur de licences.
1. La fonctionnalité de mise à jour automatique de Sensor nécessite la version 5.0 pour communiquer avec Insight Server version 6.70. En outre, les rapports de Sensor [!DNL trust_ca_cert.pem] doivent être mis à jour manuellement en les téléchargeant depuis le serveur de licences.

## Mises à jour système {#section-c1b4949ea734440aa62658ac313261db}

Les nouveaux fichiers incluent :

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Les fichiers mis à jour sont les suivants :

1. [!DNL trust_ca_cert.pem] pour tous les composants.
1. [!DNL Access Control.cfg] pour prendre en charge la configuration IMS.
1. [!DNL Base\Context\meta.cfg] pour la prise en charge des formats Date de début et Date de fin dans [!DNL Report.cfg]

1. Ajouts à [!DNL Insight.cfg] la prise en charge du proxy pour l’authentification IMS :

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Voir les notes [de mise à jour](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) archivées pour Outils de données 5.3 à 5.52.
