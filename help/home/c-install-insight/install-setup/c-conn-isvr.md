---
description: Après avoir installé votre logiciel Insight et votre certificat numérique, vous devez démarrer Insight et configurer sa connexion au serveur Insight.
title: Configuration de la connexion au serveur Insight
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Configuration de la connexion au serveur Insight{#configuring-the-connection-to-insight-server}

Après avoir installé votre logiciel Insight et votre certificat numérique, vous devez démarrer Insight et configurer sa connexion au serveur Insight.

>[!NOTE]
>
>Dans certains cas, la connexion à Insight Server a peut-être été préconfigurée par Adobe Consulting Services ou par votre administrateur système. Si tel est le cas, vous n’avez pas besoin d’effectuer cette tâche.

Lorsque vous démarrez Insight pour la première fois, il se connecte automatiquement au serveur de licences Adobe pour enregistrer votre certificat numérique. Pour réussir le processus d&#39;enregistrement, votre ordinateur doit être connecté à Internet lorsque vous exécutez les étapes suivantes.

>[!NOTE]
>
>Si vous avez déjà demandé, téléchargé et installé un certificat préverrouillé comme décrit dans [Téléchargement et installation du certificat](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)numérique, Insight ne tentera pas de se connecter au serveur de licences et vous ne recevrez pas d’erreur.

**Pour configurer la connexion au serveur Insight**

Lorsque vous travaillez dans un environnement organisé en grappes, Insight doit être configuré pour accéder au serveur maître Insight afin d’éviter des problèmes de synchronisation. Dans Insight, vous pouvez afficher des informations sur le traitement [!DNL Insight Servers] dans votre grappe à l’aide de l’option de [!DNL Related Servers] menu du gestionnaire des [serveurs](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Lancez Insight.
1. Sur la [!DNL Worktop], cliquez sur **[!UICONTROL Admin]**, puis **[!UICONTROL First Steps]**.

1. Cliquez sur la **[!UICONTROL Configure Connection to Servers]** vignette.

   Le [!DNL Servers Manager], le [!DNL Insight.cfg] fichier et les instructions de configuration de votre [!DNL Insight.cfg]fichier s’affichent.

1. Dans la [!DNL Insight.cfg] fenêtre, cliquez avec le bouton droit **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Remplissez ou modifiez les paramètres du serveur pour permettre à Insight d’accéder à votre serveur maître Insight. Pour obtenir des descriptions détaillées des paramètres du fichier Insight.cfg, voir Paramètres [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-insght-config-param.html)configuration.

   ![](assets/cfg_Workstation_AddServer.png)

1. Répétez les étapes 4 et 5 pour chaque serveur Insight sur lequel vous souhaitez configurer une connexion.
1. Pour enregistrer vos modifications de configuration, cliquez avec le bouton droit **[!UICONTROL Insight.cfg (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save as Insight.cfg]**.

   Insight tente de se connecter à l’ [!DNL Insight Server(s)] aide des paramètres que vous avez spécifiés. Si une connexion est établie, un noeud vert s’affiche dans la [!DNL Servers Manager] page comme illustré ci-dessous.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Vert :** Indique que la connexion au serveur Insight est active.
   * **Rouge clair :** Indique un problème potentiel avec le serveur, tel qu’une fuite sur le traitement du serveur, une utilisation élevée de la mémoire ou un manque d’espace disque.
   * **Rouge :** Indique que la connexion au serveur Insight n’est pas active.
   Si Insight ne parvient pas à se connecter à l’aide des paramètres spécifiés, un noeud rouge apparaît dans la [!DNL Servers Manager]. Si cela se produit, reportez-vous à la section Résolution des problèmes [de connexion](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Lorsque vous sélectionnez un profil à utiliser, les informations du profil (y compris les données associées et les espaces de travail ou visualisations spécifiques définis pour le profil) sont téléchargées sur votre ordinateur. Lorsque vous téléchargez chaque profil, Insight crée un dossier dans le répertoire d’installation à l’aide du nom du profil.

Par exemple, si vous sélectionnez un profil nommé Ventes, un dossier nommé Ventes s’affiche dans votre répertoire Insight. Ce dossier contient les mesures, dimensions, espaces de travail et visualisations définis dans le profil des ventes. Après le chargement initial du profil, le profil peut être utilisé lorsque vous travaillez hors ligne. Voir [Travail hors ligne et en ligne](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-off-on.html).

En outre, lorsque vous vous connectez pour la première fois à Insight Server à partir d’Insight, Insight Server crée les répertoires suivants dans le répertoire d’installation d’Insight.

* **[!DNL Trace]directory:**Dans le[!DNL Trace]répertoire se trouve le fichier journal Insight ([!DNL insight.log]). Lorsque la taille du[!DNL Insight.log]fichier atteint 100 Mo, le fichier est renommé[!DNL insight-1.log]. Si un fichier du nom[!DNL insight-1.log]existe déjà,[!DNL insight-1.log]est renommé[!DNL insight-2.log], etc., avec un maximum de[!DNL insight-9.log]. Le fichier[!DNL insight.log]contient toujours les informations les plus récentes du journal et[!DNL insight-max.log]contient la plus ancienne.

* **[!DNL User]directory:**Dans le[!DNL User]répertoire se trouvent des dossiers qui correspondent à chaque profil utilisé à ce jour, et dans chaque dossier de profil se trouvent des dossiers nommés[!DNL Work]et[!DNL Workspaces]. Le répertoire`User\*profile name*\Workspaces`est l’emplacement par défaut dans lequel les fichiers de l’espace de travail Insight sont enregistrés.`User\*profile name*\Work`est l’emplacement par défaut dans lequel les visualisations d’Insight et les autres tâches personnalisées effectuées par l’utilisateur d’Insight sont enregistrées.

Le tableau suivant répertorie les emplacements par défaut des composants fréquemment utilisés.

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Emplacement du répertoire </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualisations enregistrées </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>du nom</i>du profil\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espaces de <span class="wintitle"> travail enregistrés</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>nom</i>du<i>profil\Workspaces\</i>nomde l’onglet\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fichiers .png<span class="filepath"> enregistrés</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>du nom</i>du profil\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cache de données </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Fichier journal</span> Insight </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

Vous pouvez effectuer une recherche par nom de clé, type de clé ou valeur pour localiser rapidement une entrée afin de ne plus avoir à faire défiler des fichiers volumineux et étendus pour obtenir des informations imbriquées. Vous pouvez localiser les noms de dimension, les noms de serveur, etc. L’exemple suivant montre les correspondances d’une recherche sur le mappage des expressions.

![](assets/cfg_search.PNG)

Entrez une expression de recherche dans ce champ pour localiser les données. Selon la réussite d’une correspondance, la couleur du champ change. Les correspondances sont mises en surbrillance et les non-correspondances sont grisées. S’il n’y a aucune correspondance, l’arrière-plan du champ de recherche devient rouge. Lorsque vous appuyez sur Entrée, l’arborescence de configuration s’étend à tous les endroits où il y a une correspondance et s’effondre là où il n’y a pas de correspondance.

Vous pouvez également utiliser des expressions régulières dans le [!DNL Search] champ. Par exemple, vous pouvez utiliser re : [!DNL *zip.*]pour toute entrée contenant le mot &quot;zip&quot;.

Pour effacer une recherche, appuyez sur **[!UICONTROL Escape]**.
