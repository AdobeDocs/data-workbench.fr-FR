---
description: Data Workbench fournit un assistant de configuration pour installer l’application de poste de travail (client).
title: Assistant de configuration de la station de travail
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
exl-id: bfd9f2ad-282a-4be8-9f66-53e045648ef1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---

# Assistant de configuration de la station de travail{#workstation-setup-wizard}

{{eol}}

Data Workbench fournit un assistant de configuration pour installer l’application de poste de travail (client).

## Installation de la station de travail à l’aide de l’assistant de configuration {#section-58da9bb6196c46eab3b54146913fdcb8}

Lancez l’exécutable de l’assistant d’installation et parcourez chaque étape pour installer le programme client de poste de travail. Une fois le poste de travail installé, vous pouvez vous connecter aux serveurs et aux profils.

1. Double-cliquez sur le fichier exécutable du programme d’installation de la station de travail.
1. Cliquez sur **Oui** pour permettre l’installation du programme sous Windows.
1. Sélectionnez une **Langue** pour l’assistant de configuration.

   L’assistant s’ouvre :

   ![](assets/6_4_workstation_wizard.png)

1. Cliquez sur **Suivant** sur le **Bienvenue dans l’assistant de configuration du Data Workbench** boîte de dialogue.

1. Sélectionnez cette option pour installer un **Nouvelle installation** ou **Mise à niveau ou réparation** une installation existante.

   **Nouvelle installation** remplace tous les fichiers précédemment installés.

   **Mettre à niveau** met à jour votre station de travail vers la dernière version ou vous permet de réparer une installation existante. Data Workbench compare installé **Insight.exe** et exécutez l’assistant de configuration de la station de travail si une version plus récente du client est disponible.

1. Sélectionnez l’emplacement d’installation :

   **Typique** s’installe dans un dossier et un emplacement par défaut.

   * Les fichiers de programme sont enregistrés par défaut sur :

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Les fichiers de données (profils, certificats, journaux de suivi et fichiers utilisateur) sont enregistrés par défaut sur :

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Un générique ***Insight.cfg*** Le fichier sans les détails du serveur sera initialement installé. Il est recommandé d’utiliser le ***Insight.cfg*** et personnalisez-le plutôt que de déplacer un fichier d’une installation précédente. Le chemin d’installation du poste de travail ayant changé, l’ajout de polices et la suppression de la fonction *Dossier utilisateur* et la suppression de *TraceFileComponent * est recommandée.

1. (facultatif) Sélectionnez **Personnalisé** pour choisir le package de langue et l’emplacement du programme et des fichiers de données.
1. Sélectionner l’emplacement pour **raccourcis dans le menu Démarrer**.

   ![](assets/6_4_workstation_wizard_folder.png)

   Cliquez sur **Ne pas créer de dossier de menu Démarrer** pour ne pas installer de raccourci dans le menu Démarrer de Windows.

1. Cliquez sur **Suivant.** Un résumé des chemins et langues d’emplacement de fichier sélectionnés s’affiche. Cliquez sur **Installez.**

1. Recherchez la variable **Certificat Data Workbench**.

   Si l’assistant de configuration ne parvient pas à trouver le certificat du Data Workbench au cours de l’installation, il ouvre une boîte de dialogue pour accéder à l’emplacement du certificat (une **.pem** fichier situé par défaut dans le client **Certificats** ) ou cliquez sur **Ignorer** pour trouver le certificat après l’installation.

   Cliquez sur **Installer** après avoir localisé le certificat.

1. Une fois l’assistant de configuration terminé et le Data Workbench installé, cliquez sur **Terminer** pour terminer la configuration.

   >[!NOTE]
   >
   >L’emplacement du journal par défaut de l’assistant de configuration de la station de travail à l’adresse  `C:\Users\<userName>\AppData\Local\Temp`.

   Sélectionnez la **Application Launch** pour ouvrir Workbench après la configuration.

1. **Configuration des connexions** aux serveurs dans **[!DNL Insight.cfg]** fichier .

   Une fois la station de travail installée, l’espace de travail Expérience de configuration de la station de travail améliorée s’ouvre avec des informations supplémentaires sur [saisie des informations de connexion au serveur](/help/home/c-get-started/c-insght-config-param.md) dans le *Insight.cfg* et une option pour sélectionner un profil dans la liste déroulante. Vous pouvez également afficher l’état de la connexion à vos serveurs.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Dossiers d’installation {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

La structure de dossiers du Data Workbench comporte deux emplacements d’installation :

* **Fichiers de programme** Le **Insight.exe** et les fichiers client associés (**Insight.ini**) se trouvent désormais par défaut à l’adresse

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Le **Appdata** dossier.

   **Insight.cfg**, les profils, les certificats, les journaux de suivi et les fichiers utilisateur se trouvent désormais par défaut à l’adresse

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Vous pouvez définir le chemin d’accès de la variable **Appdata** dans le dossier `Insight.ini` fichier :

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Désinstallation de la station de travail {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbench inclut désormais un exécutable pour désinstaller le poste de travail (situé par défaut à l’emplacement suivant : **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Lancez et suivez les étapes pour supprimer les fichiers de la station de travail de Data Workbench de votre disque dur.

>[!NOTE]
>
>Vous pouvez lancer la **unins000.exe** exécutable à partir du dossier, à l’aide de la propriété **Désinstallation du Data Workbench** à partir du menu Démarrer ou de **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
