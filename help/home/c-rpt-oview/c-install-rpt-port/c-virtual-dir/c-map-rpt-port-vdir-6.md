---
description: Procédure de mappage du portail de rapports à un répertoire virtuel (IIS 6.0).
title: Mappage du portail de rapports à un répertoire virtuel (IIS 6.0)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# Mappage du portail de rapports à un répertoire virtuel (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

Procédure de mappage du portail de rapports à un répertoire virtuel (IIS 6.0).

Le mappage de [!DNL Report Portal] à un répertoire virtuel sur IIS 6.0 implique trois tâches distinctes :

1. [Modification du fichier de configuration](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importer le fichier de configuration dans IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Activation des pages de serveur Principal (ASP) sur IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Vous devez effectuer les trois tâches.

## Modification du fichier de configuration {#section-eaf1c58935074cfa840dac33e1286520}

1. Sur l’ordinateur sur lequel [!DNL Report Portal] est installé, ouvrez \*PortalName*\ReportPortalSetup.xml dans un éditeur de texte tel que Notepad.

1. Utilisez la fonction de recherche et de remplacement de l’éditeur pour remplacer globalement (Remplacer tout) la chaîne &quot;VSVirtualPortalName&quot; par le nom de votre portail. Par exemple, si vous souhaitez utiliser &quot;VisualReportPortal&quot; comme nom de votre [!DNL Report Portal], recherchez &quot;VSVirtualPortalName&quot; et remplacez-le par &quot;VisualReportPortal&quot;.
1. Recherchez l’élément suivant dans ce fichier :

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Définissez l’attribut [!DNL Path] de cet élément sur l’emplacement physique du répertoire dans lequel [!DNL Report Server] enregistre la sortie pour vos jeux de rapports.

   Le dossier de sortie peut être situé n’importe où, peut être nommé n’importe quel et contient un sous-dossier pour chaque jeu de rapports.

   >[!NOTE]
   >
   >Il doit s’agir du même répertoire que celui que vous spécifiez dans le paramètre Racine de sortie du fichier [!DNL Report.cfg] pour un jeu de rapports. Pour plus d’informations, voir [Configuration des fichiers Report.cfg](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   L’exemple de code suivant montre comment définir l’attribut [!DNL Path] si vos rapports étaient enregistrés dans [!DNL E:\VSReport\ReportOutput] :

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >Il est essentiel que l’attribut [!DNL Path] soit correctement défini.

1. Si vous avez modifié la valeur par défaut [!DNL Path] de l’élément [!DNL Output], déplacez le fichier [!DNL profiles.xml] de *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. Dans l’exemple ci-dessus, déplacez [!DNL profiles.xml] vers [!DNL E:\VSReport\ReportOutput].

1. Vérifiez que les attributs [!DNL Path] de tous les autres éléments [!DNL IIsWebVirtualDir] sont mappés à l’emplacement correct en recherchant toutes les instances de [!DNL C:\Inetpub\wwwroot] et en les remplaçant par le chemin correct.

1. Enregistrez le fichier. Si vous souhaitez conserver le fichier d’origine, vous pouvez enregistrer le fichier de configuration sous un nouveau nom.

## Importation du fichier de configuration dans IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. Sur la machine sur laquelle [!DNL Report Portal] est installé, démarrez le Gestionnaire IIS à l’aide de **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Sélectionnez **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Default Web Site]** et sélectionnez **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (dans le fichier).

1. Sélectionnez le fichier **[!UICONTROL ReportPortalSetup.xml]** et cliquez sur **[!UICONTROL Read File]**.

1. Vérifiez que six répertoires virtuels sont répertoriés pour votre [!DNL Report Portal] comme illustré dans l’exemple suivant.

   ![](assets/rptPort_dia_VirDirs.png)

   Si vous ne voyez pas six répertoires virtuels ou si vous recevez un message d’erreur, cliquez sur **[!UICONTROL Cancel]** et examinez le fichier de configuration à la recherche d’erreurs.

1. Sélectionnez le premier répertoire virtuel de la liste (celui qui est le parent des cinq autres) et cliquez sur **[!UICONTROL OK]**. IIS importe les mappages et ajoute les répertoires virtuels au site Web par défaut.

   Assurez-vous que la structure de répertoires obtenue comporte un dossier parent (portant le même nom que votre portail) et cinq sous-répertoires, comme illustré dans l’exemple suivant.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Cliquez sur chaque répertoire virtuel pour vous assurer qu’IIS peut localiser le répertoire physique qu’il représente. Si IIS affiche une erreur, cliquez avec le bouton droit sur le nom du répertoire virtuel et vérifiez que le champ [!DNL Local Path] pointe vers le répertoire physique correct.

## Pour activer les pages de serveur Principal (ASP) sur IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Pour utiliser [!DNL Report Portal], ASP doit être activé sur IIS. (Par défaut, ASP est désactivé lorsque IIS 6.0 est installé.) Utilisez la procédure suivante pour vérifier que les ASP sont activés sur votre IIS.

1. Dans la fenêtre Gestionnaire des services Internet, sélectionnez **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Vérifiez que l’extension [!DNL Active Server Pages] est définie sur [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Si leur statut est interdit, sélectionnez **[!UICONTROL Active Server Pages]** et cliquez sur **[!UICONTROL Allow]**.
1. Fermez le Gestionnaire des services Internet (IIS).
