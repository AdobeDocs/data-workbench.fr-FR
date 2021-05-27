---
description: L’interface du moniteur de serveur est utile pour résoudre les problèmes ou simplement pour effectuer le suivi des paramètres de performances des ordinateurs de serveur de Data Workbench et des ordinateurs de rapport qui sont des clients d’ordinateurs de serveur de Data Workbench.
title: Interface du moniteur de serveur
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Interface du moniteur de serveur{#server-monitor-interface}

L’interface du moniteur de serveur est utile pour résoudre les problèmes ou simplement pour effectuer le suivi des paramètres de performances des ordinateurs de serveur de Data Workbench et des ordinateurs de rapport qui sont des clients d’ordinateurs de serveur de Data Workbench.

L’interface du moniteur de serveur affiche un point vert ou rouge en haut à gauche du nom de l’ordinateur. Un point vert indique que l&#39;ordinateur fonctionne sans problème. Un point rouge indique qu’une ou plusieurs erreurs se sont produites sur l’ordinateur.

La partie inférieure de l’interface du moniteur de serveur répertorie l’état de traitement de chacun de vos profils disponibles, ainsi que les détails de performances de l’ordinateur.

Pour plus d’informations sur [!DNL Data Workbench servers], consultez le *Guide d’installation et d’administration des produits serveur*. Pour plus d’informations sur [!DNL Report], consultez le *Guide du Data Workbench de rapports*.

**Pour ouvrir l’interface du moniteur de serveur**

* Dans le Gestionnaire de serveurs, cliquez avec le bouton droit sur le noeud du serveur de Data Workbench ou de l’ordinateur [!DNL Report]. t

Cliquez sur **[!UICONTROL Server Monitor]** pour afficher les détails sur un serveur, ou cliquez sur **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** pour afficher les détails sur un cluster de serveurs associés.

![](assets/vis_ServerMonitor.png)

L’interface [!DNL Server Monitor]se met automatiquement à jour toutes les 10 secondes.

Le tableau suivant répertorie les tâches pouvant être effectuées à l’aide de l’interface [!DNL Server Monitor].

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
   <td colname="col2"> <p>Affichez le vecteur de nom du profil <i>Profil</i>. Dans l’exemple ci-dessus, vous verrez le vecteur Exemple de profil pour vérifier que le profil Exemple de profil traite sur un serveur et que son traitement des journaux est entièrement terminé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps nécessaire à l’ordinateur pour répondre à des requêtes </p> </td> 
   <td colname="col2"> <p>Affichez le champ de latence du sondage. Si cette valeur est supérieure à 1 000 ms, contactez les services d’assistance Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher une estimation du temps nécessaire à la réalisation de la transformation ou de l’interrogation </p> </td> 
   <td colname="col2"> <p>Affichez le champ Heure de balayage (hh:mm:ss), qui n’est présent que lors de la transformation ou de l’interrogation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le nombre actuel de connexions réseau à l’ordinateur </p> </td> 
   <td colname="col2"> <p>Affichez la dernière ligne des informations <span class="wintitle"> Server Monitor</span> de l’ordinateur. Dans l’exemple ci-dessus, vous voyez que 2 connexions réseau proviennent actuellement d’un seul ordinateur. </p> </td> 
  </tr> 
 </tbody> 
</table>
