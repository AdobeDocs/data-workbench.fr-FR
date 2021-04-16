---
description: Informations sur la mise à niveau et la désinstallation du logiciel Report Server.
title: Mise à niveau et désinstallation du serveur de rapports
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Mise à niveau et désinstallation du serveur de rapports{#upgrading-and-uninstalling-report-server}

Informations sur la mise à niveau et la désinstallation du logiciel Report Server.

* [Rapport de mise à niveau](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Désinstallation du rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Mise à niveau du serveur de rapports {#section-95fea4bddad74616a8aea450dcdb2282}

Si vous effectuez une mise à niveau vers [!DNL Report Server] 5.4, vous pouvez utiliser les instructions pour mettre à niveau votre logiciel [!DNL Report Server]. Si vous utilisez [!DNL Report Server] 3.6 ou une version antérieure, contactez l’Adobe pour obtenir de l’aide sur la mise à niveau.

Pour mettre à niveau [!DNL Report Server] 5.4, utilisez l&#39;outil de données pour copier un fichier de mise à niveau vers le serveur de l&#39;outil de données auquel [!DNL Report Server] se connecte. Après cela, les instances de serveur [!DNL Report] se mettent automatiquement à niveau lorsqu&#39;elles se connectent à ce serveur et chargent un profil.

>[!NOTE]
>
>Avant de mettre à niveau [!DNL Report Server], assurez-vous d’avoir correctement mis à niveau votre logiciel de serveur de l’outil de données ainsi que les profils exécutés sur le serveur de l’outil de données. Pour plus d&#39;informations, contactez les Services de conseil en Adobe.

Pour effectuer la procédure suivante, vous devez d&#39;abord obtenir le fichier de mise à niveau pour [!DNL Report Server].

**Pour effectuer la mise à niveau vers les versions  [!DNL Report Server] 5.4 et ultérieures**

1. Effectuez une sauvegarde de tous les fichiers sous [!DNL E:\Portal] et supprimez tous les fichiers et dossiers de ce répertoire.
1. Copiez le contenu de la nouvelle version dans [!DNL E:\Portal].
1. Modifiez [!DNL global.asa], [!DNL email.asp] et [!DNL TopNavigation.xml] conformément aux instructions de la section précédente.

1. Copiez le [!DNL users.mdb] de votre sauvegarde.

   >[!NOTE]
   >
   >Si vous n&#39;aviez pas encore généré de rapports avec une sortie .png, vous devez aller dans les dossiers de rapports individuels et modifier [!DNL reports.xml] pour inclure un format de rapport png. Sinon, vous risquez d’obtenir une erreur 500. Votre [!DNL reports.xml] original ressemblerait à ce qui suit :

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

   Il devrait être modifié comme suit :

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

1. Dans [!DNL report.cfg], incluez un format de sortie png et enregistrez. A l’avenir, il devrait générer des rapports au format png.

**Pour effectuer la mise à niveau vers  [!DNL Report Server] 4.0**

1. Sur l’ordinateur des outils de données, copiez le fichier de mise à niveau du serveur de rapports dans le dossier [!DNL Temp\Software] du répertoire d’installation des outils de données.
1. Début des outils de données et chargement du profil [!DNL Configuration].
1. Cliquez sur la miniature **[!UICONTROL Configure Connection to Servers]**.
1. Dans [!DNL Servers Manager], cliquez avec le bouton droit sur l&#39;icône du serveur de l&#39;outil de données et cliquez sur **[!UICONTROL Server Files]**.

1. Dans le dossier Software, ouvrez le dossier [!DNL Report Server].
1. Cliquez avec le bouton droit de la souris sur la coche **[!UICONTROL Temp]** pour [!DNL ReportServer.exe] et sélectionnez **[!UICONTROL Save to]** > *&lt; &lt;a4/&quot;*.**[!UICONTROL server name]**

## Désinstallation du serveur de rapports {#section-96eb3281c45a45c0a7065deaa6845c25}

**Pour désinstaller[!DNL Report Server]**

1. Annulez l&#39;enregistrement du service [!DNL Report Windows].

   1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé le serveur de l’outil de données (InsightServer64.exe). Exemple : [!DNL D:\Adobe\Report\bin]
   1. A l&#39;invite de commande, exécutez la commande suivante pour l&#39;arrêter et l&#39;annuler en tant que service sous Microsoft Windows : [!DNL visualreport /unregserver]

1. Supprimez le répertoire d’installation de Report Server.
