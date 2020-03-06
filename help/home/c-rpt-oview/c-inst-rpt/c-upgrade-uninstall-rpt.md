---
description: Informations sur la mise à niveau et la désinstallation du logiciel Report Server.
solution: Analytics
title: Mise à niveau et désinstallation du serveur de rapports
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mise à niveau et désinstallation du serveur de rapports{#upgrading-and-uninstalling-report-server}

Informations sur la mise à niveau et la désinstallation du logiciel Report Server.

* [Rapport de mise à niveau](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Désinstallation du rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Mise à niveau du serveur de rapports {#section-95fea4bddad74616a8aea450dcdb2282}

Si vous effectuez une mise à niveau vers [!DNL Report Server] la version 5.4, vous pouvez utiliser les instructions pour mettre à niveau votre [!DNL Report Server] logiciel. Si vous utilisez la version [!DNL Report Server] 3.6 ou antérieure, contactez Adobe pour obtenir de l’aide sur votre mise à niveau.

Pour effectuer la mise à niveau [!DNL Report Server] 5.4, utilisez l’outil de données pour copier un fichier de mise à niveau vers le serveur de l’outil de données auquel [!DNL Report Server] se connecte. Après cela, [!DNL Report] les instances de serveur se mettent automatiquement à niveau lorsqu’elles se connectent à ce serveur et chargent un profil.

>[!NOTE]
>
>Avant de procéder à la mise à niveau [!DNL Report Server], assurez-vous d’avoir correctement mis à niveau votre logiciel de serveur de outils de données ainsi que les profils s’exécutant sur le serveur de outils de données. Pour plus d’informations, contactez les services de conseil Adobe.

Pour effectuer la procédure suivante, vous devez d’abord obtenir le fichier de mise à niveau pour [!DNL Report Server].

**Pour effectuer la mise à niveau vers la version[!DNL Report Server].4 et les versions ultérieures**

1. Effectuez une sauvegarde de tous les fichiers sous [!DNL E:\Portal] et supprimez tous les fichiers et dossiers de ce répertoire.
1. Copy the contents of the new build into [!DNL E:\Portal].
1. Modifiez [!DNL global.asa], [!DNL email.asp]et [!DNL TopNavigation.xml] selon les instructions de la section précédente.

1. Copiez le [!DNL users.mdb] contenu de votre sauvegarde.

   >[!NOTE]
   >
   >Si vous n’aviez pas encore généré de rapports avec une sortie .png, vous devez accéder aux dossiers individuels des rapports et modifier le rapport [!DNL reports.xml] pour inclure un format de rapport de png. Dans le cas contraire, vous pourriez obtenir une erreur 500. Votre original [!DNL reports.xml] ressemblerait à ce qui suit :

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   Il faudrait le modifier comme suit :

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. Dans le [!DNL report.cfg], incluez un format de sortie png et enregistrez. Il doit ensuite générer des rapports au format png.

**Pour effectuer la mise à niveau vers[!DNL Report Server]4.0**

1. Sur l’ordinateur des outils de données, copiez le fichier de mise à niveau du serveur de rapports dans le [!DNL Temp\Software] dossier du répertoire d’installation des outils de données.
1. Démarrez l’outil de données et chargez le [!DNL Configuration] profil.
1. Cliquez sur la **[!UICONTROL Configure Connection to Servers]** vignette.
1. Dans la [!DNL Servers Manager]section, cliquez avec le bouton droit sur l’icône du serveur de l’outil de données, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans le dossier Software, ouvrez le [!DNL Report Server] dossier.
1. Cliquez avec le bouton droit sur la **[!UICONTROL Temp]** coche [!DNL ReportServer.exe] , puis sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Désinstallation du serveur de rapports {#section-96eb3281c45a45c0a7065deaa6845c25}

**Pour désinstaller[!DNL Report Server]**

1. Annulez l’enregistrement du [!DNL Report Windows] service.

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé le serveur de l’outil de données (InsightServer64.exe). Exemple : [!DNL D:\Adobe\Report\bin]
   1. A l’invite de commande, exécutez la commande suivante pour l’arrêter et l’annuler en tant que service sous Microsoft Windows : [!DNL visualreport /unregserver]

1. Supprimez le répertoire d’installation du serveur de rapports.

