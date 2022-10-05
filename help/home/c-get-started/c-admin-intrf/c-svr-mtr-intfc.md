---
description: L’interface du moniteur de serveur est utile pour résoudre les problèmes ou simplement pour effectuer le suivi des paramètres de performances des ordinateurs de serveur de Data Workbench et des ordinateurs de rapport qui sont des clients d’ordinateurs de serveur de Data Workbench.
title: Interface du moniteur de serveur
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%

---

# Interface du moniteur de serveur{#server-monitor-interface}

{{eol}}

L’interface du moniteur de serveur est utile pour résoudre les problèmes ou simplement pour effectuer le suivi des paramètres de performances des ordinateurs de serveur de Data Workbench et des ordinateurs de rapport qui sont des clients d’ordinateurs de serveur de Data Workbench.

L’interface du moniteur de serveur affiche un point vert ou rouge en haut à gauche du nom de l’ordinateur. Un point vert indique que l&#39;ordinateur fonctionne sans problème. Un point rouge indique qu’une ou plusieurs erreurs se sont produites sur l’ordinateur.

La partie inférieure de l’interface du moniteur de serveur répertorie l’état de traitement de chacun de vos profils disponibles, ainsi que les détails de performances de l’ordinateur.

Pour plus d’informations sur [!DNL Data Workbench servers], reportez-vous à la section *Guide d’installation et d’administration des produits serveur*. Pour plus d’informations sur [!DNL Report], reportez-vous à la section *Guide des rapports Data Workbench*.

**Pour ouvrir l’interface du moniteur de serveur**

* Dans le Gestionnaire de serveurs, cliquez avec le bouton droit sur le noeud du serveur Data Workbench ou [!DNL Report] ordinateur. t

Cliquez sur **[!UICONTROL Server Monitor]** pour afficher les détails d’un serveur, ou cliquez sur **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** pour afficher des détails sur un cluster de serveurs associés.

![](assets/vis_ServerMonitor.png)

Le [!DNL Server Monitor]est automatiquement mise à jour toutes les 10 secondes.

Le tableau suivant répertorie les tâches qui peuvent être effectuées à l’aide de la variable [!DNL Server Monitor] .

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche.. </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour vérifier l’état du traitement des logs d’un profil </p> </td> 
   <td colname="col2"> <p>Affichage du profil <i>Profil</i> Nom vectoriel. Dans l’exemple ci-dessus, vous verrez le vecteur Exemple de profil pour vérifier que le profil Exemple de profil traite sur un serveur et que son traitement des journaux est entièrement terminé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps nécessaire à l’ordinateur pour répondre à des requêtes </p> </td> 
   <td colname="col2"> <p>Affichez le champ de latence du sondage. Si cette valeur est supérieure à 1 000 ms, contactez les services d’assistance Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher une estimation du temps nécessaire à la réalisation de la transformation ou de l’interrogation </p> </td> 
   <td colname="col2"> <p>Afficher l’heure de balayage (hh:mm:s), qui n’est présent que lors de la transformation ou de l’interrogation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le nombre actuel de connexions réseau à l’ordinateur </p> </td> 
   <td colname="col2"> <p>Afficher la dernière ligne de l’ordinateur <span class="wintitle"> Surveillance du serveur</span> informations. Dans l’exemple ci-dessus, vous voyez que 2 connexions réseau proviennent actuellement d’un seul ordinateur. </p> </td> 
  </tr> 
 </tbody> 
</table>
