---
description: Une fois que vous avez défini votre objectif, vos détails d’hypothèse et d’expérience et créé votre contenu de test, vous devez configurer Sensor pour déployer l’expérience contrôlée.
solution: Analytics,Analytics
title: Configuration et déploiement de l’expérience
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Configuration et déploiement de l’expérience{#configuring-and-deploying-the-experiment}

Une fois que vous avez défini votre objectif, vos détails d’hypothèse et d’expérience et créé votre contenu de test, vous devez configurer Sensor pour déployer l’expérience contrôlée.

## Configuration du fichier de configuration de l&#39;expérience {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Pour configurer l&#39;expérience, vous devez compléter la feuille de calcul de configuration de l&#39;expérience fournie par l&#39;Adobe (nommée [!DNL TestExperiment.xls] par défaut). Ce fichier configure [!DNL Sensor] pour effectuer l&#39;expérience et il s&#39;agit de la version Excel du fichier texte que vous avez spécifiée dans [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

Ce fichier peut contenir des informations sur plusieurs expériences, qui peuvent s&#39;exécuter au même moment ou à des moments différents et utiliser différents groupes et pourcentages, mais ces expériences ne sont en aucune façon corrélées.

Les utilisateurs sont placés dans un groupe pour chaque expérience répertoriée dans le fichier configuré pour s’exécuter à ce stade.

>[!NOTE]
>
>Chaque expérience est indépendante de toutes les autres expériences. Les modifications que vous apportez à une expérience n&#39;affectent aucune autre expérience, et bien que les visiteurs puissent faire l&#39;objet de plusieurs expériences, les résultats ne se rapportent pas les uns aux autres. Si vous pensez qu&#39;il existe une corrélation entre les changements dans plusieurs expériences, vous devez créer une nouvelle expérience qui teste ces changements ensemble.

**Pour configurer votre expérience**

Vous devez compléter ce fichier avant le début de l&#39;expérience et ne pas modifier les informations pendant l&#39;expérience.

>[!NOTE]
>
>Toute expérience est rapidement invalide si la définition de l&#39;expérience change après le début de l&#39;expérience.

1. Si vous disposez d’un accès administrateur à vos serveurs Web ou d’applications, accédez au dossier d’installation [!DNL Sensor] sur n’importe quel ordinateur [!DNL Sensor] de votre grappe Web pour accéder au fichier [!DNL TestExperiment.xls]. Si vous ne disposez pas des droits d’administrateur, contactez votre gestionnaire de compte d’Adobe pour demander le fichier [!DNL TestExperiment.xls].

1. Ouvrez le fichier [!DNL TestExperiment.xls] (vous pouvez renommer ce fichier si vous le souhaitez) et renseignez les champs suivants :

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experiment </td> 
   <td colname="col2"> <p>Nom descriptif de l’expérience. Chaque nom d’expérience doit être unique et ne peut pas contenir d’espaces. </p> <p>Les noms des expériences sont utilisés lors de l'affichage des résultats des expériences dans <span class="keyword"> Insight </span>. Les noms apparaissent comme la première moitié des noms d’élément dans la dimension d’expérience contrôlée. La deuxième moitié du nom de l’élément est le nom du groupe figurant dans le champ Groupe de ce fichier. Chaque groupe est nommé au format suivant en utilisant le nom de l’expérience suivi du nom du groupe : </p> <p><i>Nom de l’expérience.Nom du groupe</i> </p> <p>Par exemple : <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Début </td> 
   <td colname="col2"> <p>Date et heure auxquelles l’expérience doit commencer. Si vous n’entrez aucune valeur, l’expérience commence immédiatement après le déploiement du fichier. </p> <p>Format : MM/JJ/AAAA H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Si vous quittez le début et arrêtez des heures vides, l'expérience s'exécute indéfiniment. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">Vous pouvez prédéfinir les heures de début et d'arrêt bien à l'avance ; par conséquent, vous pouvez configurer toutes vos expériences pour l'année suivante en même temps si vous le souhaitez. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">Les heures de début et d’arrêt sont basées sur l’heure système du serveur Web. Si cette horloge change pour quelque raison que ce soit, votre expérience peut début ou s'arrêter de façon inattendue. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Si vous souhaitez ajouter une expérience en tant qu'entrée de fichier de configuration mais que vous ne souhaitez pas que l'expérience s'exécute dans un avenir proche, vous pouvez commenter les informations de l'expérience en utilisant le signe numérique "#" ou définir des heures de début et d'arrêt dans le passé. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>Date et heure auxquelles l’expérience doit se terminer. Lorsque la date et l'heure d'arrêt se produisent, <span class="wintitle"> Capteur </span> arrête d'envoyer les valeurs de cookie identifiées comme un groupe de test aux URI de test et envoie tous les cookies aux URI de Population témoin. </p> <p>Format : MM/JJ/AAAA H:MM </p> <p>Consultez les notes du champ <span class="wintitle"> Début </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe </td> 
   <td colname="col2"> <p>Nom descriptif pour chaque groupe de visiteurs de l’expérience. Les noms de groupe ne peuvent pas contenir d'espaces. </p> <p>Les noms de groupe sont utilisés lors de l'affichage des résultats des expériences dans <span class="keyword"> Insight </span>. Pour plus d’informations, voir la description du champ Expérience. </p> <p>Une Population témoin peut être définie implicitement ou explicitement en fonction de la valeur saisie dans le champ Pourcentage. </p> <p> <p>Remarque :  Pour répondre au nombre de visiteurs requis pendant la période définie pour que l’expérience soit statistiquement valide, vous devrez peut-être diminuer le niveau de confiance ou augmenter la période. Par exemple, si votre période est de cinq jours, votre degré de confiance est de 98 % et que votre nombre de visiteurs requis dépasse le nombre prévu pour cette période, vous devez augmenter la période ou diminuer le niveau de confiance jusqu’à ce que le nombre de visiteurs attendus dépasse le nombre requis pour exécuter une expérience statistiquement valide. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pourcentage </td> 
   <td colname="col2"> <p>Pourcentage de visiteurs de site Web à inclure dans chaque groupe défini. Ces valeurs peuvent être exprimées en pourcentages ou en valeurs décimales. En outre, les deux valeurs doivent être supérieures ou inférieures à une. </p> <p>Par exemple : </p> <p>33,3 % et 66,7 % </p> <p>.99 et .01 </p> <p>Si la somme de tous les groupes est inférieure à 100, l’excédent non défini est associé par défaut à une Population témoin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL d’origine </td> 
   <td colname="col2"> <p>URI du contenu à mapper, suivi de $. Cette valeur est sensible à la casse. </p> <p>Format : index.asp$ </p> <p>Les URI d’origine peuvent être spécifiés à l’aide d’un signe dollar ($) à la fin de l’URI pour indiquer qu’une correspondance exacte du nom de fichier est requise. Par exemple, l'expression <span class="filepath"> /product/product_view.asp$ </span> correspond à cette page exacte uniquement, tandis que <span class="filepath"> /product </span> correspond à n'importe quelle page du répertoire <span class="filepath"> /product </span> et peut être utilisée pour remapper toute cette sous-arborescence. Les entrées d’URL d’origine qui ne spécifient pas le caractère $ à la fin du nom de fichier sont ignorées par l’expérience, sauf si le paramètre ExpPartialMatch a été défini sur "on". Pour plus d'informations sur ce paramètre, voir <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modification du paramètre ExpPartialMatch (facultatif) </a>. </p> <p>La fonctionnalité d’expérience contrôlée ignore toutes les chaînes de requête ajoutées à la racine URI. Par exemple, la page </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982  </span> n’est pas un URI valide, mais la page  <span class="filepath"> /product/product_view.asp  </span> est un URI valide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL remplacée </td> 
   <td colname="col2"> <p>URI du contenu alternatif. </p> <p>Format : index2.asp </p> <p>Consultez les notes du champ URL d’origine. </p> </td> 
  </tr> 
 </tbody> 
</table>

Voici un exemple de feuille de calcul [!DNL TextExperiment.xls] terminée :

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Ne modifiez pas les positions des colonnes dans la feuille de calcul.

Cet exemple indique que l&#39;expérience &quot;Nouvelle_page d&#39;accueil&quot; début le 1er juin 2006, se termine le 30 juin 2006 et contient une Population témoin avec 50 % des visiteurs et un groupe de test avec 50 % des visiteurs, qui voient un contenu différent pour un URI.

>[!NOTE]
>
>Bien que l&#39;exemple de fichier ci-dessus comporte une Population témoin explicite définie, il n&#39;est pas nécessaire de définir explicitement une Population témoin — l&#39;expérience crée automatiquement la Population témoin. Si la somme des pourcentages pour tous les groupes d’une expérience est inférieure à 100 %, une Population témoin implicite est attribuée aux utilisateurs qui ne font pas partie d’un des groupes explicites.

1. Pour insérer des commentaires afin de fournir des informations supplémentaires sur des expériences spécifiques, commencez la cellule par un signe dièse (#) et suivez vos commentaires. Les commentaires peuvent être insérés n’importe où dans le fichier.
1. Après avoir terminé les variables dans la feuille de calcul de configuration de l&#39;expérience, enregistrez les modifications, puis enregistrez le fichier au format texte délimité par des tabulations ( [!DNL *.txt]) en utilisant le nom que vous avez spécifié dans le paramètre ExpFile dans le fichier de configuration [!DNL Sensor]. Voir [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   Voici un exemple de fichier texte de configuration d’expérience :

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >En raison des onglets requis dans ce fichier, ne modifiez pas manuellement le fichier texte de configuration de l&#39;expérience. Si vous devez apporter des modifications au fichier, effectuez les modifications dans le fichier Excel de configuration de l’expérience et réenregistrez le fichier sous la forme d’un fichier texte délimité par des tabulations.

Si vous avez défini les heures de Début et d&#39;arrêt, il n&#39;y a aucune raison de supprimer une expérience du fichier de configuration de l&#39;expérience. Tenir à jour toutes vos expériences répertoriées dans le fichier de configuration de l&#39;expérience est en fait un bon moyen de conserver un enregistrement de la façon dont vous avez défini chacune de vos expériences.

## Déploiement du fichier de configuration et du contenu du test {#section-34ff29649f584b93bc6129b75084b37c}

Vous devez déployer le fichier de configuration de l&#39;expérience sur chaque ordinateur de votre grappe Web qui exécute [!DNL Sensor] et diffuse les pages impliquées dans l&#39;expérience. Vous pouvez le faire en utilisant une procédure manuelle ou votre système de gestion de contenu existant.

**Pour déployer votre contenu de test**

* Sur chaque application ou serveur Web exécutant [!DNL Sensor] qui diffuse les pages impliquées dans l’expérience, utilisez votre processus de publication existant pour déployer le contenu du test à l’emplacement approprié.

   Par exemple, si vous souhaitez publier la page du groupe de tests [!DNL index2.asp] dans le dossier de test de votre site Web ( [!DNL mysite.com]), vous publierez le fichier dans [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Ne créez aucun lien vers vos fichiers de test directement à partir d’une page de votre site Web. Cela invalide vos résultats de test et vos scores d’index.

**Pour déployer votre expérience**

* Sur chaque application ou serveur Web exécutant [!DNL Sensor] qui diffuse les pages impliquées dans l&#39;expérience, placez le fichier texte de configuration de l&#39;expérience dans le répertoire que vous avez spécifié dans le paramètre ExpFile dans le fichier de configuration [!DNL Sensor]. Voir [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] sélectionne de manière aléatoire les visiteurs de site Web pour chaque groupe en fonction des pourcentages que vous avez définis dans le fichier et leur fournit le contenu du test ou de la Population témoin, le cas échéant.
