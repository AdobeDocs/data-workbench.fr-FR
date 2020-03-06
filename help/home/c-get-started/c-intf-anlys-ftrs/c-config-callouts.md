---
description: Les légendes attirent l’attention sur un élément de dimension particulier en créant une nouvelle visualisation avec une sélection virtuelle d’un élément de dimension particulier dans une visualisation.
solution: Analytics
title: Configuration d’une légende
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration d’une légende{#configure-a-callout}

Les légendes attirent l’attention sur un élément de dimension particulier en créant une nouvelle visualisation avec une sélection virtuelle d’un élément de dimension particulier dans une visualisation.

Vous pouvez ajouter ou modifier des légendes en configurant les fichiers de légende stockés dans un dossier d’installation Profils\*nom du profil*\Context\Callout folder of the [!DNL Server] . Les légendes qui attirent l’attention sur une mesure particulière dans une visualisation de feuille de calcul sont appelées légendes de mesure. Les fichiers de légende de mesure sont stockés dans le dossier Profils\*nom du profil*\Context\Metric Callout folder.

Pour obtenir des instructions sur l’ajout d’une légende ou d’une légende de mesure à une visualisation, voir [Ajout d’légendes à un espace de travail](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Pour créer un nouveau type de légende**

1. Dans n’importe quel espace de travail, créez une visualisation contenant les données que vous souhaitez voir apparaître dans le nouveau type de légende. Par exemple, si vous souhaitez que votre légende soit un tableau, vous créez une visualisation de tableau présentant la mesure et la dimension souhaitées.
1. Cliquez avec le bouton droit sur la bordure supérieure de la fenêtre de légende, puis cliquez sur **[!UICONTROL Save]**.
1. Dans la [!DNL Save] fenêtre, cliquez ![](assets/btn_folder_up.png), double-cliquez **[!UICONTROL Context]**, puis double-cliquez **[!UICONTROL Callout]**. Dans le [!DNL File Name] champ, saisissez le nom du fichier, puis cliquez sur **[!UICONTROL Save]**. Le fichier de légende est enregistré dans le nom du profil utilisateur\*\Context\Callout folder.

   >[!NOTE]
   >
   >Lorsque vous nommez votre légende, choisissez un nom descriptif qui reflète le type de visualisation, la mesure et la dimension qu’elle affiche. Par exemple, si vous souhaitez créer une légende à partir d’une visualisation de tableau présentant la mesure Sessions sur la dimension Jour, vous pouvez nommer la légende &quot;Table Sessions par jour&quot;.

1. (Facultatif) Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail :

   1. Dans la [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]**, puis sur **[!UICONTROL Callout]**. Ce dossier contient tous les fichiers de visualisation ( [!DNL .vw]) qui définissent les types de légende existants.

   1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier de la nouvelle légende dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Pour transformer une légende en légende de mesure**

1. Dans la [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]**, puis sur **[!UICONTROL Callout]**. Ce dossier contient tous les fichiers de visualisation ( [!DNL .vw]) qui définissent les types de légende existants.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier du type de légende à modifier, puis cliquez sur **[!UICONTROL Make Local]**. Une fois le fichier téléchargé sur l’ordinateur local, une coche apparaît dans la [!DNL User] colonne.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Recherchez l’ [!DNL metric_y = ref:] entrée dans le fichier de légende et remplacez la valeur existante par le mot Mesure. Le texte en surbrillance dans le fragment de fichier suivant indique l’endroit où vous insérez ce mot.

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]**. Dans la **[!UICONTROL Save As]** fenêtre, cliquez une fois, puis double-cliquez **[!UICONTROL Metric Callout]**. Dans le [!DNL File Name] champ, saisissez le nom du fichier, puis cliquez sur **[!UICONTROL Save]**. Le fichier de légende de mesure est enregistré dans le nom du profil utilisateur\*nom du profil de travail*\Context\Metric Callout folder.

1. (Facultatif) Pour rendre cette légende de mesure accessible à tous les utilisateurs du profil de travail, dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche en regard du nom de fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

