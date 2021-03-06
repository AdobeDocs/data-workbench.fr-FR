---
description: Étapes de modification des fichiers Report.cfg existants à l’aide de Worktop ou d’un éditeur de texte.
title: Modification de fichiers Report.cfg existants
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Modification de fichiers Report.cfg existants{#editing-existing-report-cfg-files}

Étapes de modification des fichiers Report.cfg existants à l’aide de Worktop ou d’un éditeur de texte.

>[!NOTE]
>
>* Vous devez travailler en ligne pour modifier les fichiers [!DNL Report.cfg]. Pour travailler en ligne, dans la balise [!DNL Worktop], cliquez avec le bouton droit sur la barre de titre et cliquez sur **[!UICONTROL Work Online]**.
   >
   >
* Si le paramètre **[!UICONTROL Allow Report Regeneration]** du fichier [!DNL Report.cfg] est défini sur [!DNL True], lorsque vous apportez des modifications à ce fichier et que vous le réenregistrez sur le serveur, [!DNL Report] regénère automatiquement les rapports de cet ensemble. Bien qu’il régénère les rapports, il ne les renvoie pas par email. Pour connaître les étapes à suivre, reportez-vous à la section [Renvoi de rapports par courrier électronique](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).

>



Vous pouvez modifier un [!DNL Report.cfg] existant à partir de [!DNL Worktop] ou à l’aide d’un éditeur de texte.

La modification d’un fichier [!DNL Report.cfg] à l’aide de l’onglet [!DNL Reports] de [!DNL Worktop] permet de ne modifier que les paramètres, les vecteurs et les éléments vectoriels qui existent déjà dans le fichier. Si vous devez ajouter un paramètre ou un vecteur au fichier, vous devez le modifier à l’aide d’un éditeur de texte, tel que le Bloc-notes.

* [Pour modifier un fichier Report.cfg existant à l’aide du plan de travail](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Pour modifier un fichier Report.cfg existant à l’aide d’un éditeur de texte](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Pour modifier un fichier Report.cfg existant à l’aide du plan de travail {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Vous devez travailler en ligne pour modifier la balise [!DNL Report.cfg] de la balise [!DNL Worktop].

1. Dans Data Workbench, sous l’onglet [!DNL Reports], sélectionnez le sous-dossier (sous-répertoire de tabulation ou de liste déroulante) du jeu de rapports que vous souhaitez configurer.
1. Cliquez sur **[!UICONTROL Report.cfg]**. Les paramètres de [!DNL Report.cfg] de ce jeu de rapports s’affichent.

1. Modifiez les paramètres de configuration suivant vos besoins. Pour plus d’informations sur ces paramètres, voir [Paramètres Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Enregistrez le fichier en cliquant avec le bouton droit de la souris sur **[!UICONTROL Report.cfg (modified)]** en haut des paramètres et en cliquant sur **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]***.

## Pour modifier un fichier Report.cfg existant à l’aide d’un éditeur de texte {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Ouvrez le [!DNL Reports Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Cliquez sur le dossier de votre jeu de rapports.
1. Cliquez avec le bouton droit de la souris sur la coche située en regard de [!DNL Report.cfg] pour ce jeu de rapports, puis cliquez sur **[!UICONTROL Make Local]**.

1. Dans la colonne [!DNL User] , cliquez avec le bouton droit de la souris sur la coche située en regard de [!DNL Report.cfg] pour ce jeu de rapports, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier [!DNL Report.cfg] s’ouvre.

   L’exemple [!DNL Report.cfg] illustré dans [Configurer le jeu de rapports](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contient uniquement les paramètres inclus dans le fichier [!DNL Report.cfg] par défaut. L’exemple suivant inclut tous les paramètres disponibles pour le fichier [!DNL Report.cfg] que vous pouvez utiliser comme modèles pour vos entrées de paramètre :

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Modifiez les paramètres de configuration suivant vos besoins. Pour plus d’informations sur ces paramètres, voir [Paramètres Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Enregistrez le fichier, puis fermez-le.
1. Dans la balise [!DNL Reports Manager], cliquez avec le bouton droit de la souris sur la coche de la colonne [!DNL User] du fichier [!DNL Report.cfg] et sélectionnez **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]***.
