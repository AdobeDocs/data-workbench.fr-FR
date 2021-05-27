---
description: Vous pouvez personnaliser l’aspect de n’importe quel menu en modifiant le fichier order.txt associé à ce menu.
title: Personnaliser un menu à l’aide de fichiers order.txt
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# Personnaliser un menu à l’aide de fichiers order.txt{#customize-a-menu-using-order-txt-files}

Vous pouvez personnaliser l’aspect de n’importe quel menu en modifiant le fichier order.txt associé à ce menu.

Les étapes de cette section s&#39;appliquent à tous les types de menus.

**Pour modifier le fichier order.txt afin de personnaliser un menu**

1. Dans la colonne [!DNL Profile Manager], dans la colonne *nom du profil*, cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL order.txt] et cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL order.txt] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le fichier [!DNL order.txt] s’affiche.

   ![Infos sur l’étape](assets/cfg_ordertxt.png)

1. (Facultatif) Ajoutez ou modifiez le paramètre [Inclusive] ou [Exclusive] en haut du fichier, le cas échéant. Ce paramètre contrôle si les éléments non répertoriés dans le fichier [!DNL order.txt] mais présents dans la balise [!DNL Profile Manager] sont répertoriés dans le menu. Les options incluent :

   * **[Inclus] :**  il s’agit du paramètre par défaut. Ce paramètre entraîne la liste, par ordre alphabétique, des éléments de menu qui ne sont pas spécifiés dans le fichier [!DNL order.txt]au bas du menu. Par exemple, si [!DNL Profile Manager] contenait un élément Profil en plus de ceux répertoriés dans la balise [!DNL order.txt] ci-dessus, Profile s’afficherait sous Données.

   * **[Exclusif] :** ce paramètre entraîne l’exclusion des éléments de menu qui ne sont pas spécifiés dans le  [!DNL order.txt] fichier du menu. Par exemple, si la balise [!DNL Profile Manager] contenait un élément Profil en plus de ceux répertoriés dans la balise [!DNL order.txt] ci-dessus, Profile ne s’afficherait nulle part dans le menu.

   * **vide :** si aucun paramètre  [] inclus ou  [] exclusif n’apparaît en haut du fichier, Data Workbench affiche les options de menu comme si le paramètre était  [inclus].

1. Effectuez une ou plusieurs des étapes suivantes :

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Pour effectuer cette tâche.. </th> 
    <th colname="col2" class="entry"> Procédez comme suit... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Réorganiser les éléments de menu </p> </td> 
    <td colname="col2"> <p>Saisissez les noms des éléments dans l’ordre dans lequel ils doivent apparaître dans Data Workbench. </p> <p>Par exemple, tant que chaque nom d’élément de menu correspond à son nom de fichier ou de dossier correspondant, l’occurrence suivante affichera<b> Ajouter le tableau</b>, puis <b>Ajouter la visualisation</b>, <b>Ajouter la légende</b> et <b>Ajouter la note</b> apparaîtra en dernier. </p> <p><b>Ajouter un tableau  </b> </p> <p><b>Ajouter une visualisation  </b> </p> <p><b>Ajouter une légende  </b> </p> <p><b>Ajouter une remarque </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Renommer un élément de menu </p> </td> 
    <td colname="col2"> <p>Renommez le fichier ou le dossier correspondant dans le <span class="wintitle"> Gestionnaire de profils</span>, puis modifiez le nom de l’élément dans le fichier <span class="filepath"> order.txt</span> . </p> <p>Par exemple, pour renommer Ajouter une annotation à une nouvelle annotation, renommez le dossier Ajouter une annotation dans le <span class="wintitle"> Gestionnaire de profils</span> en Nouvelle annotation, puis remplacez le nom de l’élément Ajouter une annotation dans le fichier <span class="filepath"> order.txt</span> par Nouvelle annotation. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Masquer un élément de menu </p> </td> 
    <td colname="col2"> <p>Pour masquer l’élément de menu, mais pas supprimer l’élément lui-même, saisissez un signe moins (-) au début de son nom. </p> <p>Par exemple, le résultat suivant : <span class="wintitle"> Ajouter une annotation</span> n’apparaît pas dans le menu. </p> <p>Ajouter une légende </p> <p>-Ajouter une annotation </p> <p>Pour afficher à nouveau l’élément de menu masqué, supprimez simplement le signe moins (-) ou utilisez le paramètre Afficher tout dans le fichier <span class="filepath"> Insight.cfg</span>, voir <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Paramètres de configuration Insight</a>. </p> <p>Vous pouvez également masquer les éléments de menu à l’aide des méthodes suivantes : 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Le paramètre Afficher dans un fichier <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span> ou <span class="filepath"> .dim</span> masque les filtres, les mesures et dimensions dérivées et les dimensions étendues de leurs menus respectifs. Lorsque vous utilisez cette option, l’élément n’est pas répertorié dans le menu, mais il est toujours dans le profil et peut être utilisé. </p> <p>Pour utiliser ce paramètre afin de masquer les filtres et les mesures et dimensions dérivées, ajoutez la ligne suivante à la fin du fichier <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> ou <span class="filepath"> .filter</span> : </p> <p><span class="filepath"> show = bool : false</span> </p> <p>Pour utiliser ce paramètre afin de masquer les dimensions étendues, reportez-vous au chapitre 10 du <i>Guide de configuration des jeux de données</i> pour obtenir des instructions. </p> <p>Vous pouvez afficher temporairement les éléments masqués à l’aide de cette méthode en définissant le paramètre Afficher tout dans le fichier <span class="filepath"> Insight.cfg</span> . Pour plus d’informations sur ce paramètre, voir <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Paramètres de configuration Insight</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Le paramètre Masqué du fichier <span class="filepath"> Transformation.cfg</span> ou de tout jeu de données inclus masque les dimensions étendues du menu Dimension. Lorsque vous utilisez cette option, l’élément n’est pas répertorié dans le menu, mais il est toujours dans le profil et peut être utilisé. <p> <p>Remarque :  Lorsque vous masquez des dimensions étendues à l’aide de cette méthode, vous devez retransformer votre jeu de données pour que les dimensions soient masquées. </p> </p> <p>Vous pouvez afficher temporairement les éléments masqués à l’aide de cette méthode en définissant le paramètre Afficher tout dans le fichier <span class="filepath"> Insight.cfg</span> . Pour plus d’informations sur ce paramètre, voir <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Paramètres de configuration Insight</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Les fichiers sans octet masquent n’importe quel type d’élément dans n’importe quel menu. Lorsque vous utilisez cette option, un fichier vide (zéro octet) masque la présence d’un fichier portant le même nom que celui contenant les données. Data Workbench traite les fichiers sans octet comme s’ils n’existaient pas. Pour plus d’informations, voir <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Masquage des fichiers à l’aide de fichiers vides (zéro octet)</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Supprimer un élément de menu </p> </td> 
    <td colname="col2"> <p>Si ce fichier est défini pour utiliser l’option [Exclusif], vous pouvez simplement supprimer l’élément de menu de ce fichier. L’élément lui-même figure toujours dans le profil, mais il n’est pas répertorié dans le menu. </p> <p>Si ce fichier est défini pour utiliser l’option [Inclus], vous devez supprimer le nom de l’élément de menu de ce fichier et supprimer ou supprimer le fichier correspondant de zéro octets pour le supprimer du menu. </p> <p>Pour plus d’informations sur la suppression de fichiers, voir <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Suppression de fichiers de votre profil de travail</a>. Pour plus d’informations sur les fichiers sans octet, voir <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Masquage des fichiers à l’aide de fichiers vides (zéro octet)</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ajout d’un en-tête de groupe </p> </td> 
    <td colname="col2"> <p>Saisissez trois tirets avant et après le texte de titre que vous souhaitez afficher. </p> <p>Par exemple, ce qui suit génère un en-tête de groupe Gérer pour un ensemble d’éléments de menu associés. </p> <p>---Gérer--- </p> <p>Profil </p> <p>Jeu de données </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ajouter une ligne pour séparer les sections d’un menu </p> </td> 
    <td colname="col2"> <p>Saisissez trois traits d’union dans lesquels vous souhaitez qu’une ligne s’affiche. </p> <p>Par exemple, la ligne suivante sépare Ajouter une annotation et Ajouter personnalisé. </p> <p>Ajouter une annotation </p> <p>— </p> <p>Ajouter personnalisé </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Enregistrez le fichier, puis fermez-le.
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit sur la coche blanche du fichier [!DNL order.txt] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
