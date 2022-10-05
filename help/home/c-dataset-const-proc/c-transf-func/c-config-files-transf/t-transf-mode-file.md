---
description: Le fichier de configuration Transform Mode.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur Data Workbench exécutant la fonctionnalité de transformation enregistre ses fichiers d’état.
title: Fichier Transform Mode.cfg
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# Fichier Transform Mode.cfg{#the-transform-mode-cfg-file}

{{eol}}

Le fichier de configuration Transform Mode.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur Data Workbench exécutant la fonctionnalité de transformation enregistre ses fichiers d’état.

Changements apportés à la variable [!DNL Transform Mode.cfg] , y compris l’ajout ou la suppression de sources, ne provoque pas le retraitement des données.

**Pour modifier le fichier Transform Mode.cfg d’un profil de jeu de données**

1. Lorsque vous travaillez dans le profil dont vous souhaitez exporter les données, ouvrez le [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu du répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Transform Mode.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL Transform Mode.cfg] s’affiche.
1. Modifiez les paramètres du fichier de configuration à l’aide du tableau suivant comme guide :

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Paramètre </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Sources hors ligne </td> 
    <td colname="col2"> <p>Masque de la source du journal hors ligne. </p> <p> Pour spécifier une source hors ligne : </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Clic droit <span class="uicontrol"> Sources hors ligne</span> et cliquez sur <span class="uicontrol"> Ajouter</span> &gt; <span class="uicontrol"> Source</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Dans le paramètre de la nouvelle source, saisissez le masque de la séquence du journal. Pour les sources de journaux de Capteur avec des noms de fichier au format <span class="filepath"> YYYYMDD-SENSORID.vsl</span>, le masque est <i>SENSORID.SENSORID</i> est sensible à la casse. Pour les sources de journal des fichiers journaux, le masque est la chaîne extraite par le <span class="wintitle"> Modèle de masque</span> (voir <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Fichiers journaux</a>). </li> 
    </ul> <p> Ajout ou suppression de sources à partir de <span class="wintitle"> Sources hors ligne</span> ne provoque pas le retraitement du jeu de données. </p> <p> À partir du moment, les mesures sont conservées pour le traitement des sources en ligne du profil. Lorsque la source hors ligne est de nouveau en ligne, le traitement des fichiers journaux entrants pour cette source reprend. </p> <p> <p>Remarque : Chaque fois qu'une source revient en ligne, vous devez la supprimer de <span class="wintitle"> Sources hors ligne</span>. Si vous ne le faites pas, le serveur Data Workbench traite la source comme une source en ligne et met à jour le à partir du moment où la source envoie les données. Si la source est à nouveau hors ligne, les mesures À partir du moment s’arrêtent. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> En pause </td> 
    <td colname="col2"> True ou false. Si la valeur est true, les nouvelles données ne sont pas traitées dans le jeu de données. La valeur par défaut est false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervalle de sauvegarde (sec) </td> 
    <td colname="col2"> <p>Fréquence à laquelle le serveur Data Workbench sur lequel la fonctionnalité de transformation est en cours d’exécution enregistre ses fichiers d’état. La valeur par défaut est 3600. </p> <p> <p>Remarque : Vous ne devez pas modifier cette valeur sans Adobe de conseil. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Lors de la modification de la variable [!DNL Transform Mode.cfg] dans une fenêtre Data Workbench, vous pouvez utiliser des raccourcis clavier pour les fonctions d’édition de base, notamment couper (Ctrl+x ), copier (Ctrl+c), coller (Ctrl+v ), annuler (Ctrl+z ), rétablir (Ctrl+Maj+z ), sélectionner une section (cliquer+faire glisser), tout sélectionner (Ctrl+a ). En outre, vous pouvez utiliser les raccourcis pour copier et coller du texte d’un fichier de configuration ( [!DNL .cfg]) à un autre.

1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche de Data Workbench. [!DNL Transform Mode.cfg] dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, où nom du profil est le nom du profil pour lequel vous exportez des données. Le retraitement des données commence après la synchronisation du profil.

   Pour plus d’informations sur le retraitement de vos données en vue de l’exportation, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
