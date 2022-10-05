---
description: Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour le stockage des données de jeux de données.
title: Surveillance de l’espace des données du jeu de données
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Surveillance de l’espace des données du jeu de données{#monitoring-dataset-data-space}

{{eol}}

Informations sur la surveillance des jeux de données et l’ajout de nouveaux emplacements pour le stockage des données de jeux de données.

**Fréquence recommandée :** Toutes les 5-10 minutes

Par défaut, [!DNL Insight Server] écrit son jeu de données dans la variable [!DNL temp.db] sur le même lecteur que le fichier [!DNL Insight Server] fichiers de programme sur l’unité de traitement des données. La quantité de données du jeu de données par [!DNL Insight Server] La machine est limitée aux éléments suivants, selon ce qui se produit en premier :

* Cinq cent (500) millions d’enregistrements d’entrée de données pour ce jeu de données
* 500 (500) Go de données de jeu stockées
* Un (1) Mo de données de jeu de données stockées pour n’importe quelle dimension de niveau racine (par exemple, 5 000 enregistrements par visiteur à une moyenne de 200 octets par enregistrement).

Si vous voulez [!DNL Insight Server] pour gérer le jeu de données sur un autre lecteur ou si la quantité de données que vous prévoyez de collecter nécessite l’utilisation de plusieurs lecteurs, vous devez mettre à jour le fichier de configuration Fichiers de disque ( [!DNL Disk Files.cfg]) pour spécifier l’emplacement souhaité. [!DNL Insight Server] pour écrire la variable [!DNL temp.db] fichier(s). Le [!DNL Disk Files.cfg] Le fichier répertorie les fichiers de disque (un vecteur de chaînes) et spécifie l’emplacement des données du jeu de données utilisées par [!DNL Insight Server] pendant le retraitement et l’opération. Il y a généralement un fichier par disque physique.

>[!NOTE]
>
>Le contenu de la variable [!DNL Disk Files.cfg] a peut-être été modifié lors de l’installation. [!DNL Insight Server]. Pour plus d’informations, voir [Configuration de l’emplacement du jeu de données (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Pour ajouter de nouveaux emplacements pour le stockage des données de jeu de données**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Disk Files.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Disk Files.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Disk Files.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans le [!DNL Disk Files.cfg] fenêtre, cliquez sur **[!UICONTROL component]** pour afficher son contenu.

   ![Infos sur l’étape](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter la corruption du disque est défini sur true par défaut. Le paramètre Taille du cache de disque (Mo) contrôle la quantité de mémoire qui [!DNL Insight Server] utilise pour augmenter la vitesse d’accès au disque et est défini sur 128 par défaut. Contactez l’Adobe avant de modifier l’un de ces paramètres.

1. Pour modifier les fichiers de disque sur le [!DNL Insight Server] machine, clic droit **[!UICONTROL Disk Files]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Pour supprimer un fichier de disque, cliquez avec le bouton droit de la souris sur le numéro du fichier de disque, puis cliquez sur **[!UICONTROL Remove]**.

1. Pour le nouveau fichier de disque, saisissez le répertoire et le nom du fichier à utiliser par [!DNL Insight Server] pendant le retraitement et l’opération.

   ![Infos sur l’étape](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Le paramètre Détecter la corruption du disque est défini sur true par défaut. Le paramètre Taille du cache de disque (Mo) contrôle la quantité de mémoire qui [!DNL Insight Server] utilise pour augmenter la vitesse d’accès au disque et est défini sur 128 par défaut. Contactez l’Adobe avant de modifier l’un de ces paramètres.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
