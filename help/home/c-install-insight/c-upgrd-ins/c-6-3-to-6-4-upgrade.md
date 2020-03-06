---
description: Pour effectuer la mise à niveau vers les outils de données v6.4, procédez comme suit.
title: Mise à niveau 6.3 vers 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Upgrading 6.3 to 6.4{#upgrading-to}

Pour effectuer la mise à niveau vers les outils de données v6.4, procédez comme suit.

## Configuration requise et recommandations pour la mise à niveau {#section-8704a9ac358246cd81233dd0982d534f}

Suivez ces exigences et recommandations lors de la mise à niveau vers Outils de données 6.4.

>[!IMPORTANT]
>
>Il est recommandé d’utiliser les fichiers de configuration par défaut nouvellement installés et de les personnaliser, plutôt que de déplacer des fichiers d’une installation précédente, à l’exception des suivants :

* **Ajoutez** des processus ****** exclus pour la protection des points de fin System Center ** MS sur les serveurs Windows 2012 pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Cela permettra d&#39;accorder des droits de &quot;liste blanche&quot; pour ces exécutables interfacés.

* **Mettez à jour le certificat *Trust_ca_cert.pem*sur les serveurs**.
* **Réorganisation des profils** d’attribution.

   * Le dossier *Attribution* a été renommé ***Attribution - Premium*** (situé dans l’installation par défaut à *Profils*\*Attribution - Premium*).

   * Le profil *Premium* a été supprimé et l’espace de travail déplacé vers le nouveau dossier ***Attribution - Premium*** .

* **Mettez à jour les paramètres *Attribution-Premium***. Si vous disposez de profils personnalisés avec des paramètres qui remplacent le profil *Adobe SC* par défaut, vous devez mettre à jour les champs personnalisés dans les fichiers de configuration suivants :

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* En raison de cette réorganisation, vous souhaiterez supprimer les anciens dossiers *Attribution* et *Premium* de l’installation du serveur.

   **Modifier ces paramètres**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   aux paramètres suivants :

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **Mettez à jour les fichiers** Meta.cfg personnalisés (si nécessaire).

   Les **[!DNL Meta.cfg]** fichiers des **[!DNL Base\Context and AdobeSC\Context]** dossiers ont été mis à jour dans cette version.

   Si vous remplacez le fichier **meta.cfg** au cours de l’installation, votre copie de profil doit être mise à jour avec ces paramètres et le vecteur **de** métadonnées saisi de manière appropriée :

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **Définissez les autorisations** du serveur de rapports pour générer des rapports Microsoft Excel sur des serveurs Windows 2012.

   1. Définissez l’autorisation du dossier racine (**[!DNL E:\ReportServer\]**) sur *Tout le monde = contrôle* complet.

   1. Créez les dossiers suivants avec les autorisations appropriées :

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Si vous exécutez Report Server sous Windows Server 2012, Windows Server 2012 R2 doit être installé.

   1. Affectez &quot;SYSTEM&quot; comme propriétaire pour ces dossiers.

* **Ajoutez des polices au serveur de rapports.** Dans le fichier **[!DNL ReportServer.cfg]**, ajoutez les polices suivantes (pour toutes les langues) :

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Mettez à jour votre version de Microsoft Excel **(si nécessaire).

   Avec la version 6.4 des Outils de données, la prise en charge d’Excel 2007 a été interrompue. En outre, étant donné que les outils de données s’exécutent uniquement sur Microsoft Windows pour une architecture 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Architecture** 64 bits requise pour l’installation de Workstation (Client).
* **Exécutez l&#39;Assistant** de configuration de station de travail.

   Installez la nouvelle version de la station de travail (client) en téléchargeant et en lançant ***InsightSetup.exe*** et en suivant les instructions de configuration. L’assistant de configuration installe vos fichiers à un nouvel emplacement par défaut :

   Les fichiers du programme sont maintenant enregistrés par défaut sur :

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Les fichiers de données (profils, certificats, journaux de trace et fichiers utilisateur) sont désormais enregistrés par défaut dans :

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Ajoutez des polices au poste de travail**.

   Dans le **[!DNL Insight.cfg]** fichier, ajoutez les polices suivantes (pour toutes les langues) :

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

