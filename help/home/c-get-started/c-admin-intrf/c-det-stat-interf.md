---
description: L’interface de statut détaillée est utile pour résoudre les erreurs ou d’autres problèmes liés aux ordinateurs du serveur Data Workbench.
title: Interface de statut détaillée
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Interface de statut détaillée{#detailed-status-interface}

{{eol}}

L’interface de statut détaillée est utile pour résoudre les erreurs ou d’autres problèmes liés aux ordinateurs du serveur Data Workbench.

Cela inclut les [!DNL Transform] les profils s’exécutant sur ces ordinateurs, ou [!DNL Report] ordinateurs qui sont des clients du serveur de Data Workbench. Vous pouvez accéder à [!DNL Master Server] et [!DNL Query Server Detailed Status] par le biais de la [!DNL Admin] . Pour accéder au [!DNL Detailed Status] pour d’autres ordinateurs, dans [!DNL Servers Manager], cliquez avec le bouton droit sur le noeud du serveur pour lequel vous souhaitez afficher l’état, puis cliquez sur **[!UICONTROL Detailed Status]**. Voir [Gestionnaire des serveurs](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Pour plus d’informations sur le serveur Data Workbench, voir *Guide d’installation et d’administration des produits serveur*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Pour mettre à jour les informations d’une [!DNL Detailed Status] , cliquez avec le bouton droit de la souris sur l’interface **[!UICONTROL Detailed Status]** titre et clic **[!UICONTROL Refresh]**.

Le tableau suivant répertorie les tâches qui peuvent être effectuées à l’aide de la variable [!DNL Detailed Status] .

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche.. </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour afficher chaque composant d’ordinateur et son état actuel </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du composant</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher la quantité de mémoire utilisée sur l’ordinateur </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État de la mémoire</span> &gt; <span class="uicontrol"> Chargement de l’espace de l’adresse</span>. </p> <p>Pour plus d’informations sur la surveillance de la charge de l’espace des adresses, voir <i>Guide d’installation et d’administration des produits serveur</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer si l’ordinateur est configuré pour utiliser le commutateur /3GB </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État de la mémoire</span> &gt; <span class="uicontrol"> Espace d’adresse du processus</span>. </p> <p>Si la variable <span class="wintitle"> Total</span> affiche plus de 3000000 Ko, votre ordinateur est configuré pour utiliser le commutateur /3GB. </p> <p>Pour plus d’informations sur le commutateur /3GB, voir la section <i>Guide d’installation et d’administration des produits serveur</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller la quantité d’espace disque et de mémoire utilisée pour stocker chaque dimension ainsi que celle utilisée pour stocker les noms de ses éléments </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Dimensions</span> &gt; <span class="uicontrol"> Utilisation du disque</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt; </i>ou <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Dimensions</span> &gt; <span class="uicontrol"> Utilisation de la mémoire</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i>. </p> <p>Le <span class="wintitle"> Utilisation du disque</span> Les champs indiquent le nom et la quantité d’espace disque (en Mo) nécessaires au stockage de chaque dimension. Un grand nombre d’utilisation de disque peut avoir un impact négatif sur les temps de requête, car le serveur du Data Workbench doit parcourir toutes les données pour terminer les requêtes associées. La réduction de l’utilisation du disque pour une dimension peut réduire le temps nécessaire à l’exécution des requêtes associées. </p> <p>Le <span class="wintitle"> Utilisation de la mémoire</span> les champs indiquent le nombre d’éléments dans chaque dimension et la quantité de mémoire nécessaire pour stocker la liste des noms d’éléments. Un grand nombre d’éléments peut avoir un impact négatif sur la quantité de mémoire utilisée lors d’une requête, car le serveur du Data Workbench doit lire chaque élément. La réduction du nombre d’éléments dans une dimension peut réduire le temps nécessaire à l’exécution des requêtes associées. </p> <p>Exemple : <code>+&nbsp;Performance
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
   <td colname="col1"> <p>Pour surveiller l’utilisation de l’unité centrale pour les étapes dans Traitement du journal et transformation </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation du processeur</span> &gt; <span class="uicontrol"> Traitement du journal</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i> ou <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation du processeur</span> &gt; <span class="uicontrol"> Transformation</span> &gt; &lt;<span class="uicontrol"> nom du profil</span>&gt;. </p> <p>Chacun de ces jeux de champs vous fournit l’utilisation de l’unité centrale (en secondes) pour chacune des étapes dans Traitement du journal et transformation. </p> <p>Exemple : <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Le temps nécessaire pour terminer une requête est généralement proportionnel à la taille totale de toutes vos dimensions. Après avoir examiné la taille de chaque dimension, vous pouvez évaluer si une dimension spécifique est suffisamment utile et utilisée assez souvent pour justifier le coût de performance de la dimension. Dans le cas contraire, vous pouvez supprimer la dimension dans la variable <span class="wintitle"> Gestionnaire de profil</span>.<p>Une dimension dont la liste de noms d’éléments est trop volumineuse (c’est-à-dire de plus de 128 Mo) peut entraîner des erreurs "Mémoire insuffisante" même si l’utilisation totale de l’espace d’adresse n’est pas proche de la limite. </p> <p>En outre, si vous utilisez une grappe de serveurs Data Workbench sans utiliser de normalisation centralisée, une dimension dont la liste de noms d’éléments est volumineuse a un impact important sur les budgets de mémoire d’envoi. Pour plus d’informations sur la normalisation centralisée, voir <i>Guide de configuration des jeux de données</i>. Si la quantité de mémoire requise pour stocker toutes les listes de noms d’éléments combinées est supérieure à 100 Mo sur tous les serveurs de la grappe, vous pouvez recevoir des erreurs "Envoi du budget de la mémoire dépassé" même lorsque l’activité de requête est faible. Par exemple, si vous utilisez une grappe de quatre serveurs de plus de 25 Mo sur chaque serveur pour stocker les listes de noms d’éléments, des erreurs peuvent s’afficher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller le temps passé dans le traitement et la transformation des journaux </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation du processeur</span> &gt; <span class="uicontrol"> Traitement du journal</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i> ou <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation du processeur</span> &gt; <span class="uicontrol"> Transformation</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i>. </p> <p>La consultation des champs de ces sections vous permet d’identifier les filtres et transformations qui peuvent avoir une incidence négative sur le temps nécessaire au traitement et à la transformation des journaux. Vous pouvez ensuite prendre des décisions de conception concernant des filtres et des transformations individuels avec des temps de traitement longs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller l’utilisation de l’espace disque et augmenter la vitesse de requête </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Champs de traitement du journal</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i>. </p> <p>Chaque élément de cette section correspond à un paramètre de la section <span class="filepath"> Log Processing.cfg</span> fichier . La vérification de ces champs vous permet de voir la quantité de mémoire utilisée par chaque paramètre. Vous pouvez ensuite prendre des décisions de conception concernant des éléments individuels qui sont assez volumineux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps écoulé du retraitement ou de la transformation précédente </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du traitement</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i> &gt; <span class="uicontrol"> Historique du mode de traitement</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Temps réel : temps pendant lequel le serveur du Data Workbench était disponible pour effectuer des requêtes. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrée rapide : cette fois plus la Fusion rapide est le temps total nécessaire au traitement du jeu de données. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fusion rapide : temps total nécessaire pour transformer le jeu de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour diagnostiquer les problèmes "à partir du moment" </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du traitement</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i> &gt; <span class="uicontrol"> À partir du moment</span> &gt; <span class="uicontrol"> Sources depuis</span>. </p> <p>L’examen de l’heure de chaque source peut vous aider à déterminer quelle(s) source(s) peut avoir une incidence négative sur l’heure de début globale. Vous pouvez ensuite résoudre les problèmes liés à ces sources particulières. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour estimer le temps nécessaire à l’exécution d’une requête </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Moteur d’exécution</span>. </p> <p>Vérification de la <span class="wintitle"> Heure de balayage des données</span> vous fournit une estimation du temps nécessaire à l’exécution d’une requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour répertorier tous les profils disponibles sur cet ordinateur et les détails sur leur statut </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Profils</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher l’état de réplication </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du composant</span>. </p> <p>Vérifiez l’état du composant Répliquer . Si la réplication est en cours d’exécution, OK s’affiche. Si le composant Répliquer a échoué, un message d’erreur s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher <span class="wintitle"> Serveur de rapports</span> état d’un <span class="keyword"> Rapport</span> ordinateur qui se connecte au serveur Data Workbench </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du serveur de rapports</span>. </p> <p>Cette section de la <span class="wintitle"> Statut détaillé</span> comprend une copie de la fonction <span class="filepath"> Report Server.cfg</span> fichier, informations sur le nombre de rapports en cours d’exécution (Tranche actuelle) et informations sur la dernière erreur (Dernière erreur) la plus récente. </p> <p>Pour les étapes de modification du <span class="filepath"> Report Server.cfg</span> , voir <i>Guide des rapports Data Workbench</i>. </p> <p> <p>Remarque : Si la variable <span class="wintitle"> État du serveur de rapports</span> n’apparaît pas dans la section <span class="wintitle"> Statut détaillé</span> , vous devrez peut-être configurer le serveur de Data Workbench à afficher. <span class="wintitle"> État du serveur de rapports</span>. Pour connaître les étapes, voir <i>Guide des rapports Data Workbench</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher les informations d’utilisation de la mémoire pour Transform </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État du traitement</span> &gt; <span class="uicontrol"> Transform</span>. </p> <p>Pour plus d’informations sur Transform, voir <i>Guide d’installation et d’administration des produits serveur</i> et le <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour enregistrer le <span class="wintitle"> Statut détaillé</span> en tant qu’interface <span class="filepath"> *.cfg</span> fichier pouvant être ouvert dans un éditeur de texte tel que Bloc-notes ou distribué à d’autres utilisateurs </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur le <span class="uicontrol"> Statut détaillé</span> titre et clic <span class="uicontrol"> Enregistrer la copie sous</span>. </p> <p>Remarque :  <p>Cliquez avec le bouton droit de la souris sur le <span class="uicontrol"> Statut détaillé</span> en-tête et clic <span class="uicontrol"> Enregistrer</span> to <i>nom du serveur</i>/Status/ ne fonctionne pas dans la variable <span class="wintitle"> Statut détaillé</span> . Le message d’erreur suivant s’affiche : </p> <p>Impossible d’enregistrer /Status/. 403 Forbidden </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher <span class="uicontrol"> Lignes par source de journal</span> metric </p> </td> 
   <td colname="col2"> <p>Si la mesure Lignes par source de journal doit être signalée dans le statut détaillé, l’administrateur du Data Workbench doit définir l’"ID de source de journal" et fournir un nom unique dans le fichier de traitement du journal du profil personnalisé.cfg. </p> </td> 
  </tr> 
 </tbody> 
</table>
