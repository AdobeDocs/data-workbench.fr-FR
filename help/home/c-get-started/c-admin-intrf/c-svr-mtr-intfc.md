---
description: L’interface du moniteur de serveur est utile pour résoudre les problèmes ou simplement effectuer le suivi des paramètres de performances des ordinateurs des serveurs Outils de données et des ordinateurs des rapports qui sont des clients des ordinateurs des serveurs Outils de données.
solution: Analytics
title: Interface du moniteur de serveur
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interface du moniteur de serveur{#server-monitor-interface}

L’interface du moniteur de serveur est utile pour résoudre les problèmes ou simplement effectuer le suivi des paramètres de performances des ordinateurs des serveurs Outils de données et des ordinateurs des rapports qui sont des clients des ordinateurs des serveurs Outils de données.

L’interface du moniteur de serveur affiche un point vert ou rouge en haut, à gauche du nom de l’ordinateur. Un point vert indique que l&#39;ordinateur fonctionne sans problème. Un point rouge indique qu’une ou plusieurs erreurs se sont produites sur l’ordinateur.

La partie inférieure de l’interface du moniteur de serveur répertorie l’état de traitement de chacun des profils disponibles ainsi que les détails de performances de l’ordinateur.

Pour plus d’informations sur [!DNL Data Workbench servers]le serveur, consultez le Guide *d’installation et d’administration des produits* serveur. Pour plus d’informations sur [!DNL Report]cette solution, consultez le Guide *des rapports des outils de* données.

**Pour ouvrir l’interface du moniteur de serveur**

* Dans le Gestionnaire de serveurs, cliquez avec le bouton droit sur le noeud du serveur ou de l’ [!DNL Report] ordinateur des outils de données. t

Cliquez sur **[!UICONTROL Server Monitor]** pour afficher les détails sur un serveur ou sur **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** pour afficher les détails sur une grappe de serveurs associés.

![](assets/vis_ServerMonitor.png)

L’ [!DNL Server Monitor]interface est automatiquement mise à jour toutes les 10 secondes.

Le tableau suivant répertorie les tâches pouvant être exécutées à l’aide de l’ [!DNL Server Monitor] interface.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour vérifier l’état de traitement du journal d’un profil </p> </td> 
   <td colname="col2"> <p>Affichez le vecteur Nom du <i>profil</i> du profil. Dans l’exemple ci-dessus, vous verrez le vecteur Exemple de profil de profil pour vous assurer que les processus du profil Exemple de profil sur un serveur et son traitement du journal sont entièrement terminés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps nécessaire à l’ordinateur pour répondre aux demandes </p> </td> 
   <td colname="col2"> <p>Affichez le champ de latence du sondage. Si cette valeur est supérieure à 1 000 ms, contactez les services d’assistance Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher une estimation du temps nécessaire à la réalisation de la transformation ou de l’interrogation </p> </td> 
   <td colname="col2"> <p>Affichez le champ de temps de balayage (hh:mm:ss), qui n’est présent que lors de la transformation ou de l’interrogation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le nombre actuel de connexions réseau à l'ordinateur </p> </td> 
   <td colname="col2"> <p>Affichez la dernière ligne des informations du moniteur <span class="wintitle"> du</span> serveur de l’ordinateur. Dans l'exemple ci-dessus, vous voyez que 2 connexions réseau proviennent actuellement d'un ordinateur. </p> </td> 
  </tr> 
 </tbody> 
</table>

