---
description: Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour l’enregistrement de données des jeux de données.
title: Surveillance de l’espace des données du jeu de données
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Surveillance de l’espace des données du jeu de données{#monitoring-dataset-data-space}

Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour l’enregistrement de données des jeux de données.

**Fréquence recommandée :** toutes les 5 à 10 minutes

Par défaut, [!DNL Insight Server] écrit son jeu de données dans le fichier [!DNL temp.db] du même lecteur que les fichiers de programme [!DNL Insight Server] de l&#39;unité de traitement des données. La quantité de données de jeux de données par machine [!DNL Insight Server] est limitée aux éléments suivants, selon ce qui se produit en premier :

* Cinq cent (500) millions d&#39;enregistrements d&#39;entrée de données dans ce jeu de données
* 500 (500) Go de données d’ensemble stockées
* Un (1) Mo de données d&#39;ensemble de données stockées par dimension de niveau racine (par exemple, 5 000 enregistrements par Visiteur à une moyenne de 200 octets par enregistrement)

Si vous souhaitez que [!DNL Insight Server] conserve le jeu de données sur un autre lecteur, ou si la quantité de données que vous prévoyez de collecter nécessite l&#39;utilisation de plusieurs lecteurs, vous devez mettre à jour le fichier de configuration Fichiers de disque ( [!DNL Disk Files.cfg]) pour spécifier où [!DNL Insight Server] doit écrire le ou les fichiers [!DNL temp.db]. Le fichier [!DNL Disk Files.cfg] liste les fichiers de disque (un vecteur de chaînes) et indique l&#39;emplacement des données du jeu de données utilisées par [!DNL Insight Server] lors du retraitement et du fonctionnement. Il y a généralement un fichier par disque physique.

>[!NOTE]
>
>Le contenu du fichier [!DNL Disk Files.cfg] a peut-être été modifié lors de l&#39;installation de [!DNL Insight Server]. Pour plus d&#39;informations, voir [Configuration de l&#39;emplacement du jeu de données (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Pour ajouter de nouveaux emplacements pour l’enregistrement de données de jeu de données**

1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l&#39;icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en vue le contenu. Le fichier [!DNL Disk Files.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit sur la coche de la colonne *nom du serveur* pour [!DNL Disk Files.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Disk Files.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la fenêtre [!DNL Disk Files.cfg], cliquez sur **[!UICONTROL component]** pour en vue le contenu.

   ![Infos sur l’étape](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter l&#39;altération du disque est défini sur true par défaut. Le paramètre Disk Cache Size (MB) contrôle la quantité de mémoire utilisée par [!DNL Insight Server] pour augmenter la vitesse d&#39;accès du disque et est défini sur 128 par défaut. Veuillez contacter l&#39;Adobe avant de modifier l&#39;un ou l&#39;autre de ces paramètres.

1. Pour modifier les fichiers de disque sur l&#39;ordinateur [!DNL Insight Server], cliquez avec le bouton droit de la souris sur **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Pour supprimer un fichier de disque, cliquez avec le bouton droit de la souris sur le numéro de fichier de disque et cliquez sur **[!UICONTROL Remove]**.

1. Pour le nouveau fichier de disque, saisissez le répertoire et le nom du fichier à utiliser par [!DNL Insight Server] lors du retraitement et de l&#39;opération.

   ![Infos sur l’étape](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter l&#39;altération du disque est défini sur true par défaut. Le paramètre Disk Cache Size (MB) contrôle la quantité de mémoire utilisée par [!DNL Insight Server] pour augmenter la vitesse d&#39;accès du disque et est défini sur 128 par défaut. Veuillez contacter l&#39;Adobe avant de modifier l&#39;un ou l&#39;autre de ces paramètres.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la colonne [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
