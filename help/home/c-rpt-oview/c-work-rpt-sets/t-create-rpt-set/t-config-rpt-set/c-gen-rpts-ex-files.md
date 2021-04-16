---
description: Informations permettant de générer des rapports sous la forme de fichiers Excel.
title: Génération de rapports sous la forme de fichiers Microsoft Excel
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 4%

---

# Génération de rapports sous la forme de fichiers Microsoft Excel{#generating-reports-as-microsoft-excel-files}

Informations permettant de générer des rapports sous la forme de fichiers Excel.

Les exigences suivantes doivent être respectées :

* Microsoft Excel doit être installé sur le même ordinateur que [!DNL Report Server].
* Le compte utilisateur sous lequel le processus [!DNL Report Server] est exécuté doit disposer des autorisations nécessaires pour accéder à Microsoft Excel.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Lorsque vous générez des rapports sous la forme de fichiers Excel, vous ouvrez une nouvelle instance d&#39;Excel. Pour plus d’informations sur ce processus, voir [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
   >    * Bien que les outils de données prennent en charge plus de 256 colonnes et 65 536 lignes de données, Microsoft Excel ne le prend pas.


Si ces conditions sont remplies, [!DNL Report Server] début automatiquement Microsoft Excel et génère les données de certaines visualisations, légendes de dimension et de valeur et annotations de texte dans un nouveau classeur Excel avec une visualisation par feuille de calcul.

>[!NOTE]
>
>Les données ne sont pas exportées à partir de graphiques, de navigateurs de chemins, de mappages de processus, de tracés de dispersion et de globes.

A moins que vous n’ayez spécifié un [!DNL Custom Title] pour la visualisation, le type de fenêtre (par exemple, Table de film) est utilisé comme nom de feuille de calcul.

Pour plus d&#39;informations sur la spécification de [!DNL Custom Titles] pour les visualisations, consultez le [Guide du client Data Workbench](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/client/t-open-ins.html).

## Utilisation d&#39;un fichier modèle {#section-40ab11916f464b1a88214ab969da6751}

Vous pouvez également générer un rapport sous la forme d&#39;un fichier Excel à l&#39;aide d&#39;un fichier Excel modèle ( [!DNL .xls] ou [!DNL .xlsx]). L&#39;utilisation d&#39;un fichier de modèle peut réduire le temps passé à formater vos données chaque fois que le rapport est généré.

Ce fichier de modèle doit être un fichier [!DNL .xls] ou [!DNL .xlsx], et non un fichier [!DNL .xlt].

Vous pouvez choisir de définir un modèle pour chaque rapport individuel, un modèle générique pour tous vos rapports ou une combinaison des deux. Ces deux éléments ne s’excluent pas mutuellement. Vous pouvez donc définir un modèle générique, puis définir des modèles spécifiques.

Pour générer un rapport à l&#39;aide d&#39;un modèle générique que vous utilisez pour tous les rapports, vous devez indiquer le nom de ce fichier Excel dans le paramètre Modèle Excel par défaut de [!DNL Report.cfg] pour ce fichier de jeu de rapports, puis placer le fichier de modèle dans le même dossier que le [!DNL Report.cfg] pour ce jeu de rapports (*répertoire d&#39;installation des outils de données*\*NomProfil*\Reports\*NomReportSetName*). Pour plus d’informations sur ce paramètre, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Pour générer un rapport à l&#39;aide d&#39;un modèle spécifique à un rapport, vous devez nommer le fichier Excel de la même manière que le fichier de l&#39;espace de travail du rapport ( [!DNL .vw]), puis placer le fichier de modèle dans le même dossier que le fichier de l&#39;espace de travail du rapport ( [!DNL .vw]).

Lorsque le rapport est généré, les feuilles à onglets existantes dans le modèle (chacune représentant une visualisation) sont réinsérées avec les données les plus récentes du rapport, tandis que les nouvelles fenêtres qui ne sont pas présentes dans le modèle en tant que feuilles à onglets sont ignorées. Toutes les autres feuilles à onglets du fichier de modèle restent inchangées.

En outre, si une macro est définie dans le fichier Excel du modèle que vous souhaitez exécuter automatiquement lors de la génération du rapport, nommez la macro &quot;VSExport&quot;.
