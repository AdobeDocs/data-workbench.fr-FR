---
description: Le fichier de configuration Log Processing Mode.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur de l’outil de données enregistre ses fichiers d’état.
solution: Analytics
title: Mode de traitement du journal.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mode de traitement du journal.cfg{#log-processing-mode-cfg}

Le fichier de configuration Log Processing Mode.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur de l’outil de données enregistre ses fichiers d’état.

Les modifications apportées au [!DNL Log Processing Mode.cfg] fichier, y compris l’ajout ou la suppression de sources, ne provoquent pas le retraitement des données.

**Pour modifier le fichier Log Processing Mode.cfg pour un profil de jeu de données**

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu.

   >[!NOTE]
   >
   >Si le [!DNL Log Processing Mode.cfg] fichier n’est pas situé dans le répertoire du profil souhaité, vous devez copier ce fichier du répertoire de base sur l’ordinateur du serveur de l’outil de données dans le répertoire du profil.

   Pour plus d’informations sur l’ouverture et l’utilisation de [!DNL Profile Manager,] Data Workbench, consultez le Guide *de l’utilisateur des outils de* données.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier de configuration, puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s’affiche.
1. Modifiez les paramètres du fichier de configuration à l’aide du tableau suivant comme guide.

   >[!NOTE]
   >
   >Certains paramètres du [!DNL Log Processing Mode.cfg] fichier portent des noms qui incluent [!DNL Fast Input] ou [!DNL Fast Merge]. [!DNL Fast Input]fait référence à la phase de traitement du journal de la construction des ensembles de données et est responsable d&#39;environ la moitié du temps total de traitement des ensembles de données. [!DNL Fast Merge] fait référence à la phase de transformation de la construction des jeux de données uniquement lorsqu&#39;elle est précédée par le traitement des journaux. [!DNL Fast Merge] ne se produit pas lors de la transformation résultant de la modification d’un [!DNL Transformation Dataset Configuration] fichier. Comme [!DNL Fast Input], [!DNL Fast Merge] est également responsable d&#39;environ la moitié du temps de traitement des jeux de données.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Octets du cloud </td> 
      <td colname="col2"> <p>Paramètre de réglage qui affecte l’efficacité de la transformation des données. La valeur par défaut est 128000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans consulter Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Taux de décision d’entrée rapide </td> 
      <td colname="col2"> <p>Paramètre de réglage qui spécifie le rapport entre le total et les octets de journal non lus au niveau duquel le système passe en mode d’entrée <span class="wintitle"></span> rapide (puis de fusion <span class="wintitle"></span>rapide) au lieu de traiter les données en temps réel. </p> <p> La valeur par défaut est 200, ce qui signifie que le système passe en mode <span class="wintitle"> d’entrée</span> rapide à partir du mode en temps réel lorsque les données de journal non lues se situent à 1/200ème des données totales. Un taux de décision plus élevé rend le système plus facile à entrer en mode <span class="wintitle"> d’entrée</span> rapide, tandis qu’un taux plus faible le rend moins susceptible d’entrer en mode d’entrée <span class="wintitle"></span> rapide. </p> <p> <p>Remarque : La définition du paramètre sur 0 empêche le système de passer en mode Entrée <span class="wintitle"></span> rapide, même pour le traitement initial. La définition du paramètre sur 1.1 permet au système d’entrer une entrée <span class="wintitle"></span> rapide lors du traitement initial, mais pas pour un traitement ultérieur. Adobe déconseille d’utiliser des valeurs comprises entre 0 et 1.1. Pour plus d’informations sur la définition de ce paramètre, contactez Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Octets FIFO d’entrée rapide </td> 
      <td colname="col2"> <p>Paramètre de réglage qui équilibre l’utilisation de la mémoire et les performances du système pendant le traitement des données. La valeur par défaut est 120000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans consulter Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Octets de mémoire tampon de fusion rapide </td> 
      <td colname="col2"> <p>Paramètre de réglage qui équilibre l’utilisation de la mémoire et les performances du système pendant le traitement des données. La valeur par défaut est 128000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans consulter Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Sources hors ligne </td> 
      <td colname="col2"> <p>Masque de la source du journal hors ligne. </p> <p> <b> Pour spécifier une source hors ligne</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Cliquez avec le bouton droit de la souris sur Sources <span class="uicontrol"> hors ligne, puis sur</span>Ajouter une nouvelle <span class="uicontrol"> &gt;</span> Source <span class="uicontrol"></span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Dans le paramètre de la nouvelle source, saisissez le masque de la séquence de journaux. Pour les sources de journaux de Sensor avec des noms de fichier au format AAAAMMJJ-<i>SENSORID</i>.vsl, le masque est <i>SENSORID.SENSORID</i> est sensible à la casse. Pour les sources de journaux de fichiers journaux, le masque est la chaîne extraite par le <span class="wintitle"> modèle de masque</span>. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </li> 
      </ul> </p> <p> L’ajout ou la suppression de sources dans les sources hors ligne n’entraîne pas le retraitement du jeu de données. </p> <p> A partir du moment où les mesures sont maintenues pour le traitement des sources en ligne du profil. Lorsque la source hors ligne est de nouveau en ligne, le traitement des fichiers journaux entrants pour cette source reprend. </p> <p> Chaque fois qu’une source revient en ligne, vous devez la supprimer des sources hors ligne. Si vous ne le faites pas, le serveur de l’outil de données traite la source comme une source en ligne et met à jour l’outil A partir du moment où la source envoie les données. Si la source est de nouveau hors ligne, les mesures A partir du moment s’arrêtent. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> En pause </td> 
      <td colname="col2"> True ou false. Si la valeur est true, les nouvelles données ne sont pas traitées dans le jeu de données. La valeur par défaut est false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Délai en temps réel </td> 
      <td colname="col2"> durée, en secondes, pendant laquelle le serveur de l’outil de données attend entre les intervalles de traitement des données dans le jeu de données. Lorsque cette valeur est définie sur zéro, le système tente de suivre les données entrantes en temps réel. La valeur par défaut est zéro (0), mais vous pouvez augmenter cette valeur pour réduire la charge CPU. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Octets FIFO en temps réel </td> 
      <td colname="col2"> <p>Quantité de mémoire en octets utilisée pour stocker les données en attente de traitement dans le jeu de données. Vous devrez peut-être modifier cette valeur en fonction du nombre de secondes spécifié pour le délai en temps réel. La valeur par défaut est 16000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans consulter Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervalle d’enregistrement (s) </td> 
      <td colname="col2"> <p>Fréquence à laquelle le serveur de l’outil de données enregistre ses fichiers d’état. La valeur par défaut est 3600. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans consulter Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Lors de la modification du [!DNL Log Processing Mode.cfg] fichier dans une fenêtre de l’outil de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller le texte d’un fichier de configuration ( [!DNL .cfg]) vers un autre.

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.
