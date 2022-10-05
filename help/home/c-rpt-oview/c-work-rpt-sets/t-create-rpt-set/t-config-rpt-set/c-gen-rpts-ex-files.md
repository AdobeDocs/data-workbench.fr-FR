---
description: Informations pour générer des rapports sous forme de fichiers Excel.
title: Génération de rapports sous la forme de fichiers Microsoft Excel
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 4%

---

# Génération de rapports sous la forme de fichiers Microsoft Excel{#generating-reports-as-microsoft-excel-files}

{{eol}}

Informations pour générer des rapports sous forme de fichiers Excel.

Les exigences suivantes doivent être respectées :

* Microsoft Excel doit être installé sur le même ordinateur que [!DNL Report Server].
* Le compte utilisateur sous lequel la variable [!DNL Report Server] Le processus est en cours d’exécution et doit disposer des autorisations nécessaires pour accéder à Microsoft Excel.

   >[!NOTE]
   >
   >
   >
   >
   >    * Lorsque vous générez des rapports sous la forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel. Pour plus d’informations sur ce processus, voir [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Bien que Data Workbench prenne en charge plus de 256 colonnes et 65 536 lignes de données, Microsoft Excel ne le fait pas.


Si ces exigences sont respectées, [!DNL Report Server] lance automatiquement Microsoft Excel et génère des données à partir de certaines visualisations, légendes des dimensions et valeurs et annotations dans un nouveau classeur Excel avec une visualisation par feuille de calcul.

>[!NOTE]
>
>Les données ne sont pas exportées à partir des graphiques, des navigateurs de chemins, des mappages de processus, des tracés de dispersion et des globes.

Sauf si vous avez spécifié une [!DNL Custom Title] pour la visualisation, le type de fenêtre (par exemple, Tableau des films) est utilisé comme nom de feuille de calcul.

Pour plus d’informations sur la spécification [!DNL Custom Titles] pour les visualisations, reportez-vous à la section [Guide du client Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=fr).

## Utilisation d’un fichier de modèle {#section-40ab11916f464b1a88214ab969da6751}

Vous pouvez également générer un rapport sous la forme d’un fichier Excel à l’aide d’un modèle Excel ( [!DNL .xls] ou [!DNL .xlsx]). L’utilisation d’un fichier de modèle peut réduire le temps que vous passez à formater vos données chaque fois que le rapport est généré.

Ce fichier de modèle doit être [!DNL .xls] ou [!DNL .xlsx] fichier, pas un [!DNL .xlt] fichier .

Vous pouvez choisir de définir un modèle pour chaque rapport, un modèle générique pour tous vos rapports ou une combinaison des deux. Ces deux éléments ne s’excluent pas mutuellement. Vous pouvez donc définir un modèle générique, puis définir des modèles spécifiques.

Pour générer un rapport à l’aide d’un modèle générique que vous utilisez pour tous les rapports, vous devez indiquer le nom de ce fichier Excel dans le paramètre Modèle Excel par défaut de la variable [!DNL Report.cfg] pour ce fichier de jeu de rapports, placez le fichier de modèle dans le même dossier que le fichier [!DNL Report.cfg] pour ce jeu de rapports (*répertoire d’installation de data workbench*\*NomProfil*\Rapports\*NomJeuDeRapports*). Pour plus d’informations sur ce paramètre, voir [Paramètres Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Pour générer un rapport à l’aide d’un modèle spécifique à un rapport, vous devez nommer le fichier Excel de la même manière que l’espace de travail du rapport ( [!DNL .vw]), puis placez le fichier modèle dans le même dossier que l’espace de travail du rapport ( [!DNL .vw]).

Lorsque le rapport est généré, les feuilles d’onglets existantes dans le modèle (qui représentent chacune une visualisation) sont rérenseignées avec les données les plus récentes du rapport, tandis que les nouvelles fenêtres qui ne sont pas présentes dans le modèle sous forme de feuilles à onglets sont ignorées. Toutes les autres feuilles à onglets du fichier de modèle restent inchangées.

En outre, si une macro est définie dans le fichier Excel modèle que vous souhaitez exécuter automatiquement lors de la génération du rapport, nommez la macro &quot;VSExport&quot;.
