---
description: Informations sur la mise à niveau et la désinstallation de votre logiciel de serveur de rapports.
title: Mise à niveau et désinstallation du serveur de rapports
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Mise à niveau et désinstallation du serveur de rapports{#upgrading-and-uninstalling-report-server}

Informations sur la mise à niveau et la désinstallation de votre logiciel de serveur de rapports.

* [Rapport de mise à niveau](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Désinstallation du rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Mise à niveau du serveur de rapports {#section-95fea4bddad74616a8aea450dcdb2282}

Si vous effectuez une mise à niveau vers [!DNL Report Server] 5.4, vous pouvez suivre les instructions pour mettre à niveau votre logiciel [!DNL Report Server]. Si vous utilisez [!DNL Report Server] 3.6 ou version antérieure, contactez Adobe pour obtenir de l’aide sur votre mise à niveau.

Pour mettre à niveau [!DNL Report Server] 5.4, utilisez Data Workbench pour copier un fichier de mise à niveau vers le serveur Data Workbench auquel [!DNL Report Server] se connecte. Ensuite, les instances de serveur [!DNL Report] se mettent automatiquement à niveau lorsqu’elles se connectent à ce serveur et chargent un profil.

>[!NOTE]
>
>Avant de mettre à niveau [!DNL Report Server], vérifiez que vous avez correctement mis à niveau le logiciel de votre serveur Data Workbench ainsi que les profils s’exécutant sur le serveur Data Workbench. Pour plus d’informations, contactez les Services de conseil Adobe.

Pour effectuer la procédure suivante, vous devez d’abord obtenir le fichier de mise à niveau pour [!DNL Report Server].

**Pour effectuer la mise à niveau vers la version  [!DNL Report Server] 5.4 et les versions ultérieures**

1. Sauvegardez tous les fichiers sous [!DNL E:\Portal] et supprimez tous les fichiers et dossiers dans ce répertoire.
1. Copiez le contenu de la nouvelle version dans [!DNL E:\Portal].
1. Modifiez [!DNL global.asa], [!DNL email.asp] et [!DNL TopNavigation.xml] conformément aux instructions de la section précédente.

1. Copiez le [!DNL users.mdb] de votre sauvegarde.

   >[!NOTE]
   >
   >Si vous n’avez pas généré auparavant de rapports avec une sortie .png, vous devez accéder aux dossiers de rapports individuels et modifier la balise [!DNL reports.xml] afin d’inclure un format de rapport png. Sinon, vous risquez d’obtenir une erreur 500. Votre [!DNL reports.xml] original ressemblerait à ce qui suit :

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

   Il doit être modifié comme suit :

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

1. Dans la balise [!DNL report.cfg], incluez un format de sortie png et save. Dorénavant, il doit générer des rapports au format png.

**Pour effectuer la mise à niveau vers la version  [!DNL Report Server] 4.0**

1. Sur l’ordinateur Data Workbench, copiez le fichier de mise à niveau du serveur de rapports dans le dossier [!DNL Temp\Software] du répertoire d’installation de Data Workbench.
1. Démarrez Data Workbench et chargez le profil [!DNL Configuration].
1. Cliquez sur la miniature **[!UICONTROL Configure Connection to Servers]**.
1. Dans la balise [!DNL Servers Manager], cliquez avec le bouton droit sur l’icône du serveur Data Workbench et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le dossier Logiciel , ouvrez le dossier [!DNL Report Server] .
1. Cliquez avec le bouton droit de la souris sur la case **[!UICONTROL Temp]** correspondant à [!DNL ReportServer.exe] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Désinstallation du serveur de rapports {#section-96eb3281c45a45c0a7065deaa6845c25}

**Pour désinstaller[!DNL Report Server]**

1. Annulez l’enregistrement du service [!DNL Report Windows].

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé le serveur Data Workbench (InsightServer64.exe). Exemple : [!DNL D:\Adobe\Report\bin]
   1. A l’invite de commande, exécutez la commande suivante pour l’arrêter et l’annuler en tant que service sous Microsoft Windows : [!DNL visualreport /unregserver]

1. Supprimez le répertoire d’installation du serveur de rapports.
