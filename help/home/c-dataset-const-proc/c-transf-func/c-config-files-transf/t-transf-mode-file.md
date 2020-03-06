---
description: Le fichier de configuration Transform Mode.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur d’outils de données exécutant la fonctionnalité de transformation enregistre ses fichiers d’état.
solution: Analytics
title: Le fichier Transform Mode.cfg
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Le fichier Transform Mode.cfg{#the-transform-mode-cfg-file}

Le fichier de configuration Transform Mode.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur d’outils de données exécutant la fonctionnalité de transformation enregistre ses fichiers d’état.

Les modifications apportées au [!DNL Transform Mode.cfg] fichier, y compris l’ajout ou la suppression de sources, ne provoquent pas le retraitement des données.

**Pour modifier le fichier Transform Mode.cfg pour un profil de jeu de données**

1. Lorsque vous travaillez dans le profil dont vous souhaitez exporter les données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu du répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Transform Mode.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL Transform Mode.cfg] fenêtre s&#39;affiche.
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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Cliquez avec le bouton droit de la souris sur Sources <span class="uicontrol"> hors ligne et cliquez sur</span> Ajouter une nouvelle <span class="uicontrol"> &gt;</span> Source <span class="uicontrol"></span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Dans le paramètre de la nouvelle source, saisissez le masque de la séquence de journaux. Pour les sources de journaux de Sensor avec des noms de fichier au format <span class="filepath"> AAAAMMJJ-SENSORID.vsl</span>, le masque est <i>SENSORID.SENSORID</i> est sensible à la casse. Pour les sources de journaux de fichiers journaux, le masque est la chaîne extraite par le modèle <span class="wintitle"> de</span> masque (voir Fichiers <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> journaux</a>). </li> 
    </ul> <p> L’ajout ou la suppression de sources des sources <span class="wintitle"></span> hors ligne n’entraîne pas le retraitement du jeu de données. </p> <p> A partir du moment où les mesures sont maintenues pour le traitement des sources en ligne du profil. Lorsque la source hors ligne est de nouveau en ligne, le traitement des fichiers journaux entrants pour cette source reprend. </p> <p> <p>Remarque : Chaque fois qu’une source revient en ligne, vous devez la supprimer des sources <span class="wintitle"></span>hors ligne. Si vous ne le faites pas, le serveur de l’outil de données traite la source comme une source en ligne et met à jour l’outil A partir du moment où la source envoie les données. Si la source est de nouveau hors ligne, les mesures A partir du moment s’arrêtent. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> En pause </td> 
    <td colname="col2"> True ou false. Si la valeur est true, les nouvelles données ne sont pas traitées dans le jeu de données. La valeur par défaut est false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervalle d’enregistrement (s) </td> 
    <td colname="col2"> <p>Fréquence à laquelle le serveur de l’outil de données sur lequel la fonctionnalité de transformation est en cours d’exécution enregistre ses fichiers d’état. La valeur par défaut est 3600. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans consulter Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Lors de la modification du [!DNL Transform Mode.cfg] fichier dans une fenêtre de l’outil de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller le texte d’un fichier de configuration ( [!DNL .cfg]) vers un autre.

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche de l’outil de données [!DNL Transform Mode.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, où nom du profil est le nom du profil pour lequel vous exportez des données. Le retraitement des données commence après la synchronisation du profil.

   Pour plus d’informations sur le retraitement de vos données pour l’exportation, voir [Retraitement et retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
