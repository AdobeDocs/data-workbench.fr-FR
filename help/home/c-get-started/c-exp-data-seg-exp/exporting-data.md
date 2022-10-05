---
description: Vous pouvez désormais utiliser les protocoles CSV, TSV, Exportation de segments et Exportation de segments avec en-tête à l’aide des protocoles FTP et SFTP pour exporter des fichiers de segments du client (poste de travail) vers le serveur.
title: Exportation d’un segment à l’aide de la diffusion S/FTP
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
exl-id: 0f1dc0a1-f376-47fb-887c-612a654ed0f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 4%

---

# Exportation d’un segment à l’aide de la diffusion S/FTP{#export-a-segment-using-s-ftp-delivery}

{{eol}}

Vous pouvez désormais utiliser les protocoles CSV, TSV, Exportation de segments et Exportation de segments avec en-tête à l’aide des protocoles FTP et SFTP pour exporter des fichiers de segments du client (poste de travail) vers le serveur.

**Configuration des fichiers de configuration de l’exportation S/FTP**

Pour définir la configuration de l’exportation, deux nouveaux fichiers de configuration d’exportation ont été ajoutés pour configurer une connexion FTP ou SFTP, ce qui permet de sélectionner les détails du serveur dans la variable *FTPServerInfo.cfg* et les informations d’identification sont sélectionnées à partir de *FTPUserCredentials* dossier (correspondant au nom du serveur indiqué dans les arguments de commande).

* Définissez la variable **FTPServerInfo.cfg** fichier .

   Renseignez les informations du serveur FTP et définissez les reprises de connexion autorisées depuis le poste de travail. Modifier à partir du poste de travail ou du serveur à l’adresse  [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]**fichier .

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* Définissez la variable **FTPUserCredentials.cfg** fichier .

   Saisie des informations d’identification de l’utilisateur pour la connexion aux serveurs à l’aide de  [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]**fichier . Ce fichier contient les informations d’identification de l’utilisateur nécessaires pour se connecter aux serveurs et ne peut être modifié qu’à partir du serveur et non à partir du poste de travail (client).

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >Assurez-vous que les clés SSH que vous générez pour l’authentification sont au format identique à celles générées lorsque vous utilisez la commande SSH Keygen .
   >
   >Exemple de génération de clés SSH à l’aide de keygen :
   >
   >
   ```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Il existe six paramètres dans la variable **FTPUserCredentials.cfg** fichier requis pour divers transferts FTP ou SFTP.

   1. *Nom d’utilisateur*
   1. *Mot de passe utilisateur*
   1. *Nom du serveur*
   1. *Chemin de la clé publique*
   1. *Chemin de la clé privée*
   1. *Passphrase*

   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protocol </th> 
      <th colname="col2" class="entry"> Paramètres </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>Définissez les paramètres 1, 2 et 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP à l’aide de l’authentification par mot de passe </p> </td> 
      <td colname="col2"> <p>Définissez les paramètres 1, 2 et 3 lorsque le transfert utilise l’authentification par mot de passe (-p dans les arguments de commande). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP à l’aide de l’authentification par clé </p> </td> 
      <td colname="col2"> <p>Définissez les paramètres 1, 2, 3, 4, 5, 6 lorsque le transfert utilise l’authentification par clé (-k dans les arguments de commande). </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Définition des commandes d’exportation FTP et SFTP**

1. Ouvrez une table d&#39;export.

   Dans la station de travail, cliquez avec le bouton droit de la souris sur une *Tableau des détails* et sélectionnez l’un des types d’exportation : CSV , TSV, Exportation de segments ou Exportation de segments avec en-tête . Ou ouvrez le [!DNL .export] à partir d’une invite de commande et de modification (voir [Configuration de segments à exporter](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. Dans le *Commande* , définissez-le pour pointer vers le fichier exécutable de l’exportation :

   ```
   ExportIntegration.exe
   ```

1. Définissez la variable *Arguments de commande* comme illustré ci-dessous pour le protocole et l’authentification requis :

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (en cas d’utilisation d’un mot de passe pour l’authentification)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** (en cas d’utilisation de clés pour l’authentification)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

Tous les arguments de commande sont obligatoires et doivent être renseignés comme indiqué.

## Exportation S/FTP à l’aide de clés privées/publiques {#section-0534424d79a54a47b82594cfa7b3c17f}

Pour mettre en oeuvre l’exportation FTP et SFTP à l’aide de clés privées et publiques, placez les fichiers de configuration dans les dossiers suivants :

* Placer **FTPServerInfo.cfg** dans le [!DNL Server/Addresses/Export/] dossier.
* Placer **FTPUserCredentials.cfg** dans le [!DNL Server/Admin/Export/] dossier.

Six paramètres sont inclus dans la variable **FTPServerInfo.cfg** fichier :

1. *Nom d’utilisateur*
1. *Mot de passe utilisateur*
1. *Nom du serveur*
1. *Chemin de la clé publique*
1. *Chemin d’accès à la clé privée —* Placez le chemin d’accès à la clé privée dans le fichier de configuration sans l’extension, par exemple :

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Passphrase*

FTP utilise les paramètres 1, 2 et 3.

SFTP utilise les paramètres 1, 2 et 3 lorsque le transfert utilise l’authentification par mot de passe.

Le protocole SFTP utilise les six paramètres lorsque le transfert est effectué à l’aide de l’authentification par clé. Par exemple, si vous utilisez des clés pour l’authentification :

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

Les fichiers de configuration doivent se trouver au bon emplacement.

>[!NOTE]
>
>Les clés publiques doivent pointer vers un **.pem** et non vers un emplacement de dossier. Vous pouvez créer des clés à l’aide d’une fonction de génération de clé SSH à partir d’applications telles que Cygwin. (Putty génère des clés au format .ppk non pris en charge.)
