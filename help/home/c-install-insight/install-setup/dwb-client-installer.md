---
description: Les outils de données fournissent un assistant de configuration pour installer l’application de station de travail (client).
title: Assistant Installation de station de travail
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Assistant Installation de station de travail{#workstation-setup-wizard}

Les outils de données fournissent un assistant de configuration pour installer l’application de station de travail (client).

## Installation de Workstation à l&#39;aide de l&#39;Assistant Installation {#section-58da9bb6196c46eab3b54146913fdcb8}

Lancez le fichier exécutable de l&#39;assistant d&#39;installation et passez en revue chaque étape pour installer le programme client de la station de travail. Après l&#39;installation de la station de travail, vous pouvez vous connecter aux serveurs et aux profils.

1. Cliquez deux fois sur le fichier exécutable du programme d&#39;installation de la station de travail.
1. Cliquez sur **Oui** pour autoriser l’installation du programme sous Windows.
1. Sélectionnez une **langue** pour l’assistant de configuration.

   L’assistant s’ouvre :

   ![](assets/6_4_workstation_wizard.png)

1. Cliquez sur **Suivant** dans la boîte de dialogue **Bienvenue dans l’Assistant** de configuration des outils de données.

1. Choisissez d’installer une **nouvelle installation** ou de **mettre à niveau ou de réparer** une installation existante.

   **La nouvelle installation** remplace tous les fichiers précédemment installés.

   **La mise à niveau** met à jour votre station de travail vers la dernière version ou vous permet de réparer une installation existante. Les outils de données compareront les fichiers **Insight.exe** installés et exécuteront l’Assistant Installation de Workstation si une version plus récente du client est disponible.

1. Sélectionnez l’emplacement d’installation :

   **Installation standard** vers un dossier et un emplacement par défaut.

   * Les fichiers du programme sont enregistrés par défaut sur :

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Les fichiers de données (profils, certificats, journaux de trace et fichiers utilisateur) sont enregistrés par défaut dans :

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Un fichier générique ***Insight.cfg*** sans détails de serveur sera initialement installé. Il est recommandé d’utiliser le fichier ***Insight.cfg*** récemment installé et de le personnaliser au lieu de déplacer un fichier d’une installation précédente. Comme le chemin d&#39;installation de la station de travail a changé, il est recommandé d&#39;ajouter des polices, de supprimer le dossier *des* utilisateurs et de supprimer le composant *TraceFileComponent *.

1. (Facultatif) Sélectionnez** Personnalisé** pour choisir le module linguistique et l&#39;emplacement du programme et des fichiers de données.
1. Sélectionnez l’emplacement des **raccourcis dans le menu** Démarrer.

   ![](assets/6_4_workstation_wizard_folder.png)

   Cliquez sur **Ne pas créer de dossier** de menu Démarrer pour ne pas installer de raccourci dans le menu Démarrer de Windows.

1. Cliquez sur **Suivant.** Un résumé des chemins d’accès et des langues sélectionnés s’affiche. Click **Install.**

1. Localisez le certificat **Outils de** données.

   Si l’assistant de configuration ne parvient pas à trouver le certificat Outils de données lors de l’installation, une boîte de dialogue s’ouvre pour accéder à l’emplacement du certificat (fichier **.pem** situé par défaut dans le dossier des **certificats** client), ou cliquez sur **Ignorer** pour rechercher le certificat après l’installation.

   Cliquez sur **Installer** après avoir localisé le certificat.

1. Une fois l’assistant de configuration terminé et les outils de données installés, cliquez sur **Terminer** pour terminer la configuration.

   >[!NOTE]
   >
   >Emplacement du journal par défaut de l&#39;Assistant Configuration de la station de travail à l&#39;adresse **[!DNL C:\Users\&#39;<userName>`\AppData\Local\Temp.]**

   Cochez la case **Lancer l’application** pour ouvrir le Workbench après l’installation.

1. **Configurez les connexions** aux serveurs dans **[!DNL Insight.cfg]** le fichier.

   Après l’installation de la station de travail, l’espace de travail Expérience de configuration améliorée de la station de travail s’ouvre avec des informations supplémentaires sur la [saisie des informations](/help/home/c-get-started/c-insght-config-param.md) de connexion au serveur dans le fichier *Insight.cfg* et une option permettant de sélectionner un profil dans la liste déroulante. Vous pouvez également afficher l’état de la connexion à vos serveurs.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Dossiers d’installation {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

La structure de dossiers Outils de données comporte deux emplacements d’installation :

* **Fichiers** du programme Le fichier **Insight.exe** et les fichiers client pris en charge (**Insight.ini**) se trouvent désormais par défaut à l’emplacement suivant :

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Dossier **Appdata** .

   **Insight.cfg**, les profils, les certificats, les journaux de trace et les fichiers utilisateur se trouvent désormais par défaut à l’emplacement suivant :

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Vous pouvez définir le chemin d’accès du dossier **Appdata** dans le `Insight.ini` fichier :

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Désinstallation de la station de travail {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Les outils de données incluent désormais un exécutable pour désinstaller le poste de travail (situé par défaut à **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Lancez et suivez les étapes pour supprimer les fichiers de station de travail Outils de données de votre disque dur.

>[!NOTE]
>
>Vous pouvez lancer l’exécutable **unins000.exe** à partir du dossier, à l’aide du raccourci **Désinstaller les outils** de données à partir du menu Démarrer ou de **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
