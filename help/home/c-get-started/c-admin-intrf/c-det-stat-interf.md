---
description: L’interface d’état détaillé est utile pour résoudre les erreurs ou d’autres problèmes liés aux ordinateurs du serveur Outils de données.
solution: Analytics
title: Interface d’état détaillé
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: fd3afa80250d5ae20b7758ba840fd4d436545cf2

---


# Interface d’état détaillé{#detailed-status-interface}

L’interface d’état détaillé est utile pour résoudre les erreurs ou d’autres problèmes liés aux ordinateurs du serveur Outils de données.

Cela inclut tout [!DNL Transform] s’exécutant sur ces ordinateurs ou [!DNL Report] les ordinateurs clients du serveur Outils de données. Vous pouvez accéder aux interfaces [!DNL Master Server] et aux [!DNL Query Server Detailed Status] interfaces via le [!DNL Admin] menu. Pour accéder à l&#39; [!DNL Detailed Status] interface d&#39;autres ordinateurs, dans la [!DNL Servers Manager]section, cliquez avec le bouton droit sur le noeud du serveur pour lequel vous souhaitez l&#39;état et cliquez sur **[!UICONTROL Detailed Status]**. Voir [Le Gestionnaire](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba)Des Serveurs.

Pour plus d’informations sur le serveur Outils de données, voir le Guide *d’installation et d’administration des produits* serveur.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Pour mettre à jour les informations dans une [!DNL Detailed Status] interface, cliquez avec le bouton droit de la souris sur l’ **[!UICONTROL Detailed Status]** en-tête et cliquez **[!UICONTROL Refresh]**.

Le tableau ci-dessous  la  de qui peut être terminée à l’aide de l’ [!DNL Detailed Status] interface.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette ... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour afficher chaque composant d'ordinateur et son état actuel </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État</span>du composant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher la quantité de mémoire utilisée sur l'ordinateur </p> </td> 
   <td colname="col2"> <p>Cliquez sur État <span class="uicontrol"> de la</span> mémoire &gt; Chargement <span class="uicontrol"> de l’espace</span>d’adressage. </p> <p>Pour plus d'informations sur la surveillance de la charge de l'espace d'adressage, consultez le Guide <i>d'installation et d'administration des produits</i>serveur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer si l'ordinateur est configuré pour utiliser le commutateur /3GB </p> </td> 
   <td colname="col2"> <p>Cliquez sur État <span class="uicontrol"> de la</span> mémoire &gt; Espace <span class="uicontrol"> d’adresse</span>du processus. </p> <p>Si le champ <span class="wintitle"> Total</span> affiche plus de 300 000 Ko, votre ordinateur est configuré pour utiliser le commutateur /3GB. </p> <p>Pour plus d'informations sur le commutateur /3GB, consultez le Guide <i>d'installation et d'administration des produits</i>serveur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller la quantité d’espace disque et de mémoire utilisée pour stocker chaque dimension ainsi que celle utilisée pour stocker les noms de ses éléments </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Dimensions</span> &gt; <span class="uicontrol"> Utilisation</span> disque &gt; <i>&lt;  nom&gt; ou Performance&gt; Dimensions&gt; Utilisationde la mémoire &gt;&lt;nomdu&gt;.<span class="uicontrol"></span></i><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><i><span class="uicontrol"></span></i> </p> <p>Les champs Utilisation <span class="wintitle"> du</span> disque indiquent le nom et la quantité d’espace disque (en Mo) nécessaires au stockage de chaque dimension. Un nombre élevé d’utilisation de disque peut avoir une incidence négative sur les  de temps, car le serveur Outils de données doit lire toutes les données pour terminer les  connexes. La réduction de l’utilisation du disque pour une dimension peut réduire le temps nécessaire pour terminer les  de connexes. </p> <p>Les <span class="wintitle"> champs Utilisation</span> de la mémoire indiquent le nombre d’éléments dans chaque dimension et la quantité de mémoire requise pour stocker le des noms d’éléments. Un grand nombre d’éléments peut avoir une incidence négative sur la quantité de mémoire utilisée au cours d’une  de, car le serveur Outils de données doit lire chaque élément. La réduction du nombre d’éléments d’une dimension peut réduire le temps nécessaire pour terminer les  de connexes. </p> <p>Exemple : <code>+&nbsp;Performance
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
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation</span> du processeur &gt; <span class="uicontrol"> Traitement</span> du journal &gt; <i>&lt;  nom&gt;ou Performances&gt; Utilisation du processeur &gt; Transformation&gt; &lt;nomdu&gt;.<span class="uicontrol"></span></i><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span> </p> <p>Chacun de ces ensembles de champs fournit l’utilisation de l’UC (en secondes) pour chacune des étapes du traitement du journal et de la transformation. </p> <p>Exemple : <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Le temps nécessaire pour terminer une  de est généralement proportionnel à la taille totale de toutes vos dimensions. Après avoir examiné la taille de chaque dimension, vous pouvez déterminer si une dimension particulière est suffisamment utile et utilisée assez souvent pour justifier le coût de performance de la dimension. Si ce n’est pas le cas, vous pouvez supprimer la dimension dans le <span class="wintitle"> Gestionnaire</span>de .<p>Une dimension dont le de noms d’élément est excessivement volumineux (c’est-à-dire de plus de 128 Mo) peut provoquer des erreurs "Mémoire insuffisante" même si l’utilisation totale de l’espace d’adresse n’est pas proche de la limite. </p> <p>En outre, si vous utilisez une grappe de serveurs Outils de données sans avoir recours à une normalisation centralisée, une dimension dont le de noms d’éléments est important a un impact significatif sur les budgets d’envoi de la mémoire. Pour plus d'informations sur la normalisation centralisée, consultez le Guide <i>de configuration des jeux de</i>données. Si la quantité de mémoire requise pour stocker tous les  de noms d’éléments combinés est supérieure à 100 Mo sur tous les serveurs de la grappe, vous pouvez recevoir des erreurs "Envoi du budget mémoire dépassé", même lorsque le  lede la mémoire est léger. Si, par exemple, vous disposez d’une grappe de quatre serveurs avec plus de 25 Mo sur chaque serveur utilisé pour stocker le  de noms d’élément, des erreurs peuvent s’afficher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller le temps passé dans le traitement des journaux et la transformation </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; <span class="uicontrol"> Utilisation</span> du processeur &gt; <span class="uicontrol"> Traitement</span> du journal &gt; <i>&lt;  nom&gt;ou Performance&gt; Utilisation du processeur &gt; Transformation&gt; &lt;nomdu&gt;.<span class="uicontrol"></span></i><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><i><span class="uicontrol"></span></i> </p> <p>L’examen des champs de ces sections vous permet d’identifier les  et transformations susceptibles d’affecter négativement le temps nécessaire au traitement et à la transformation des journaux. Vous pouvez ensuite prendre des décisions de conception concernant des  et des transformations individuelles avec des temps de traitement longs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour surveiller l'utilisation de l'espace disque et augmenter la vitesse de  du </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Performances</span> &gt; Champs <span class="uicontrol"> de traitement du</span> journal &gt; <i>&lt;<span class="uicontrol">  nom</span>du&gt;.</i> </p> <p>Chaque ligne de cette section correspond à un paramètre du fichier <span class="filepath"> Log Processing.cfg</span> . L’examen de ces champs vous permet de voir la quantité de mémoire utilisée par chaque paramètre. Vous pouvez ensuite prendre des décisions de conception concernant des éléments individuels assez volumineux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps écoulé du retraitement ou de la transformation précédents </p> </td> 
   <td colname="col2"> <p>Cliquez sur Etat <span class="uicontrol"> de</span> traitement &gt; <i>&lt;<span class="uicontrol">  nom</span>du&gt;</i> <span class="uicontrol"> &gt; Historique du mode de traitement.</span> </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Temps réel : temps pendant lequel le serveur Outils de données était disponible pour créer des  de. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrée rapide : cette fois, plus le temps de fusion rapide, correspond au temps total nécessaire au traitement du jeu de données. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fusion rapide : temps total nécessaire pour transformer le jeu de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour diagnostiquer les problèmes liés au délai </p> </td> 
   <td colname="col2"> <p>Cliquez sur Etat <span class="uicontrol"> de</span> traitement &gt; <i>&lt;<span class="uicontrol">  nom</span>du&gt;</i> <span class="uicontrol"> &gt; A partir du moment &gt; Sources de  en tant que de.</span><span class="uicontrol"></span> </p> <p>L'examen des heures d'utilisation de chaque source peut vous aider à déterminer la ou les source(s) susceptible(s) d'affecter négativement la date d'expiration globale. Vous pouvez alors résoudre les problèmes avec ces sources particulières. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour estimer la durée d’exécution d’un  en cours d’exécution </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Moteur</span>d’exécution. </p> <p>L’examen du champ Temps <span class="wintitle"> de balayage des</span> données vous donne une estimation du temps nécessaire à l’exécution d’un . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour  tous les disponibles sur cet ordinateur et des détails sur leur état </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour  l’état de la réplication </p> </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> État</span>du composant. </p> <p>Vérifiez l’état du composant Répliquer. Si la réplication est en cours d’exécution, OK s’affiche. Si le composant Répliquer a échoué, un message d’erreur s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour  l’état du serveur <span class="wintitle"> de</span> rapports pour un <span class="keyword"> ordinateur Report</span> se connectant au serveur Outils de données </p> </td> 
   <td colname="col2"> <p>Cliquez sur État <span class="uicontrol"> du serveur de</span>rapports. </p> <p>Cette section de l’interface État <span class="wintitle"> détaillé comprend une copie du fichier</span> Report Server.cfg <span class="filepath"></span> , des informations sur le nombre de rapports en cours d’exécution (Tranche actuelle) et des informations sur l’erreur la plus récente (Dernière erreur). </p> <p>Pour connaître les étapes de modification du fichier <span class="filepath"> Report Server.cfg</span> , consultez le Guide <i>des rapports des outils de</i>données. </p> <p> <p>Remarque : Si la section État <span class="wintitle"> du serveur de</span> rapports n’apparaît pas dans l’interface État <span class="wintitle"> détaillé, vous devrez peut-être configurer le serveur Outils de données pour afficher</span> l’état <span class="wintitle"></span>du serveur de rapports. Pour obtenir des instructions, consultez le Guide <i>des rapports des outils de</i>données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour des informations d’utilisation de la mémoire pour Transform </p> </td> 
   <td colname="col2"> <p>Cliquez sur Etat <span class="uicontrol"> de</span> traitement &gt; <span class="uicontrol"> Transformation</span>. </p> <p>Pour plus d’informations sur Transform, consultez le Guide <i>d’installation et d’administration des produits</i> serveur et le Guide <i>de configuration des jeux de</i>données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour enregistrer l’interface État <span class="wintitle"> détaillé sous la forme d’un fichier</span> *.cfg <span class="filepath"></span> pouvant être ouvert dans un éditeur de texte tel que le Bloc-notes ou distribué à d’autres utilisateurs </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur l’en-tête État <span class="uicontrol"> détaillé, puis cliquez sur</span> Enregistrer la copie sous <span class="uicontrol"></span>. </p> <p>Remarque :  <p>Le fait de cliquer avec le bouton droit de la souris sur l’en-tête <span class="uicontrol"> Etat</span> détaillé et de cliquer sur Enregistrer <span class="uicontrol"> dans le nom</span> /État/ <i></i><span class="wintitle"> serveur ne fonctionne pas dans l’interface État détaillé. </span> Le message d’erreur suivant s’affiche : </p> <p>Impossible d'enregistrer /Status/. 403 Interdit </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour des <span class="uicontrol"> lignes par mesure Source</span> du journal </p> </td> 
   <td colname="col2"> <p>Si la mesure Lignes par source de journal doit être signalée dans Etat détaillé, l’administrateur des outils de données doit définir l’"ID de source de journal" et fournir un nom unique dans le fichier Custom Log Processing.cfg. </p> </td> 
  </tr> 
 </tbody> 
</table>

