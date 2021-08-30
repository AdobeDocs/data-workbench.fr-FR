---
description: Nouvelles fonctionnalités, correctifs et problèmes connus dans Data Workbench 6.7.
title: Notes de mise à jour Data Workbench 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 34%

---

# Notes de mise à jour Data Workbench 6.7{#data-workbench-release-notes}

Nouvelles fonctionnalités, correctifs et problèmes connus dans Data Workbench 6.7.

## Notes de mise à jour Data Workbench 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Nouvelles fonctionnalités, correctifs et problèmes connus dans Data Workbench 6.7.

## Nouvelles fonctionnalités de la version 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Nouveau modèle d’authentification pour Data Workbench Workstation (intégration IMS)**

Data Workbench Workstation prend maintenant en charge l’authentification des utilisateurs par nom d’utilisateur et mot de passe. Grâce à cette nouvelle méthode, les administrateurs peuvent créer et gérer leurs propres comptes d’utilisateur, ce qui leur évite d’avoir à contacter l’assistance clientèle.

Pour en savoir plus, voir [Self-Provisioning of Users](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html) (Habilitation en libre-service des utilisateurs).

**Recherche de fichiers plats**

Data Workbench Workstation prend maintenant en charge l’authentification des utilisateurs par nom d’utilisateur et mot de passe. Grâce à cette nouvelle méthode, les administrateurs peuvent créer et gérer leurs propres comptes d’utilisateur, ce qui leur évite d’avoir à contacter l’assistance clientèle.

Auparavant, la recherche de fichiers plats chargeait le fichier complet dans les tampons en mémoire, ce qui encombrait l’utilisation de la mémoire et nuisait aux performances d’autres sous-systèmes. Les fichiers peuvent maintenant être mappés en mémoire et mis en cache dans Windows, ce qui permet d’optimiser l’utilisation de la mémoire en définissant le paramètre *Memory Mapped Lookup Files* sur true dans [!DNL MemorySettings.cfg].

Pour en savoir plus, voir [Self-Provisioning of Users](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html) (Habilitation en libre-service des utilisateurs).

**Utilisation de la mémoire**

L’utilisation de pages volumineuses peut désormais être désactivée en définissant *Utiliser les pages volumineuses* sur false dans [!DNL MemorySettings.cfg]. Pour en savoir plus, voir [Surveillance de l’utilisation de la mémoire](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html).

**Chiffrements de sécurité**

Ajout de la prise en charge d’ECDHE et de DHE.

Prise en charge de la messagerie électronique dans [!DNL User List.cfg]

Ajout de la prise en charge de l’attribut Email dans [!DNL User List.cfg]. Pour en savoir plus, voir [Administration utilisateur des membres de groupe](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html?lang=en).

**Menu Aide**

Le menu d’aide présente maintenant un raccourci vers le répertoire Ouvrir les certificats.

**`TargetBulkUpload`export**

Les URL seront fournies à la fin du fichier de trace d’exportation et du fichier `targetbulkuploadexportname.log.completed` afin d’effectuer le suivi de l’enregistrement des lots bloqués.

Un nouveau fichier, [!DNL TargetBulkUpload.cfg], est fourni afin de configurer l’intervalle de temporisation maximal (en minutes). Le fichier se trouve dans  [!DNL Server\Admin\Export\].

## Correctifs {#section-160baf6ea04c45a993777ee4260691ed}

* Correction d’un problème en raison duquel la dimension Clic publicitaire de campagne affichait des valeurs exagérées.
* Correction d’un problème lié à la génération de fichiers Excel à partir du serveur de rapports.
* Le chiffrement RC4 est désormais désactivé par défaut.
* Correction d’un problème en raison duquel le poste de travail du Data Workbench se bloquait lors de l’ajout d’un élément de dimension à un tableau de légende des valeurs.
* Correction d’un problème en raison duquel Data Workbench AAM des exportations provoquait des dépassements de délai.
* Correction d’un problème en raison duquel le poste de travail du Data Workbench se bloquait lorsqu’un utilisateur sans niveau d’accès suffisant enregistrait l’espace de travail sur le serveur.
* Correction d’un problème en raison duquel le format de date dans [!DNL report.cfg] était incorrect ou non localisé.
* Correction d’un problème en raison duquel les lignes mobiles et de produits du flux AVRO affichaient des informations confuses.
* Correction d’un problème qui empêchait l’ordre des fichiers `*.1cd` et `*.1ad` dans [!DNL order.txt].

* L’option Envoyer au serveur a été désactivée pour l’algorithme Maximisation de l’attente lors de l’exécution de la mise en grappe.
* Correction d’un problème lié au blocage de l’exécutable `TargetBulkUpload` et à l’échec de l’exécution complète.

## Problèmes connus {#section-d76322bdac5043f087ab303dc68b8fff}

* Lors de la déconnexion, le fichier [!DNL user cache.db] est nettoyé.
* Les adresses électroniques des utilisateurs IMS contenant des caractères &quot;+&quot; ou &quot;%&quot; ne sont pas prises en charge.
* L’utilisateur ne parvient pas à se déconnecter en cas d’erreur d’état de connexion. Pour pallier ce problème, déconnectez-vous en mode hors ligne.
* La fenêtre de connexion IMS ne s’affiche pas correctement sur certains périphériques dotés d’une résolution élevée et d’une résolution élevée en ppp. Pour pallier ce problème, cliquez avec le bouton droit de la souris sur [!DNL Insight.exe] et accédez à **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, puis cochez la case **[!UICONTROL Override high DPI scaling behavior]**.

## Conditions requises pour la mise à niveau {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Mettez à jour [!DNL trust_ca_cert.pem] sur les serveurs Insight qui font partie du module de génération.
1. Mettez à jour le certificat du serveur et du serveur de rapports en téléchargeant les nouveaux certificats à partir de [https://aap.adobe.com](https://aap.adobe.com).
1. Pour mettre automatiquement à jour Workstation et Report Server, mettez à jour manuellement [!DNL trust_ca_cert.pem] pour les deux en les téléchargeant à partir du serveur de licences.
1. La fonction de mise à jour automatique de Capteur requiert la version 5.0 pour communiquer avec le serveur Insight version 6.70. De plus, la [!DNL trust_ca_cert.pem] du Capteur doit être mise à jour manuellement en la téléchargeant à partir du serveur de licences.

## Mises à jour système {#section-c1b4949ea734440aa62658ac313261db}

Les nouveaux fichiers incluent :

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Les fichiers mis à jour incluent :

1. [!DNL trust_ca_cert.pem] pour tous les composants.
1. [!DNL Access Control.cfg] pour prendre en charge la configuration IMS.
1. [!DNL Base\Context\meta.cfg] pour la prise en charge des formats Date de début et Date de fin dans  [!DNL Report.cfg]

1. Ajouts à [!DNL Insight.cfg] pour prendre en charge le proxy de l’authentification IMS :

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Voir [notes de mise à jour archivées](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) pour Data Workbench 5.3 à 5.52.
