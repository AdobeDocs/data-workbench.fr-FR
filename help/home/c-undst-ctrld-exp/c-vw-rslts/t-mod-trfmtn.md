---
description: Maintenant que le champ x-expérience est disponible, vous devez créer une dimension étendue pour inclure le champ x-expérience dans votre jeu de données, ce qui vous permet d’afficher vos résultats dans Insight.
solution: Analytics
title: Modification de Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Modification de Transformation.cfg{#modifying-transformation-cfg}

Maintenant que le champ x-expérience est disponible, vous devez créer une dimension étendue pour inclure le champ x-expérience dans votre jeu de données, ce qui vous permet d’afficher vos résultats dans Insight.

Pour ce faire, vous devez ajouter une nouvelle dimension au [!DNL Transformation.cfg] fichier .

Si vous prévoyez d’exécuter plusieurs expériences, vous devez également ajouter une nouvelle transformation Partage à la variable [!DNL Transformation.cfg] fichier . Cette transformation de division sépare les différents noms d’expérience et de groupe afin que les informations soient plus faciles à interpréter. Pour éviter de retraiter vos données si vous deviez ajouter d’autres expériences ultérieurement, Adobe vous recommande d’ajouter la transformation Partage même si vous ne prévoyez pas d’exécuter plusieurs expériences.

La procédure suivante inclut la création de la nouvelle transformation Partage et de la dimension étendue. Si vous ne souhaitez pas ajouter la transformation Partage, ignorez les étapes 5 à 7.

**Modification de Transformation.cfg**

1. Dans [!DNL Insight], ouvrez le [!DNL Profile Manager] en cliquant avec le bouton droit dans un espace de travail, puis en cliquant sur **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** ou en ouvrant l’espace de travail de la gestion des profils sur le [!DNL Admin] .
1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Dataset]** pour afficher son contenu.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Transformation.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Le [!DNL Transformation.cfg] s’affiche.
1. Cliquez sur **[!UICONTROL Transformation]** pour afficher son contenu.
1. Clic droit **[!UICONTROL Transformations]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Complétez le nouveau partage sur la transformation des virgules comme illustré dans l’exemple suivant :

   ![Infos sur l’étape](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Vous pouvez saisir n’importe quelle valeur dans le champ Nom .

1. Clic droit **[!UICONTROL Extended Dimensions]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Renseignez la nouvelle dimension comme illustré dans l’exemple suivant :

   ![Infos sur l’étape](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Vous pouvez saisir n’importe quelle valeur dans le champ Nom .
   >* Si vous n’avez pas inclus la transformation Partage, vous devez saisir &quot;x-experience&quot; dans la variable [!DNL Input] champ .


1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Transformation.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]** pour enregistrer les modifications apportées localement au profil de travail.

   >[!NOTE]
   >
   >Le jeu de données commence à se retransformer immédiatement.

   Pour plus d’informations sur [!DNL Transformation.cfg] et les dimensions étendues, voir *Guide de configuration des jeux de données*.
