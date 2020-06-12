---
description: Pour effectuer la mise à niveau vers les outils de données v6.4, procédez comme suit.
title: Mise à niveau 6.3 vers 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---


# Upgrading 6.3 to 6.4{#upgrading-to}

Pour effectuer la mise à niveau vers les outils de données v6.4, procédez comme suit.

## Exigences de mise à niveau et recommandations {#section-8704a9ac358246cd81233dd0982d534f}

Suivez ces exigences et recommandations lors de la mise à niveau vers les outils de données version 6.4.

>[!IMPORTANT]
>
>Il est recommandé d’utiliser les fichiers de configuration par défaut nouvellement installés et de les personnaliser, plutôt que de déplacer des fichiers d’une installation précédente, à l’exception des suivants :

* **Ajouter** les processus ****** exclus pour la protection des points de terminaison *MS System Center sur les serveurs* Windows 2012 pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Cela permettra d&#39;autoriser les droits pour ces exécutables interfacés.

* **Mettez à jour le certificat *Trust_ca_cert.pem*sur les serveurs**.
* **Réorganisation des Profils** d’attribution.

   * Le dossier *Attribution* a été renommé ***Attribution - Premium*** (situé dans l’installation par défaut de *Profils*\*Attribution - Premium*).

   * Le profil *Premium* a été supprimé et l’espace de travail déplacé vers le nouveau dossier ***Attribution - Premium*** .

* **Mettez à jour les paramètres **Attribution-Premium**. Si vous avez des profils personnalisés avec des paramètres qui remplacent le profil *Adobe SC* par défaut, vous devez mettre à jour les champs personnalisés dans ces fichiers de configuration :

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Grâce à cette réorganisation, vous souhaitez supprimer les anciens dossiers *Attribution* et *Premium* de votre installation serveur.

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

   à ces paramètres :

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

* **Définissez les autorisations** de Report Server pour générer des rapports Microsoft Excel sur des serveurs Windows 2012.

   1. Définissez l’autorisation du dossier racine (**[ !DNL E:\ReportServer\]**) sur *Tout le monde = contrôle* complet.

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

   1. Affectez &quot;SYSTEM&quot; en tant que propriétaire pour ces dossiers.

* **Ajoutez les polices sur le serveur de rapports.** Dans le **[!DNL ReportServer.cfg]**fichier, ajoutez les polices suivantes (pour toutes les langues) :

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Mettez à jour votre version de Microsoft Excel ** (si nécessaire).

   Avec la version 6.4 des Outils de données, la prise en charge d’Excel 2007 a été interrompue. En outre, puisque les outils de données s’exécutent uniquement sur Microsoft Windows pour une architecture 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Architecture** 64 bits requise pour l’installation de la station de travail (client).
* **Exécutez l&#39;Assistant** Installation de la station de travail.

   Installez la nouvelle version de la station de travail (client) en téléchargeant et en lançant ***InsightSetup.exe*** et en suivant les instructions de configuration. L&#39;assistant de configuration installe vos fichiers à un nouvel emplacement par défaut :

   Les fichiers de Programme sont désormais enregistrés par défaut sur :

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Les fichiers de données (profils, certificats, journaux de suivi et fichiers utilisateur) sont maintenant enregistrés par défaut sur :

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Ajoutez les polices sur la station de travail**.

   Dans le **[!DNL Insight.cfg]** fichier, ajoutez les polices suivantes (pour toutes les langues) :

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

