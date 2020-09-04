---
description: Data Workbench fournit un assistant de configuration pour installer l'application de station de travail (client).
title: Assistant de configuration de la station de travail
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---


# Assistant de configuration de la station de travail{#workstation-setup-wizard}

Data Workbench fournit un assistant de configuration pour installer l&#39;application de station de travail (client).

## Installation de la station de travail à l&#39;aide de l&#39;Assistant Installation {#section-58da9bb6196c46eab3b54146913fdcb8}

Lancez l&#39;exécutable de l&#39;assistant d&#39;installation et passez en revue chaque étape pour installer le programme client de la station de travail. Après l&#39;installation de la station de travail, vous pouvez vous connecter aux serveurs et aux profils.

1. Doublon-cliquez sur l&#39;exécutable du programme d&#39;installation de la station de travail.
1. Cliquez sur **Oui** pour autoriser l’installation du programme sous Windows.
1. Sélectionnez une **langue** pour l’assistant de configuration.

   L&#39;Assistant s&#39;ouvre :

   ![](assets/6_4_workstation_wizard.png)

1. Cliquez sur **Suivant** dans la boîte de dialogue Assistant **d&#39;installation de l&#39;** Data Workbench.

1. Choisissez d&#39;installer une **nouvelle installation** ou de **mettre à niveau ou de réparer** une installation existante.

   **La nouvelle installation** remplace tous les fichiers précédemment installés.

   **Mettez à niveau** votre station de travail vers la dernière version ou vous permet de réparer une installation existante. Le Data Workbench compare les fichiers **Insight.exe** installés et exécute l&#39;Assistant Installation de la station de travail si une version plus récente du client est disponible.

1. Sélectionnez l’emplacement d’installation :

   **Installation type** sur un dossier et un emplacement par défaut.

   * Les fichiers programmes sont enregistrés par défaut sur :

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Les fichiers de données (profils, certificats, journaux de suivi et fichiers utilisateur) sont enregistrés par défaut sur :

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Un fichier ***Insight.cfg*** générique sans détails de serveur sera initialement installé. Il est recommandé d’utiliser le nouveau fichier ***Insight.cfg*** et de le personnaliser plutôt que de déplacer un fichier d’une installation précédente. Comme le chemin d&#39;installation de la station de travail a changé, il est recommandé d&#39;ajouter des polices, de supprimer le dossier ** utilisateur et de supprimer le composant *TraceFileComponent *.

1. (Facultatif) Sélectionnez **Personnalisé** pour choisir le module linguistique et l’emplacement du programme et des fichiers de données.
1. Sélectionnez l&#39;emplacement des **raccourcis dans le menu** Début.

   ![](assets/6_4_workstation_wizard_folder.png)

   Cliquez sur **Ne pas créer de dossier** de menu Début pour ne pas installer de raccourci dans le menu Début Windows.

1. Cliquez sur **Suivant.** Un résumé des chemins et langues d&#39;emplacement de fichier sélectionnés s&#39;affiche. Click **Install.**

1. Recherchez le certificat **du** Data Workbench.

   Si l&#39;Assistant Installation ne parvient pas à trouver le certificat du Data Workbench pendant l&#39;installation, une boîte de dialogue s&#39;ouvre pour accéder à l&#39;emplacement du certificat (un fichier **.pem** situé par défaut dans le dossier **Certificats** client), ou cliquez sur **Ignorer** pour rechercher le certificat après l&#39;installation.

   Cliquez sur **Installer** après avoir localisé le certificat.

1. Une fois l&#39;Assistant Installation terminé et le Data Workbench installé, cliquez sur **Terminer** pour terminer la configuration.

   >[!NOTE]
   >
   >Emplacement du journal par défaut de l&#39;Assistant Configuration de la station de travail à `C:\Users\<userName>\AppData\Local\Temp`.

   Cochez la case **Lancer l’application** pour ouvrir le Workbench après l’installation.

1. **Configurez les connexions** aux serveurs dans **[!DNL Insight.cfg]** le fichier.

   Après l’installation de la station de travail, l’espace de travail Expérience de configuration améliorée de la station de travail s’ouvre avec des informations supplémentaires sur la [saisie des informations](/help/home/c-get-started/c-insght-config-param.md) de connexion au serveur dans le fichier *Insight.cfg* et une option permettant de sélectionner un profil dans la liste déroulante. Vous pouvez également vue l’état de la connexion à vos serveurs.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Dossiers d&#39;installation {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

La structure de dossiers du Data Workbench comporte deux emplacements d’installation :

* **Fichiers** de programme Le fichier **Insight.exe** et les fichiers client pris en charge (**Insight.ini**) se trouvent désormais par défaut à l’emplacement suivant :

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Dossier **Appdata** .

   **Insight.cfg**, les profils, les certificats, les journaux de suivi et les fichiers utilisateur se trouvent désormais par défaut à l’emplacement suivant :

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

Le Data Workbench inclut désormais un exécutable pour désinstaller la station de travail (située par défaut à **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Lancez et suivez les étapes pour supprimer les fichiers de station de travail Data Workbench de votre disque dur.

>[!NOTE]
>
>Vous pouvez lancer l&#39;exécutable **unins000.exe** à partir du dossier, à l&#39;aide du raccourci Data Workbench **de** désinstallation du menu Début ou de **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
