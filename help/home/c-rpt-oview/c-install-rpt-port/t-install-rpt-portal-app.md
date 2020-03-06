---
description: Le portail de rapports est constitué d’un ensemble de pages de serveur d’applications (ASP) et de fichiers de prise en charge.
solution: Analytics
title: Installation des fichiers d’application du portail de rapports
topic: Data workbench
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installation des fichiers d’application du portail de rapports{#install-the-report-portal-application-files}

Le portail de rapports est constitué d’un ensemble de pages de serveur d’applications (ASP) et de fichiers de prise en charge.

Pour installer le [!DNL Report Portal], vous devez extraire ces fichiers du fichier de distribution que vous avez reçu d’Adobe et les installer sur l’ordinateur sur lequel Microsoft IIS est en cours d’exécution.

**Installation des fichiers[!DNL Report Portal]d’application**

1. Si vous ne l’avez pas déjà fait, téléchargez le package d’installation (fichier .zip) pour le [!DNL Report Portal] site FTP d’Adobe.
1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, extrayez les fichiers du package d’installation vers n’importe quel emplacement. Cette étape installe les sous-dossiers et fichiers suivants dans le dossier VSVirtualPortalName.

   | Dossier ou fichier | Description |
   |---|---|
   | [!DNL \data\users.mdb] | Base de données contenant la liste des [!DNL Report Portal] utilisateurs autorisés. |
   | [!DNL \PortalASP\] | Dossier contenant les fichiers ASP qui composent [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Dossier contenant cinq sous-dossiers (Core, CSS, HTC, Images et Output) contenant les fichiers de prise en charge utilisés par [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Fichier de configuration que vous utilisez pour définir les répertoires virtuels associés à [!DNL Report Portal] (utilisé avec IIS 6.0 uniquement). |

   Le répertoire ressemble à l’exemple suivant :

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Le nom du répertoire peut différer du nom indiqué dans l’exemple.

1. Renommez le dossier VSVirtualPortalName (ou un autre nom) en ce que vous souhaitez utiliser comme répertoire virtuel racine de votre [!DNL Report Portal] (ci-après appelé *PortalName*). Pour plus d’informations sur les répertoires virtuels, voir la section suivante.