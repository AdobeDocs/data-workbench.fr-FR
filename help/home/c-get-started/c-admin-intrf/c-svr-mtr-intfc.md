---
description: L'interface Server Monitor est utile pour le dépannage ou simplement le suivi des paramètres de performances des ordinateurs de serveur Data Workbench et des ordinateurs Report qui sont des clients d'ordinateurs de serveur Data Workbench.
title: Interface du moniteur de serveur
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Interface du moniteur de serveur{#server-monitor-interface}

L&#39;interface Server Monitor est utile pour le dépannage ou simplement le suivi des paramètres de performances des ordinateurs de serveur Data Workbench et des ordinateurs Report qui sont des clients d&#39;ordinateurs de serveur Data Workbench.

L’interface du Moniteur du serveur affiche soit un point vert, soit un point rouge en haut, à gauche du nom de l’ordinateur. Un point vert indique que l&#39;ordinateur fonctionne sans problème. Un point rouge indique qu’une ou plusieurs erreurs se sont produites sur l’ordinateur.

La partie inférieure de l&#39;interface Server Monitor liste l&#39;état de traitement de chacun des profils disponibles ainsi que les détails de performances de l&#39;ordinateur.

Pour plus d&#39;informations sur [!DNL Data Workbench servers], consultez le *Server Products Installation and Administration Guide*. Pour plus d&#39;informations sur [!DNL Report], consultez le *Guide des rapports du Data Workbench*.

**Pour ouvrir l’interface du moniteur de serveur**

* Dans le Gestionnaire de serveurs, cliquez avec le bouton droit de la souris sur le noeud du serveur de Data Workbench ou de l&#39;ordinateur [!DNL Report]. t

Cliquez sur **[!UICONTROL Server Monitor]** pour vue des détails sur un serveur ou sur **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** pour vue des détails sur un cluster de serveurs associés.

![](assets/vis_ServerMonitor.png)

L&#39;interface [!DNL Server Monitor]se met à jour automatiquement toutes les 10 secondes.

Le tableau suivant liste les tâches qui peuvent être exécutées à l&#39;aide de l&#39;interface [!DNL Server Monitor].

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour vérifier l'état de traitement du journal d'un profil </p> </td> 
   <td colname="col2"> <p>Vue du Profil <i>Profil</i> vecteur de nom. Dans l’exemple ci-dessus, vous pouvez vue le vecteur ExempleProfile du Profil pour vous assurer que le profil ExempleProfil est traité sur un serveur et que son traitement du journal est 100 % terminé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le temps nécessaire à l'ordinateur pour répondre aux demandes </p> </td> 
   <td colname="col2"> <p>Vue du champ de latence du sondage. Si cette valeur est supérieure à 1 000 ms, contactez les services d’assistance à l’Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour vue une estimation du temps qu'il faudra pour terminer la transformation ou l'interrogation </p> </td> 
   <td colname="col2"> <p>Vue du champ Durée du balayage (hh:mm:ss), qui n’est présent que lors de la transformation ou de l’interrogation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour déterminer le nombre actuel de connexions réseau à l'ordinateur </p> </td> 
   <td colname="col2"> <p>Vue de la dernière ligne des informations <span class="wintitle"> Server Monitor</span> de l'ordinateur. Dans l'exemple ci-dessus, vous voyez que 2 connexions réseau proviennent actuellement d'un ordinateur. </p> </td> 
  </tr> 
 </tbody> 
</table>
