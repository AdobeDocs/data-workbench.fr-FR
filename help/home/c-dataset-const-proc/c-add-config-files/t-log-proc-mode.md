---
description: Le fichier de configuration Mode de traitement du journal.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur Data Workbench enregistre ses fichiers d’état.
title: Mode de traitement du journal.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Mode de traitement du journal.cfg{#log-processing-mode-cfg}

Le fichier de configuration Mode de traitement du journal.cfg vous permet de suspendre le traitement des données dans un jeu de données, de spécifier des sources hors ligne ou de spécifier la fréquence à laquelle le serveur Data Workbench enregistre ses fichiers d’état.

Apporter des modifications au fichier [!DNL Log Processing Mode.cfg], y compris ajouter ou supprimer des sources, ne provoque pas le retraitement des données.

**Pour modifier le fichier Log Processing Mode.cfg d’un profil de jeu de données**

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la balise [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu.

   >[!NOTE]
   >
   >Si le fichier [!DNL Log Processing Mode.cfg] ne se trouve pas dans le répertoire du profil souhaité, vous devez copier ce fichier du répertoire de base de l’ordinateur du serveur Data Workbench dans le répertoire du profil.

   Pour plus d’informations sur l’ouverture et l’utilisation de [!DNL Profile Manager,], consultez le *Guide de l’utilisateur du Data Workbench*.

1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier de configuration, puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre de configuration s’affiche.
1. Editez les paramètres du fichier de configuration à partir du tableau suivant comme guide.

   >[!NOTE]
   >
   >Certains paramètres du fichier [!DNL Log Processing Mode.cfg] portent des noms qui incluent [!DNL Fast Input] ou [!DNL Fast Merge]. [!DNL Fast Input]fait référence à la phase de traitement du journal de la construction du jeu de données et est responsable d’environ la moitié du temps total de traitement du jeu de données. [!DNL Fast Merge] fait référence à la phase de transformation de la construction du jeu de données uniquement lorsqu’elle est précédée par le traitement du journal. [!DNL Fast Merge] ne se produit pas lors d’une retransformation résultant de la modification d’un  [!DNL Transformation Dataset Configuration] fichier. Comme [!DNL Fast Input], [!DNL Fast Merge] est également responsable d’environ la moitié du temps de traitement du jeu de données.

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
      <td colname="col2"> <p>Paramètre d’optimisation qui affecte l’efficacité de la transformation des données. La valeur par défaut est 128000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rapport de décision d’entrée rapide </td> 
      <td colname="col2"> <p>Paramètre de réglage qui spécifie le rapport entre le nombre total d’octets de journal non lus auquel le système passe en mode <span class="wintitle"> Entrée rapide</span> (puis <span class="wintitle"> Fusion rapide</span>) au lieu de traiter les données en temps réel. </p> <p> La valeur par défaut est 200, ce qui signifie que le système passe en mode <span class="wintitle"> Entrée rapide</span> à partir du mode temps réel lorsque les données de journal non lues se situent à 1/200e du total des données. Un taux de décision plus élevé rend le système plus facile à passer en mode <span class="wintitle"> Entrée rapide</span>, tandis qu’un taux plus faible le rend moins susceptible d’entrer en mode <span class="wintitle"> Entrée rapide</span>. </p> <p> <p>Remarque : La définition du paramètre sur 0 empêche le système d’entrer en mode <span class="wintitle"> Entrée rapide</span> , même pour le traitement initial. La définition du paramètre sur 1.1 permet au système d’entrer <span class="wintitle"> une entrée rapide</span> lors du traitement initial, mais pas pour un traitement ultérieur. Adobe ne recommande pas d'utiliser des valeurs comprises entre 0 et 1.1. Pour plus d'informations sur la définition de ce paramètre, contactez l'Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Octets FIFO d’entrée rapide </td> 
      <td colname="col2"> <p>Paramètre d’optimisation qui équilibre l’utilisation de la mémoire et les performances du système lors du traitement des données. La valeur par défaut est 120000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Octets de mémoire tampon de fusion rapide </td> 
      <td colname="col2"> <p>Paramètre d’optimisation qui équilibre l’utilisation de la mémoire et les performances du système lors du traitement des données. La valeur par défaut est 128000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Sources hors ligne </td> 
      <td colname="col2"> <p>Masque de la source du journal hors ligne. </p> <p> <b> Pour spécifier une source hors ligne</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Sources hors ligne</span>, puis cliquez sur <span class="uicontrol"> Ajouter </span> &gt; <span class="uicontrol"> Source</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Dans le paramètre de la nouvelle source, saisissez le masque de la séquence du journal. Pour les sources de journal de Capteur avec des noms de fichier au format YYYYMMDD-<i>SENSORID</i>.vsl, le masque est <i>SENSORID.SENSORID</i> sensible à la casse. Pour les sources de journal des fichiers journaux, le masque est la chaîne extraite par le <span class="wintitle"> modèle de masque</span>. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Fichiers journaux</a>. </li> 
      </ul> </p> <p> L’ajout ou la suppression de sources à partir des sources hors ligne n’entraîne pas le retraitement du jeu de données. </p> <p> À partir du moment, les mesures sont conservées pour le traitement des sources en ligne du profil. Lorsque la source hors ligne est de nouveau en ligne, le traitement des fichiers journaux entrants pour cette source reprend. </p> <p> Chaque fois qu’une source revient en ligne, vous devez la supprimer des sources hors ligne. Si vous ne le faites pas, le serveur Data Workbench traite la source comme une source en ligne et met à jour le à partir du moment où la source envoie les données. Si la source est à nouveau hors ligne, les mesures À partir du moment s’arrêtent. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> En pause </td> 
      <td colname="col2"> Vrai ou faux. Si la valeur est true, les nouvelles données ne sont pas traitées dans le jeu de données. La valeur par défaut est false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Délai en temps réel </td> 
      <td colname="col2"> Durée en secondes pendant laquelle le serveur Data Workbench attend entre les intervalles de traitement des données dans le jeu de données. Lorsque cette valeur est définie sur zéro, le système tente de suivre les données entrantes en temps réel. La valeur par défaut est zéro (0), mais vous pouvez augmenter cette valeur pour réduire la charge du processeur. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Octets FIFO en temps réel </td> 
      <td colname="col2"> <p>La quantité de mémoire en octets utilisée pour stocker les données en attente de traitement dans le jeu de données. Vous devrez peut-être modifier cette valeur en fonction du nombre de secondes spécifié pour le délai en temps réel. La valeur par défaut est 16000000. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervalle de sauvegarde (sec) </td> 
      <td colname="col2"> <p>Fréquence à laquelle le serveur Data Workbench enregistre ses fichiers d’état. La valeur par défaut est 3600. </p> <p> <p>Remarque :  Vous ne devez pas modifier cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Lors de l’édition du fichier [!DNL Log Processing Mode.cfg] dans une fenêtre Data Workbench, vous pouvez utiliser des raccourcis clavier pour les fonctions d’édition de base, notamment couper (Ctrl+x ), copier (Ctrl+c), coller (Ctrl+v ), annuler (Ctrl+z ), rétablir (Ctrl+Maj+z ), sélectionner une section (clic+glisser) et tout sélectionner (Ctrl+a ). En outre, vous pouvez utiliser les raccourcis pour copier et coller le texte d’un fichier de configuration ( [!DNL .cfg]) vers un autre.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
