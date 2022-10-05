---
description: Procédez comme suit pour effectuer la mise à niveau vers Data Workbench v6.4.
title: Mise à niveau de 6.3 vers 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Mise à niveau de 6.3 vers 6.4{#upgrading-to}

{{eol}}

Procédez comme suit pour effectuer la mise à niveau vers Data Workbench v6.4.

## Configuration requise pour la mise à niveau et Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Suivez ces exigences et recommandations lors de la mise à niveau vers Data Workbench 6.4.

>[!IMPORTANT]
>
>Il est recommandé d’utiliser les fichiers de configuration par défaut nouvellement installés et de les personnaliser, plutôt que de déplacer des fichiers d’une installation précédente, à l’exception des suivants :

* **Ajouter** ***Processus exclus*** pour *Protection des points d’entrée MS System Center sur les serveurs Windows 2012* pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Cela permettra d’activer les droits de liste autorisée pour ces exécutables interfaces.

* **Mettez à jour le *Trust_ca_cert.pem* certificat sur les serveurs**.
* **Réorganisation des profils d’attribution**.

   * Le *Attribution* Le dossier a été renommé en ***Attribution - Premium*** (se trouve dans l’installation par défaut à l’adresse *Profils*\*Attribution - Premium*).

   * Le *Premium* le profil a été supprimé et l’espace de travail déplacé vers la nouvelle ***Attribution - Premium*** dossier.

* **Mettre à jour *Attribution-Premium* paramètres**. Si vous disposez de profils personnalisés avec des paramètres qui remplacent la valeur par défaut *Adobe SC* , puis vous devez mettre à jour les champs personnalisés dans ces fichiers de configuration :

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* En raison de cette réorganisation, vous souhaiterez supprimer l’ancien *Attribution* et *Premium* à partir de l’installation de votre serveur.

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

* **Mise à jour de fichiers Meta.cfg personnalisés** (si nécessaire).

   Le **[!DNL Meta.cfg]** fichiers dans **[!DNL Base\Context and AdobeSC\Context]** ont été mis à jour dans cette version.

   Si vous remplacez la variable **meta.cfg** lors de l’installation, votre copie de profil doit être mise à jour avec ces paramètres et la variable **vecteur de métadonnées** saisie de manière appropriée :

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

* **Définition des autorisations du serveur de rapports** pour générer des rapports Excel Microsoft sur des serveurs Windows 2012.

   1. Définissez l’autorisation du dossier racine (**[!DNL E:\ReportServer\]**) à *Tout le monde = contrôle total*.

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

   1. Attribuez &quot;SYSTEM&quot; comme propriétaire pour ces dossiers.

* **Ajoutez des polices au serveur de rapports.** Dans le **[!DNL ReportServer.cfg]**, ajoutez les polices suivantes (pour toutes les langues) :

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Mettez à jour votre version de Microsoft Excel ** (si nécessaire).

   Avec la version 6.4 de Data Workbench, la prise en charge d’Excel 2007 a été abandonnée. En outre, comme Data Workbench ne s’exécute que sur Microsoft Windows pour une architecture 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Architecture 64 bits** requis pour l’installation de Workstation (Client).
* **Exécution de l’assistant de configuration de la station de travail**.

   Installez la nouvelle version de la station de travail (client) en la téléchargeant et en la lançant. ***InsightSetup.exe*** et en suivant les instructions de configuration. L’assistant de configuration installe par défaut vos fichiers à un nouvel emplacement :

   Les fichiers de programme sont désormais enregistrés par défaut sur :

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Les fichiers de données (profils, certificats, journaux de suivi et fichiers utilisateur) sont désormais enregistrés par défaut sur :

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Ajout de polices à la station de travail**.

   Dans le **[!DNL Insight.cfg]** ajoutez les polices suivantes (pour toutes les langues) :

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
