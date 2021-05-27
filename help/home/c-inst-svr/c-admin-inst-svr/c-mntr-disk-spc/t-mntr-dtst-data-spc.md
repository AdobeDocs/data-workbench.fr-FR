---
description: Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour le stockage des données de jeux de données.
title: Surveillance de l’espace des données du jeu de données
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Surveillance de l’espace des données du jeu de données{#monitoring-dataset-data-space}

Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour le stockage des données de jeux de données.

**Fréquence recommandée :** Toutes les 5-10 minutes

Par défaut, [!DNL Insight Server] écrit son jeu de données dans le fichier [!DNL temp.db] sur le même lecteur que les fichiers de programme [!DNL Insight Server] de l’unité de traitement des données. La quantité de données de jeu de données par [!DNL Insight Server] machine est limitée à ce qui suit, selon ce qui se produit en premier :

* Cinq cent (500) millions d’enregistrements d’entrée de données pour ce jeu de données
* 500 (500) Go de données de jeu stockées
* Un (1) Mo de données de jeu de données stockées pour n’importe quelle dimension de niveau racine (par exemple, 5 000 enregistrements par visiteur à une moyenne de 200 octets par enregistrement).

Si vous souhaitez que [!DNL Insight Server] conserve le jeu de données sur un autre lecteur ou si la quantité de données que vous prévoyez de collecter nécessite l’utilisation de plusieurs lecteurs, vous devez mettre à jour le fichier de configuration Fichiers de disque ( [!DNL Disk Files.cfg]) pour spécifier où [!DNL Insight Server] doit écrire le ou les fichiers [!DNL temp.db]. Le fichier [!DNL Disk Files.cfg] répertorie les fichiers de disque (un vecteur de chaînes) et spécifie l’emplacement des données du jeu de données utilisées par [!DNL Insight Server] lors du retraitement et de l’opération. Il y a généralement un fichier par disque physique.

>[!NOTE]
>
>Le contenu du fichier [!DNL Disk Files.cfg] peut avoir été modifié lors de l&#39;installation de [!DNL Insight Server]. Pour plus d’informations, voir [Configuration de l’emplacement du jeu de données (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Pour ajouter de nouveaux emplacements pour le stockage des données de jeu de données**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en visualiser le contenu. Le fichier [!DNL Disk Files.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* pour [!DNL Disk Files.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Disk Files.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la fenêtre [!DNL Disk Files.cfg], cliquez sur **[!UICONTROL component]** pour en visualiser le contenu.

   ![Infos sur l’étape](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter la corruption du disque est défini sur true par défaut. Le paramètre Disk Cache Size (MB) contrôle la quantité de mémoire utilisée par [!DNL Insight Server] pour augmenter la vitesse d’accès au disque et est défini sur 128 par défaut. Contactez l’Adobe avant de modifier l’un de ces paramètres.

1. Pour modifier les fichiers de disque sur la machine [!DNL Insight Server], cliquez avec le bouton droit de la souris sur **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Pour supprimer un fichier de disque, cliquez avec le bouton droit de la souris sur le numéro du fichier de disque et cliquez sur **[!UICONTROL Remove]**.

1. Pour le nouveau fichier disque, saisissez le répertoire et le nom du fichier à utiliser par [!DNL Insight Server] lors du retraitement et de l’opération.

   ![Infos sur l’étape](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter la corruption du disque est défini sur true par défaut. Le paramètre Disk Cache Size (MB) contrôle la quantité de mémoire utilisée par [!DNL Insight Server] pour augmenter la vitesse d’accès au disque et est défini sur 128 par défaut. Contactez l’Adobe avant de modifier l’un de ces paramètres.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
