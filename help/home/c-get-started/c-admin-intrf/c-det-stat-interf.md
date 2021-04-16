---
description: L’interface d’état détaillé est utile pour résoudre les erreurs ou d’autres problèmes liés aux ordinateurs du serveur Data Workbench.
title: Interface de statut détaillée
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Interface de statut détaillée{#detailed-status-interface}

L’interface d’état détaillé est utile pour résoudre les erreurs ou d’autres problèmes liés aux ordinateurs du serveur Data Workbench.

Cela inclut tous les profils [!DNL Transform] s&#39;exécutant sur ces ordinateurs, ou les ordinateurs [!DNL Report] qui sont clients du serveur Data Workbench. Vous pouvez accéder aux interfaces [!DNL Master Server] et [!DNL Query Server Detailed Status] via le menu [!DNL Admin]. Pour accéder à l&#39;interface [!DNL Detailed Status] d&#39;autres ordinateurs, dans [!DNL Servers Manager], cliquez avec le bouton droit de la souris sur le noeud du serveur pour lequel vous souhaitez vue l&#39;état et cliquez sur **[!UICONTROL Detailed Status]**. Voir [Gestionnaire de serveurs](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Pour plus d&#39;informations sur le serveur Data Workbench, consultez le *Guide d&#39;installation et d&#39;administration des produits serveur*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Pour mettre à jour les informations dans une interface [!DNL Detailed Status], cliquez avec le bouton droit de la souris sur l&#39;en-tête **[!UICONTROL Detailed Status]** et cliquez sur **[!UICONTROL Refresh]**.

Le tableau suivant liste les tâches qui peuvent être exécutées à l&#39;aide de l&#39;interface [!DNL Detailed Status].

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour afficher chaque composant d'ordinateur et son état actuel </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du composant</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher la quantité de mémoire utilisée sur l'ordinateur </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État de la mémoire</span> &gt; <span class="uicontrol"> Chargement de l'espace d'adressage</span>. </p> <p>Pour plus d'informations sur la surveillance de la charge de l'espace d'adressage, consultez le <i>Guide d'installation et d'administration des produits serveur</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer si l'ordinateur est configuré pour utiliser le commutateur /3GB </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État de la mémoire</span> &gt; <span class="uicontrol"> Espace d’adressage du processus </span>. </p> <p>Si le champ <span class="wintitle"> Total</span> affiche plus de 3000000 Ko, votre ordinateur est configuré pour utiliser le commutateur /3GB. </p> <p>Pour plus d'informations sur le commutateur /3GB, consultez le <i>Guide d'installation et d'administration des produits serveur</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller la quantité d'espace disque et de mémoire utilisée pour stocker chaque dimension ainsi que celle utilisée pour stocker les noms de ses éléments </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Dimensions</span> &gt; <span class="uicontrol"> Utilisation du disque</span> &gt; <i>"a7/&gt; nom du profil</span> </i>ou <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Dimensions&lt;a13/ &gt; <span class="uicontrol"> Utilisation de la mémoire</span> &gt; <i>"a17/&gt; nom du profil&lt;a18/"</i>.<span class="uicontrol"></span><span class="uicontrol"></span> </span></p> <p>Les champs <span class="wintitle"> Disk Usage</span> indiquent le nom et la quantité d'espace disque (en Mo) nécessaires au stockage de chaque dimension. Un grand nombre d'utilisation de disques peut avoir une incidence négative sur les temps de requête, car le serveur Data Workbench doit parcourir toutes les données pour terminer les requêtes associées. La réduction de l'utilisation du disque pour une dimension peut réduire le temps nécessaire à l'achèvement des requêtes connexes. </p> <p>Les champs <span class="wintitle"> Utilisation de la mémoire</span> indiquent le nombre d’éléments dans chaque dimension et la quantité de mémoire requise pour stocker la liste des noms d’éléments. Un grand nombre d'éléments peut avoir un impact négatif sur la quantité de mémoire utilisée pendant une requête, car le serveur Data Workbench doit lire chaque élément. La réduction du nombre d’éléments d’une dimension peut réduire le temps nécessaire à l’achèvement des requêtes connexes. </p> <p>Exemple : <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller l'utilisation de l'UC pour les étapes du traitement du journal et de la transformation </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation du processeur</span> &gt; <span class="uicontrol"> Traitement du journal</span> &gt; <i>"a7/&gt; nom du profil</span></i> ou <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation&lt;a1/ &gt; <span class="uicontrol"> Transformation</span> &gt; "a16/&gt; nom du profil&lt;a17/".<span class="uicontrol"></span><span class="uicontrol"></span> </span></p> <p>Chacun de ces champs vous fournit l’utilisation de l’UC (en secondes) pour chacune des étapes du traitement du journal et de la transformation. </p> <p>Exemple : <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Le temps nécessaire pour terminer une requête est généralement proportionnel à la taille totale de toutes vos dimensions. Après avoir examiné la taille de chaque dimension, vous pouvez déterminer si une dimension particulière est suffisamment utile et utilisée assez souvent pour justifier le coût de performances de la dimension. Dans le cas contraire, vous pouvez supprimer la dimension dans le <span class="wintitle"> Gestionnaire de Profils</span>.<p>Une dimension dont la liste des noms d’élément est excessivement grande (c’est-à-dire supérieure à 128 Mo) peut provoquer des erreurs "Mémoire insuffisante" même si l’espace d’adressage total n’est pas proche de la limite. </p> <p>En outre, si vous utilisez une grappe de serveurs Data Workbench sans recourir à une normalisation centralisée, une dimension dont la liste des noms d’éléments est importante a un impact significatif sur les budgets d’envoi de la mémoire. Pour plus d'informations sur la normalisation centralisée, consultez le <i>Guide de configuration des ensembles de données</i>. Si la quantité de mémoire requise pour stocker toutes les listes de noms d’élément combinées est supérieure à 100 Mo sur tous les serveurs de la grappe, vous risquez de recevoir des erreurs "Envoi du budget mémoire dépassé" même lorsque l’activité de la requête est faible. Par exemple, si vous disposez d’une grappe de quatre serveurs de plus de 25 Mo sur chaque serveur utilisé pour stocker les listes de noms d’élément, des erreurs peuvent s’afficher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller le temps passé dans le traitement des journaux et la transformation </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation du processeur</span> &gt; <span class="uicontrol"> Traitement du journal</span> &gt; <i>"a7/&gt; nom du profil</span></i> ou <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation&lt;a1/ &gt; <span class="uicontrol"> Transformation</span> &gt; <i>"a17/&gt; nom du profil&lt;a18/"</i>.<span class="uicontrol"></span><span class="uicontrol"></span> </span></p> <p>L'examen des champs de ces sections vous permet d'identifier les filtres et les transformations qui peuvent avoir une incidence négative sur le temps nécessaire au traitement et à la transformation des journaux. Vous pouvez ensuite prendre des décisions de conception concernant des filtres individuels et des transformations avec de longs délais de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller l'utilisation de l'espace disque et augmenter la vitesse de requête </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Champs de traitement du journal</span> &gt; <i>"a5/&gt; nom du profil&lt;a6/"</i>.<span class="uicontrol"></span> </p> <p>Chaque élément de cette section correspond à un paramètre du fichier <span class="filepath"> Log Processing.cfg</span>. La révision de ces champs vous permet de voir la quantité de mémoire utilisée par chaque paramètre. Vous pouvez ensuite prendre des décisions de conception concernant des éléments individuels assez volumineux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps écoulé du retraitement ou de la transformation précédente </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Etat de traitement</span> &gt; <i>"a3/&gt; nom du profil&lt;a4/"</i> &gt; <span class="uicontrol"> Historique du mode de traitement</span>.<span class="uicontrol"></span> </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Temps réel : temps pendant lequel le serveur Data Workbench était disponible pour créer des requêtes. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrée rapide : cette fois plus la fusion rapide est le temps total nécessaire au traitement du jeu de données. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fusion rapide : temps total nécessaire pour transformer le jeu de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour diagnostiquer les problèmes liés au "A partir du moment" </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Etat de traitement</span> &gt; <i>"a3/&gt; nom du profil&lt;a4/"</i> &gt; <span class="uicontrol"> A partir du moment</span> &gt; <span class="uicontrol"> Sources en tant que </span>.<span class="uicontrol"></span> </p> <p>L'examen des heures d'utilisation de chaque source peut vous aider à déterminer quelle(s) source(s) peut avoir une incidence négative sur le niveau global d'utilisation. Vous pouvez ensuite résoudre les problèmes liés à ces sources particulières. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour estimer la durée d'exécution d'une requête </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Moteur d'exécution</span>. </p> <p>L’examen du champ <span class="wintitle"> Temps de balayage des données</span> vous permet d’estimer le temps nécessaire à l’exécution d’une requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour liste de tous les profils disponibles sur cet ordinateur et des détails sur leur état </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Profils</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vers le statut de réplication de vue </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du composant</span>. </p> <p>Vérifiez l’état du composant Répliquer. Si la réplication est en cours d'exécution, OK s'affiche. Si le composant Répliquer a échoué, un message d’erreur s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>À la vue <span class="wintitle"> État du serveur de rapports</span> pour un ordinateur <span class="keyword"> Report</span> connecté au serveur Data Workbench </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du serveur de rapports</span>. </p> <p>Cette section de l'interface <span class="wintitle"> État détaillé</span> comprend une copie du fichier <span class="filepath"> Report Server.cfg</span>, des informations sur le nombre de rapports en cours d'exécution (Tranche actuelle) et des informations sur l'erreur la plus récente (Dernière erreur). </p> <p>Pour connaître les étapes de modification du fichier <span class="filepath"> Report Server.cfg</span>, consultez le <i>Guide des rapports du Data Workbench</i>. </p> <p> <p>Remarque : Si la section <span class="wintitle"> État du serveur de rapports</span> n'apparaît pas dans l'interface <span class="wintitle"> État détaillé</span>, vous devrez peut-être configurer le serveur de Data Workbench pour afficher <span class="wintitle"> État du serveur de rapports</span>. Pour connaître les étapes à suivre, consultez le <i>Guide des rapports des Data Workbench</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour vue des informations d’utilisation de la mémoire pour Transformer </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Etat de traitement</span> &gt; <span class="uicontrol"> Transformer</span>. </p> <p>Pour plus d'informations sur Transform, consultez le <i>Server Products Installation and Administration Guide</i> et le <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour enregistrer l'interface <span class="wintitle"> État détaillé</span> sous la forme d'un fichier <span class="filepath"> *.cfg</span> qui peut être ouvert dans un éditeur de texte tel que le Bloc-notes ou distribué à d'autres utilisateurs </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur l’en-tête <span class="uicontrol"> État détaillé</span> et cliquez sur <span class="uicontrol"> Enregistrer la copie sous</span>. </p> <p>Remarque :  <p>Le fait de cliquer avec le bouton droit sur l'en-tête <span class="uicontrol"> État détaillé</span> et de cliquer sur <span class="uicontrol"> Enregistrer</span> dans <i>nom du serveur</i>/État/ ne fonctionne pas dans l'interface <span class="wintitle"> État détaillé</span>. Le message d’erreur suivant s’affiche : </p> <p>Impossible d'enregistrer /Status/. 403 Interdit </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour la mesure <span class="uicontrol"> Lignes par source de journal</span> vue </p> </td> 
   <td colname="col2"> <p>Si la mesure Lignes par source de journal doit être signalée dans le statut détaillé, l'administrateur du Data Workbench doit définir l'"ID de source de journal" et fournir un nom unique dans le fichier Traitement du journal de Profil personnalisé.cfg. </p> </td> 
  </tr> 
 </tbody> 
</table>
