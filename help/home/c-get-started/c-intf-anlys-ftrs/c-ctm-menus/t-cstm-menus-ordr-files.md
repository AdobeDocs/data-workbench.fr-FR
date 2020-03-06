---
description: Vous pouvez personnaliser l’aspect de n’importe quel menu en modifiant le fichier order.txt associé à ce menu.
solution: Analytics
title: Personnalisation d’un menu à l’aide de fichiers order.txt
topic: Data workbench
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personnalisation d’un menu à l’aide de fichiers order.txt{#customize-a-menu-using-order-txt-files}

Vous pouvez personnaliser l’aspect de n’importe quel menu en modifiant le fichier order.txt associé à ce menu.

Les étapes de cette section s&#39;appliquent à tous les types de menus.

**Pour modifier le fichier order.txt afin de personnaliser un menu**

1. Dans la [!DNL Profile Manager]colonne Nom *du* profil, cliquez avec le bouton droit de la souris sur la coche du [!DNL order.txt] fichier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du [!DNL order.txt] fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Le [!DNL order.txt] fichier s’affiche.

   ![Infos sur l’étape](assets/cfg_ordertxt.png)

1. (Facultatif) Ajoutez ou modifiez le paramètre [Inclusif] ou [Exclusif] en haut du fichier, le cas échéant. Ce paramètre détermine si les éléments non répertoriés dans le [!DNL order.txt] fichier mais présents dans le [!DNL Profile Manager] fichier sont répertoriés dans le menu. Les options disponibles sont les suivantes :

   * **[Inclusif]:**Il s’agit du paramètre par défaut. Ce paramètre indique que les options de menu qui ne sont pas spécifiées dans le[!DNL order.txt]fichier sont répertoriées dans la partie inférieure du menu par ordre alphabétique. Par exemple, si le[!DNL Profile Manager]contenu contient un élément de profil en plus de ceux répertoriés dans la[!DNL order.txt]section ci-dessus, le profil s’affiche sous Données.

   * **[Exclusif]:**Ce paramètre entraîne l’exclusion des options de menu qui ne sont pas spécifiées dans le[!DNL order.txt]fichier du menu. Par exemple, si le[!DNL Profile Manager]contenu contient un élément Profil en plus de ceux répertoriés dans le[!DNL order.txt]précédent, le profil ne s’affichera nulle part dans le menu.

   * **blank:** Si aucun paramètre [Inclusif] ou [Exclusif] n’apparaît en haut du fichier, les Outils de données affichent les options de menu comme si le paramètre était [Inclusif].

1. Effectuez une ou plusieurs des étapes suivantes :

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Pour effectuer cette tâche... </th> 
    <th colname="col2" class="entry"> Procédez comme suit... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Réorganiser les éléments de menu </p> </td> 
    <td colname="col2"> <p>Entrez les noms des éléments dans l’ordre dans lequel ils doivent apparaître dans les Outils de données. </p> <p>Par exemple, tant que chaque nom d’élément de menu correspond à son nom de fichier ou de dossier correspondant, ce qui suit entraîne<b> l’affichage</b> d’abord de l’option Ajouter une table <b>, puis de l’option</b>Ajouter une visualisation <b>,</b>Ajouter une légende <b>etAjouter une note en dernier.</b> </p> <p><b>Ajouter un tableau </b> </p> <p><b>Ajouter une visualisation </b> </p> <p><b>Ajouter une légende </b> </p> <p><b>Ajouter une remarque </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Renommer un élément de menu </p> </td> 
    <td colname="col2"> <p>Renommez le fichier ou le dossier correspondant dans le Gestionnaire <span class="wintitle"> de</span>profils, puis modifiez le nom de l’élément dans le fichier <span class="filepath"> .txt</span> . </p> <p>Par exemple, pour renommer l’option Ajouter une annotation à la nouvelle annotation, renommez le dossier Ajouter une annotation dans le Gestionnaire <span class="wintitle"> de</span> profils en Nouvelle annotation, puis renommez l’élément Ajouter une annotation dans le fichier <span class="filepath"> .txt</span> en Nouvelle annotation. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Masquer un élément de menu </p> </td> 
    <td colname="col2"> <p>Pour masquer l’élément de menu sans supprimer l’élément lui-même, saisissez un signe moins (-) au début de son nom. </p> <p>Par exemple, l’option <span class="wintitle"> Ajouter une annotation</span> n’apparaît pas dans le menu. </p> <p>Ajouter une légende </p> <p>-Ajouter une annotation </p> <p>Pour afficher à nouveau l’option de menu masquée, il vous suffit de supprimer le signe moins (-) ou d’utiliser le paramètre Tout afficher dans le fichier <span class="filepath"> Insight.cfg</span> , voir Paramètres <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> de configuration</a>Insight. </p> <p>Vous pouvez également masquer les éléments de menu à l’aide des méthodes suivantes : 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Le paramètre Afficher dans un fichier <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span>ou <span class="filepath"> .dim</span> masque les filtres, les mesures et dimensions dérivées et les dimensions étendues de leurs menus respectifs. Lors de l’utilisation de cette option, l’élément n’est pas répertorié dans le menu, mais il figure toujours dans le profil et peut être utilisé. </p> <p>Pour utiliser ce paramètre pour masquer les filtres et les mesures et dimensions dérivées, ajoutez la ligne suivante à la fin du fichier <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>ou <span class="filepath"> .filter</span> : </p> <p><span class="filepath"> show = bool : false</span> </p> <p>Pour utiliser ce paramètre pour masquer les dimensions étendues, voir le chapitre 10 du Guide <i>de configuration des jeux de</i> données pour obtenir des instructions. </p> <p>Vous pouvez afficher temporairement les éléments masqués à l’aide de cette méthode en définissant le paramètre Tout afficher dans le fichier <span class="filepath"> Insight.cfg</span> . Pour plus d’informations sur ce paramètre, voir Paramètres <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> de configuration</a>Insight. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Le paramètre Masqué du fichier <span class="filepath"> Transformation.cfg</span> ou de tout jeu de données inclus masque les dimensions étendues du menu de dimension. Lors de l’utilisation de cette option, l’élément n’est pas répertorié dans le menu, mais il figure toujours dans le profil et peut être utilisé. <p> <p>Remarque :  Lorsque vous masquez des dimensions étendues à l’aide de cette méthode, vous devez retransformer votre jeu de données pour que les dimensions soient masquées. </p> </p> <p>Vous pouvez afficher temporairement les éléments masqués à l’aide de cette méthode en définissant le paramètre Tout afficher dans le fichier <span class="filepath"> Insight.cfg</span> . Pour plus d’informations sur ce paramètre, voir Paramètres <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> de configuration</a>Insight. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Les fichiers sans octet masquent tout type d’élément dans un menu. Lorsque vous utilisez cette option, un fichier vide (zéro octet) masque la présence d’un fichier portant le même nom que celui contenant des données. Les outils de données traitent les fichiers à zéro octet comme s’ils n’existaient pas. Pour plus d’informations, voir <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Masquage des fichiers à l’aide de fichiers</a>vides (zéro octet). </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Suppression d’un élément de menu </p> </td> 
    <td colname="col2"> <p>Si ce fichier est configuré pour utiliser l'option [Exclusif], vous pouvez simplement supprimer l'élément de menu de ce fichier. L’élément lui-même est toujours dans le profil, mais il n’est pas répertorié dans le menu. </p> <p>Si ce fichier est configuré pour utiliser l'option [Inclusif], vous devez supprimer le nom de l'élément de menu de ce fichier et supprimer ou supprimer le fichier correspondant sur zéro octet pour supprimer l'élément du menu. </p> <p>Pour plus d’informations sur la suppression de fichiers, voir <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Suppression de fichiers de votre profil</a>de travail. Pour plus d’informations sur les fichiers à zéro octet, voir <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Masquage des fichiers à l’aide de fichiers</a>vides (zéro octet). </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ajouter un en-tête de groupe </p> </td> 
    <td colname="col2"> <p>Saisissez trois traits d’union avant et après le texte de titre que vous souhaitez afficher. </p> <p>Par exemple, le résultat suivant est un en-tête de groupe Gérer pour un ensemble d’éléments de menu associés. </p> <p>---Gérer--- </p> <p>Profil </p> <p>Jeu de données </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ajouter une ligne à des sections distinctes d'un menu </p> </td> 
    <td colname="col2"> <p>Tapez trois traits d’union à l’endroit où vous souhaitez qu’une ligne apparaisse. </p> <p>Par exemple, le résultat suivant est une ligne qui sépare Ajouter une annotation et Ajouter personnalisé. </p> <p>Ajouter une annotation </p> <p>--- </p> <p>Ajouter personnalisé </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Enregistrez et fermez le fichier.
1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche blanche du [!DNL order.txt] fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
