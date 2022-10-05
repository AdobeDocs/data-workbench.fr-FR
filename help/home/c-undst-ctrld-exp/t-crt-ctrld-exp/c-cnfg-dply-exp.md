---
description: Après avoir défini l’objectif, l’hypothèse et les détails de l’expérience, ainsi que le contenu de votre test, vous devez configurer Capteur pour déployer l’expérience contrôlée.
solution: Analytics
title: Configuration et déploiement de l’expérience
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Configuration et déploiement de l’expérience{#configuring-and-deploying-the-experiment}

{{eol}}

Après avoir défini l’objectif, l’hypothèse et les détails de l’expérience, ainsi que le contenu de votre test, vous devez configurer Capteur pour déployer l’expérience contrôlée.

## Configuration du fichier de configuration de l’expérience {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Pour configurer l’expérience, vous devez remplir la feuille de calcul de configuration de l’expérience fournie par Adobe (nommée [!DNL TestExperiment.xls] par défaut). Ce fichier configure [!DNL Sensor] pour effectuer l’expérience. Il s’agit de la version Excel du fichier texte que vous avez spécifiée dans [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

Ce fichier peut contenir des informations sur plusieurs expériences, qui peuvent s’exécuter au même moment ou à des moments différents et utiliser différents groupes et pourcentages, mais ces expériences ne sont en aucune manière corrélées.

Les utilisateurs sont placés dans un groupe pour chaque expérience répertoriée dans le fichier configuré pour être exécuté à ce moment-là.

>[!NOTE]
>
>Chaque expérience est indépendante de toutes les autres expériences. Les modifications apportées à une expérience n’affectent aucune autre expérience. Bien que les visiteurs puissent faire plusieurs expériences, les résultats ne sont pas liés les uns aux autres. Si vous pensez qu’il existe une corrélation entre les changements dans plusieurs expériences, vous devez créer une nouvelle expérience qui teste ces changements ensemble.

**Pour configurer votre expérience**

Vous devez compléter ce fichier avant que l’expérience ne commence et ne pas modifier les informations pendant l’exécution de l’expérience.

>[!NOTE]
>
>Toute expérience est rapidement invalide si la définition de l’expérience change une fois l’expérience commencée.

1. Si vous disposez d’un accès administrateur à vos serveurs web ou d’applications, accédez à la page [!DNL Sensor] dossier d’installation sur n’importe quel [!DNL Sensor] machine de votre grappe web pour accéder à [!DNL TestExperiment.xls] fichier . Si vous ne disposez pas d’un accès administrateur, contactez votre gestionnaire de compte d’Adobe pour demander à la variable [!DNL TestExperiment.xls] fichier .

1. Ouvrez le [!DNL TestExperiment.xls] (vous pouvez renommer ce fichier si vous le souhaitez) et renseignez les champs suivants :

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Expérience </td> 
   <td colname="col2"> <p>Nom explicite de l’expérience. Chaque nom d’expérience doit être unique et ne peut pas contenir d’espaces. </p> <p>Les noms d’expérience sont utilisés lors de l’affichage des résultats d’expériences dans <span class="keyword"> Insight </span>. Les noms apparaissent comme la première moitié des noms d’éléments dans la dimension de l’expérience contrôlée. La seconde moitié du nom de l'élément est le nom du groupe dans le champ Groupe de ce fichier. Chaque groupe est nommé au format suivant à l’aide du nom de l’expérience suivi du nom du groupe : </p> <p><i>NomExpérience.Group</i> </p> <p>Par exemple : <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Début </td> 
   <td colname="col2"> <p>Date et heure auxquelles vous souhaitez que l’expérience commence. Si vous ne saisissez pas de valeurs, l’expérience commence immédiatement après le déploiement du fichier. </p> <p>Format : MM/JJ/AAAA H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Si vous laissez les heures de début et d’arrêt vides, l’expérience s’exécute indéfiniment. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">Vous pouvez prédéfinir les heures de début et d’arrêt bien à l’avance ; par conséquent, vous pouvez configurer toutes vos expériences pour l’année suivante en même temps, si vous le souhaitez. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">Les heures de démarrage et d’arrêt sont basées sur l’heure système du serveur web. Si cette horloge change pour une raison quelconque, votre expérience peut démarrer ou s’arrêter de manière inattendue. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Si vous souhaitez ajouter une expérience en tant qu’entrée de fichier de configuration, mais que vous ne souhaitez pas que l’expérience s’exécute dans un futur proche, vous pouvez commenter les informations de l’expérience à l’aide du signe dièse "#" ou définir les heures de début et d’arrêt dans le passé. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>Date et heure auxquelles vous souhaitez que l’expérience se termine. Lorsque la date et l’heure d’arrêt se produisent, <span class="wintitle"> Sensor </span> cessera d’envoyer les valeurs de cookie identifiées comme un groupe de test aux URI de test et enverra tous les cookies aux URI de la population témoin. </p> <p>Format : MM/JJ/AAAA H:MM </p> <p>Voir les notes de la section <span class="wintitle"> Début </span> champ . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe </td> 
   <td colname="col2"> <p>Nom descriptif pour chaque groupe de visiteurs de l’expérience. Les noms de groupe ne peuvent pas contenir d’espaces. </p> <p>Les noms de groupe sont utilisés lors de l’affichage des résultats d’expériences dans <span class="keyword"> Insight </span>. Pour plus d’informations, voir la description du champ Expérience . </p> <p>Une population témoin peut être définie implicitement ou explicitement à partir de la valeur renseignée dans le champ Pourcentage . </p> <p> <p>Remarque : Pour que l’expérience soit statistiquement valide, vous devrez peut-être diminuer le degré de confiance ou augmenter la période afin de répondre au nombre de visiteurs nécessaire au cours de la période définie. Par exemple, si votre période est de cinq jours, votre degré de confiance est de 98 % et que le nombre de visiteurs nécessaire dépasse le nombre prévu pour cette période, vous devez augmenter la période ou diminuer le degré de confiance jusqu’à ce que le nombre de visiteurs attendu dépasse le nombre requis pour exécuter une expérience statistiquement valide. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pourcentage </td> 
   <td colname="col2"> <p>Pourcentage de visiteurs de site Web à inclure dans chaque groupe défini. Ces valeurs peuvent être exprimées sous la forme de pourcentages ou de valeurs décimales. En outre, les deux valeurs doivent être supérieures ou inférieures à une. </p> <p>Par exemple : </p> <p>33,3 % et 66,7 % </p> <p>.99 et .01 </p> <p>Si la somme pour tous les groupes est inférieure à 100, l’excédent indéfini est défini par défaut sur une population témoin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL d’origine </td> 
   <td colname="col2"> <p>URI du contenu à remapper, suivi de $. Cette valeur est sensible à la casse. </p> <p>Format : index.asp$ </p> <p>Les URI d’origine peuvent être spécifiés à l’aide d’un signe dollar ($) à la fin de l’URI pour indiquer qu’une correspondance exacte du nom de fichier est requise. Par exemple, l’expression <span class="filepath"> /product/product_view.asp$ </span> correspond uniquement à cette page exacte, tandis que <span class="filepath"> /product </span> correspond à n’importe quelle page dans <span class="filepath"> /product </span> et peut être utilisé pour remapper cette sous-arborescence entière. Les entrées d’URL d’origine qui ne spécifient pas le caractère $ à la fin du nom de fichier sont ignorées par l’expérience, sauf si le paramètre ExpPartialMatch a été défini sur "on". Pour plus d’informations sur ce paramètre, voir <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modification du paramètre ExpPartialMatch (facultatif) </a>. </p> <p>La fonctionnalité d’expérience contrôlée ignore toutes les chaînes de requête ajoutées à la racine URI. Par exemple, la page </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> n’est pas un URI valide, mais la page <span class="filepath"> /product/product_view.asp </span> est un URI valide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL récupérée </td> 
   <td colname="col2"> <p>URI du contenu alternatif. </p> <p>Format : index2.asp </p> <p>Voir les notes du champ URL d’origine . </p> </td> 
  </tr> 
 </tbody> 
</table>

Voici un exemple d’une [!DNL TextExperiment.xls] feuille de calcul :

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Ne modifiez pas la position des colonnes dans la feuille de calcul.

Cet exemple indique que l’expérience &quot;New_Homepage&quot; démarre le 1er juin 2006, se termine le 30 juin 2006 et contient une population témoin contenant 50 % des visiteurs et un groupe de test comportant 50 % des visiteurs, qui voient un contenu différent pour un URI.

>[!NOTE]
>
>Bien que le fichier d’exemple ci-dessus ait une population témoin explicite définie, il n’est pas nécessaire de définir explicitement une population témoin : l’expérience crée automatiquement la population témoin. Si la somme des pourcentages pour tous les groupes d’une expérience est inférieure à 100 %, une population témoin implicite est affectée aux utilisateurs qui ne font pas partie de l’un des groupes explicites.

1. Pour insérer des commentaires afin de fournir des informations supplémentaires sur des expériences spécifiques, commencez la cellule par un signe dièse (#) et suivez vos commentaires. Les commentaires peuvent être insérés n’importe où dans le fichier.
1. Une fois les variables renseignées dans la feuille de calcul de configuration de l’expérience, enregistrez les modifications, puis enregistrez le fichier au format de texte délimité par des tabulations ( [!DNL *.txt]) en utilisant le nom que vous avez spécifié dans le paramètre ExpFile dans la variable [!DNL Sensor] fichier de configuration. Voir [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   Voici un exemple de fichier texte de configuration d’expérience :

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >En raison des onglets requis dans ce fichier, ne modifiez pas le fichier texte de configuration de l’expérience à la main. Si vous devez apporter des modifications au fichier, apportez les modifications dans le fichier Excel de configuration de l’expérience et enregistrez à nouveau le fichier en tant que fichier texte délimité par des tabulations.

Si vous avez défini les heures de début et de fin, il n’y a aucune raison de supprimer une expérience du fichier de configuration de l’expérience. Le fait de conserver toutes vos expériences répertoriées dans le fichier de configuration de l’expérience est en fait un bon moyen de conserver un enregistrement de la manière dont vous avez défini chacune de vos expériences.

## Déploiement du fichier de configuration et du contenu de test {#section-34ff29649f584b93bc6129b75084b37c}

Vous devez déployer le fichier de configuration de l’expérience sur chaque ordinateur de la grappe web qui exécute une [!DNL Sensor] et de servir les pages impliquées dans l’expérience. Vous pouvez le faire à l’aide d’une procédure manuelle ou de votre système de gestion de contenu existant.

**Pour déployer le contenu du test**

* Sur chaque application ou serveur web exécutant un [!DNL Sensor] qui diffuse les pages impliquées dans l’expérience, utilisez votre processus de publication existant pour déployer le contenu du test à l’emplacement approprié.

   Par exemple, si vous souhaitez publier la page du groupe de test [!DNL index2.asp] au dossier test de votre site web ( [!DNL mysite.com]), vous publierez le fichier sur [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Ne créez aucun lien vers l’un de vos fichiers de test directement à partir d’une page de votre site web. Cela invalide vos résultats de test et vos scores d’index.

**Pour déployer votre expérience**

* Sur chaque application ou serveur web exécutant un [!DNL Sensor] qui diffuse les pages impliquées dans l’expérience, placez le fichier texte de configuration de l’expérience dans le répertoire que vous avez spécifié dans le paramètre ExpFile dans la variable [!DNL Sensor] fichier de configuration. Voir [Modification du paramètre ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] sélectionne de manière aléatoire les visiteurs de chaque groupe de sites web en fonction des pourcentages que vous avez définis dans le fichier et leur fournit le contenu du groupe de test ou de contrôle, le cas échéant.
