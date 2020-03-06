---
description: Procédure de démarrage d’Insight Server et d’enregistrement simultané en tant que service Microsoft Windows.
solution: Insight
title: Enregistrement d’Insight Server en tant que service Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Enregistrement d’Insight Server en tant que service Windows{#registering-insight-server-as-a-windows-service}

Procédure de démarrage d’Insight Server et d’enregistrement simultané en tant que service Microsoft Windows.

>[!NOTE]
>
>Lorsque vous démarrez [!DNL Insight Server] pour la première fois, il se connecte automatiquement au serveur de licences Adobe pour enregistrer votre certificat numérique. Pour réussir le processus d’enregistrement, votre ordinateur doit être connecté à Internet lorsque vous exécutez les étapes suivantes.

**Pour démarrer[!DNL Insight Server]et l&#39;enregistrer en tant que service Windows**

1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier dans lequel vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\bin]

1. A l’invite de commande, exécutez la commande suivante pour démarrer [!DNL Insight Server] et enregistrer simultanément l’exécution en tant que service sous Microsoft Windows :

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Pour vérifier que [!DNL Insight Server] l’exécution est correcte, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Cette séquence de commandes peut varier selon la version de Windows utilisée.

   1. Dans la liste des services, recherchez l’entrée correspondant **[!DNL Adobe Insight Server]** et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
   1. Fermez le panneau de configuration Services.

1. Pour vérifier si [!DNL Insight Server] des erreurs ont eu lieu au démarrage, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Cette séquence de commandes peut varier selon la version de Windows utilisée.

   1. Dans le volet gauche de la [!DNL Event Viewer] fenêtre, sélectionnez le **[!UICONTROL Application]** journal.
   1. Dans le volet de droite, recherchez des événements avec &quot;Adobe&quot; dans la [!DNL Source] colonne.
   1. Si vous trouvez une erreur de &quot;Adobe&quot;, cliquez deux fois sur l’erreur pour afficher la [!DNL Event Properties] fenêtre. Cette fenêtre fournit des informations détaillées sur l’erreur.

1. Lorsque vous avez terminé d’examiner le [!DNL Applications] journal, fermez l’Observateur d’événements.

Vous avez terminé l&#39;installation de [!DNL Insight Server]. [!DNL Insight Server] est conçue pour fonctionner en continu. Si vous redémarrez l’ordinateur, [!DNL Insight Server] redémarre automatiquement. Si vous devez démarrer et arrêter [!DNL Insight Server] manuellement, vous pouvez le faire à l’aide du panneau de configuration Services de Windows. Comme décrit dans la section suivante, vous pouvez éventuellement configurer [!DNL Insight Server] le service pour qu’il redémarre automatiquement périodiquement.

## Configuration du service à redémarrer automatiquement {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] est conçue pour continuer à fonctionner sans interruption. Il est généralement arrêté ou démarré uniquement lorsque vous effectuez des tâches peu fréquentes, telles que des mises à niveau logicielles ou des modifications de certificat, ou en cas de certaines erreurs système. Il n&#39;est pas nécessaire d&#39;arrêter ou de redémarrer le [!DNL Insight Server] service pendant le fonctionnement normal du système; toutefois, vous pouvez configurer le service pour qu’il redémarre périodiquement (tous les jours, toutes les semaines ou tous les mois) afin, par exemple, d’effacer les messages d’événement.

**Pour configurer le[!DNL Insight Server]service de sorte qu’il redémarre automatiquement**

1. Accédez au [!DNL Components] dossier du répertoire dans lequel vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Utilisez un éditeur de texte tel que le Bloc-notes pour créer un nouveau fichier appelé [!DNL ScheduledRestart.cfg].
1. Entrez le texte suivant dans le [!DNL ScheduledRestart.cfg] fichier :

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Pour cette valeur... </th> 
      <th colname="col2" class="entry"> Spécifiez les </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Mois JJ, AAAA HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Heure à laquelle vous souhaitez que <span class="keyword"> Insight Server </span> soit redémarré pour la première fois. </p> <p>Exemple : 13 août 2013 22:30:00 EST </p> <p> <p>Remarque :  Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur l’heure du système s’il n’est pas spécifié. Si vous souhaitez mettre en oeuvre l’heure d’été ou une stratégie similaire de changement d’horloge, vous devez enregistrer le fichier <span class="filepath"> .dst </span> contenant les règles appropriées sur l’Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> machine. Pour obtenir la liste des abréviations de fuseau horaire prises en charge et des informations sur l’implémentation de l’heure d’été, voir Codes de <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> fuseau horaire </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequency</i> </td> 
      <td colname="col2"> <p>L’une des valeurs suivantes : 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E"> mois </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C"> semaine </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902"> jour </li> 
       </ul> </p> <p>Pour indiquer la fréquence à laquelle vous souhaitez que <span class="keyword"> Insight Server </span> soit redémarré après l’heure initiale spécifiée dans Heure de début. </p> <p>Par exemple, si vous souhaitez que <span class="keyword"> Insight Server </span> redémarre une fois par semaine, définissez cette valeur sur "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   Vérifiez que le [!DNL ScheduledRestart.cfg] fichier se trouve dans le [!DNL Components] dossier du répertoire dans lequel vous avez installé [!DNL Insight Server].
