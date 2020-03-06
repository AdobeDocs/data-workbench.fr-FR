---
description: Maintenant que le champ x-experience est disponible, vous devez créer une dimension étendue afin d’inclure le champ x-experience dans votre jeu de données, ce qui vous permet d’afficher vos résultats dans Insight.
solution: Insight,Analytics
title: Modification de Transformation.cfg
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Modification de Transformation.cfg{#modifying-transformation-cfg}

Maintenant que le champ x-experience est disponible, vous devez créer une dimension étendue afin d’inclure le champ x-experience dans votre jeu de données, ce qui vous permet d’afficher vos résultats dans Insight.

Pour ce faire, vous devez ajouter une nouvelle dimension au [!DNL Transformation.cfg] fichier.

Si vous prévoyez d’exécuter plusieurs expériences, vous devez également ajouter une nouvelle transformation Split au [!DNL Transformation.cfg] fichier. Cette transformation de fractionnement sépare les différents noms d’expérience et de groupe afin que les informations soient plus faciles à interpréter. Pour éviter de retraiter vos données si vous deviez ajouter d’autres expériences ultérieurement, Adobe vous conseille d’ajouter la transformation Split même si vous ne prévoyez pas d’exécuter plusieurs expériences.

La procédure suivante inclut la création de la nouvelle transformation Fractionnée et de la dimension étendue. Si vous ne souhaitez pas ajouter la transformation Fractionner, ignorez simplement les étapes 5 à 7.

**Pour modifier Transformation.cfg**

1. Dans [!DNL Insight]la, ouvrez l’ [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail et en cliquant **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, ou en ouvrant l’espace de travail Gestion des profils dans l’ [!DNL Admin] onglet.
1. Dans la [!DNL Profile Manager], cliquez **[!UICONTROL Dataset]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Transformation.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Transformation.cfg] fenêtre s&#39;affiche.
1. Cliquez sur **[!UICONTROL Transformation]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris **[!UICONTROL Transformations]** , puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Terminez la nouvelle division sur la transformation des virgules, comme illustré dans l’exemple suivant :

   ![Infos sur l’étape](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Vous pouvez saisir n’importe quelle valeur dans le champ Nom.

1. Cliquez avec le bouton droit de la souris **[!UICONTROL Extended Dimensions]** , puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Remplissez la nouvelle dimension comme illustré dans l’exemple suivant :

   ![Infos sur l’étape](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Vous pouvez saisir n’importe quelle valeur dans le champ Nom.
   >* Si vous n’avez pas inclus la transformation de fractionnement, vous devez taper &quot;x-experience&quot; dans le [!DNL Input] champ.


1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Transformation.cfg] de la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]** pour enregistrer les modifications apportées localement au profil de travail.

   >[!NOTE]
   >
   >Le jeu de données commence à se transformer immédiatement.

   Pour plus d’informations sur les dimensions [!DNL Transformation.cfg] et étendues, voir le Guide *de configuration des jeux de* données.
