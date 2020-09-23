---
description: Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour l’enregistrement de données des jeux de données.
solution: Analytics
title: Surveillance de l’espace des données du jeu de données
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---


# Surveillance de l’espace des données du jeu de données{#monitoring-dataset-data-space}

Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour l’enregistrement de données des jeux de données.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

Par défaut, [!DNL Insight Server] écrit son jeu de données dans le [!DNL temp.db] fichier sur le même lecteur que les fichiers [!DNL Insight Server] de programme de l&#39;unité de traitement des données. La quantité de données de jeux de données par [!DNL Insight Server] ordinateur est limitée aux éléments suivants, selon ce qui se produit en premier :

* Cinq cent (500) millions d&#39;enregistrements d&#39;entrée de données dans ce jeu de données
* 500 (500) Go de données d’ensemble stockées
* Un (1) Mo de données d&#39;ensemble de données stockées par dimension de niveau racine (par exemple, 5 000 enregistrements par Visiteur à une moyenne de 200 octets par enregistrement)

Si vous souhaitez [!DNL Insight Server] conserver le jeu de données sur un autre lecteur ou si la quantité de données que vous prévoyez de collecter nécessite l&#39;utilisation de plusieurs lecteurs, vous devez mettre à jour le fichier de configuration Fichiers de disque ( [!DNL Disk Files.cfg]) pour indiquer où vous souhaitez [!DNL Insight Server] écrire le ou les [!DNL temp.db] fichiers. Le [!DNL Disk Files.cfg] fichier liste les fichiers de disque (un vecteur de chaînes) et indique l’emplacement des données du jeu de données utilisées [!DNL Insight Server] lors du retraitement et du fonctionnement. Il y a généralement un fichier par disque physique.

>[!NOTE]
>
>Le contenu du [!DNL Disk Files.cfg] fichier a peut-être été modifié lors de l&#39;installation [!DNL Insight Server]. Pour plus d’informations, voir [Configuration de l’emplacement du jeu de données (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Pour ajouter de nouveaux emplacements pour l’enregistrement de données de jeu de données**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône de la [!DNL Insight Server] fenêtre à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en vue le contenu. Le [!DNL Disk Files.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche de la colonne du nom *du* serveur [!DNL Disk Files.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Disk Files.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la [!DNL Disk Files.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en vue le contenu.

   ![Infos sur l’étape](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter l&#39;altération du disque est défini sur true par défaut. Le paramètre Disk Cache Size (MB) contrôle la quantité de mémoire utilisée [!DNL Insight Server] pour augmenter la vitesse d&#39;accès du disque et est défini sur 128 par défaut. Veuillez contacter l&#39;Adobe avant de modifier l&#39;un ou l&#39;autre de ces paramètres.

1. Pour modifier les fichiers de disque sur l’ [!DNL Insight Server] ordinateur, cliquez avec le bouton droit **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Pour supprimer un fichier de disque, cliquez avec le bouton droit de la souris sur le numéro de fichier de disque et cliquez sur **[!UICONTROL Remove]**.

1. Pour le nouveau fichier de disque, saisissez le répertoire et le nom du fichier à utiliser [!DNL Insight Server] lors du retraitement et de l’opération.

   ![Infos sur l’étape](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter l&#39;altération du disque est défini sur true par défaut. Le paramètre Disk Cache Size (MB) contrôle la quantité de mémoire utilisée [!DNL Insight Server] pour augmenter la vitesse d&#39;accès du disque et est défini sur 128 par défaut. Veuillez contacter l&#39;Adobe avant de modifier l&#39;un ou l&#39;autre de ces paramètres.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** de la souris en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

