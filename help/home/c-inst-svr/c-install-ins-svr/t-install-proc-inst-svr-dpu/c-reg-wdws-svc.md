---
description: Procédure de démarrage d’Insight Server et d’enregistrement simultané en tant que service Microsoft Windows.
title: Enregistrement du serveur Insight en tant que service Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---

# Enregistrement du serveur Insight en tant que service Windows{#registering-insight-server-as-a-windows-service}

Procédure de démarrage d’Insight Server et d’enregistrement simultané en tant que service Microsoft Windows.

>[!NOTE]
>
>Lorsque vous démarrez [!DNL Insight Server] pour la première fois, il se connecte automatiquement au serveur de licences d’Adobe pour enregistrer votre certificat numérique. Pour que le processus d’enregistrement soit terminé, votre machine doit être connectée à Internet lorsque vous exécutez les étapes suivantes.

**Pour démarrer  [!DNL Insight Server] et l’enregistrer en tant que service Windows**

1. Ouvrez une invite de commande et accédez au sous-répertoire bin du dossier où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\bin]

1. A l’invite de commande, exécutez la commande suivante pour démarrer [!DNL Insight Server] et enregistrez-la simultanément pour l’exécuter en tant que service sous Microsoft Windows :

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Pour vérifier que [!DNL Insight Server] s’exécute correctement, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

   1. Dans la liste des services, recherchez l’entrée **[!DNL Adobe Insight Server]** et vérifiez que son état est Démarré et que son type de démarrage est Automatique.
   1. Fermez le panneau de configuration Services .

1. Pour vérifier si [!DNL Insight Server] a rencontré des erreurs au démarrage, cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Cette séquence de commandes peut varier en fonction de la version de Windows utilisée.

   1. Dans le volet de gauche de la fenêtre [!DNL Event Viewer], sélectionnez le journal **[!UICONTROL Application]**.
   1. Dans le volet de droite, recherchez les événements avec &quot;Adobe&quot; dans la colonne [!DNL Source].
   1. Si vous trouvez une erreur de &quot;Adobe&quot;, double-cliquez sur l&#39;erreur pour afficher la fenêtre [!DNL Event Properties]. Cette fenêtre fournit des informations détaillées sur l’erreur.

1. Lorsque vous avez terminé d’examiner le journal [!DNL Applications], fermez la visionneuse d’événements.

Vous avez terminé l’installation de [!DNL Insight Server]. [!DNL Insight Server] est conçu pour fonctionner en continu. Si vous redémarrez la machine, [!DNL Insight Server] redémarre automatiquement. Si vous devez démarrer et arrêter [!DNL Insight Server] manuellement, vous pouvez le faire à l’aide du panneau de configuration Services de Windows. Comme décrit dans la section suivante, vous pouvez éventuellement configurer le service [!DNL Insight Server] pour qu’il redémarre automatiquement périodiquement.

## Configuration du service à redémarrer automatiquement {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] est conçu pour continuer à fonctionner sans interruption. En règle générale, il est arrêté ou démarré uniquement lorsque vous effectuez des tâches peu fréquentes, telles que des mises à niveau de logiciels ou des modifications de certificat, ou en cas d’erreur système. Il n’est pas nécessaire d’arrêter ou de redémarrer le service [!DNL Insight Server] pendant le fonctionnement normal du système ; vous pouvez toutefois configurer le service pour qu’il redémarre périodiquement (tous les jours, toutes les semaines ou tous les mois) afin, par exemple, d’effacer les messages d’événement.

**Configuration du  [!DNL Insight Server] service pour le redémarrage automatique**

1. Accédez au dossier [!DNL Components] dans le répertoire où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Utilisez un éditeur de texte tel que Notepad pour créer un fichier appelé [!DNL ScheduledRestart.cfg].
1. Saisissez le texte suivant dans le fichier [!DNL ScheduledRestart.cfg] :

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
      <td colname="col2"> <p>Heure à laquelle vous souhaitez que <span class="keyword"> le serveur Insight </span> soit redémarré pour la première fois. </p> <p>Exemple : 13 août 2013 22:30:00 EST </p> <p> <p>Remarque :  Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur l’heure système s’il n’est pas spécifié. Si vous souhaitez implémenter l’heure d’été ou une stratégie de changement d’heure similaire, vous devez enregistrer le fichier <span class="filepath"> .dst </span> contenant les règles appropriées dans la machine Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>. Pour obtenir la liste des abréviations de fuseau horaire prises en charge et des informations sur l’implémentation de l’heure d’été, voir <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codes de fuseau horaire </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>fréquence</i> </td> 
      <td colname="col2"> <p>L’une des valeurs suivantes : 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C"> semaine </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>Pour indiquer la fréquence à laquelle vous souhaitez que <span class="keyword"> le serveur Insight </span> soit redémarré après l’heure initiale spécifiée dans l’heure de début. </p> <p>Par exemple, si vous souhaitez que <span class="keyword"> le serveur Insight </span> redémarre une fois par semaine, définissez cette valeur sur "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Enregistrez le fichier [!DNL ScheduledRestart.cfg].

   Vérifiez que le fichier [!DNL ScheduledRestart.cfg] se trouve dans le dossier [!DNL Components] du répertoire où vous avez installé [!DNL Insight Server].
