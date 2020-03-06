---
description: Informations relatives à la génération de rapports sous forme de fichiers Excel.
solution: Analytics
title: Génération de rapports sous forme de fichiers Microsoft Excel
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Génération de rapports sous forme de fichiers Microsoft Excel{#generating-reports-as-microsoft-excel-files}

Informations relatives à la génération de rapports sous forme de fichiers Excel.

Les conditions suivantes doivent être remplies :

* Microsoft Excel doit être installé sur le même ordinateur que [!DNL Report Server].
* Le compte utilisateur sous lequel le [!DNL Report Server] processus est en cours d’exécution doit avoir l’autorisation d’accéder à Microsoft Excel.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Lorsque vous générez des rapports sous forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel. Pour plus d’informations sur ce processus, voir [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
   >    * Bien que les outils de données prennent en charge plus de 256 colonnes et 65 536 lignes de données, Microsoft Excel ne le prend pas en charge.


Si ces conditions sont remplies, [!DNL Report Server] démarre automatiquement Microsoft Excel et génère des données à partir de certaines visualisations, légendes de dimension et de valeur et annotations textuelles dans un nouveau classeur Excel avec une visualisation par feuille de calcul.

>[!NOTE]
>
>Les données ne sont pas exportées à partir de graphiques, de navigateurs de chemins, de mappages de processus, de tracés de dispersion et de globes.

A moins que vous n’ayez spécifié un nom [!DNL Custom Title] pour la visualisation, le type de fenêtre (par exemple, Table de film) est utilisé comme nom de feuille de calcul.

Pour plus d’informations sur la spécification [!DNL Custom Titles] pour les visualisations, consultez le Guide [du client des outils de](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html)données.

## Utilisation d’un fichier modèle {#section-40ab11916f464b1a88214ab969da6751}

Vous pouvez également générer un rapport sous forme de fichier Excel à l’aide d’un modèle de fichier Excel ( [!DNL .xls] ou [!DNL .xlsx]). L’utilisation d’un fichier de modèle peut réduire le temps passé à formater vos données chaque fois que le rapport est généré.

Ce fichier de modèle doit être un fichier [!DNL .xls] ou [!DNL .xlsx] , et non un [!DNL .xlt] fichier.

Vous pouvez choisir de définir un modèle pour chaque rapport individuel, un modèle générique pour tous vos rapports ou une combinaison des deux. Ces deux éléments ne s’excluent pas mutuellement. Vous pouvez donc définir un modèle générique, puis définir des modèles spécifiques.

Pour générer un rapport à l’aide d’un modèle générique que vous utilisez pour tous les rapports, vous devez spécifier le nom de ce fichier Excel dans le paramètre Modèle Excel par défaut [!DNL Report.cfg] pour ce fichier de jeu de rapports, puis le placer dans le même dossier que [!DNL Report.cfg] pour ce jeu de rapports (répertoire *d’installation des outils de* données\*NomProfil*\Reports\*NomJeuRapport*). Pour plus d’informations sur ce paramètre, voir Paramètres [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

Pour générer un rapport à l&#39;aide d&#39;un modèle spécifique à un rapport, vous devez nommer le fichier Excel de la même manière que le fichier de l&#39;espace de travail du rapport ( [!DNL .vw]), puis placer le fichier du modèle dans le même dossier que le fichier de l&#39;espace de travail du rapport ( [!DNL .vw]).

Lors de la génération du rapport, les feuilles à onglets existantes dans le modèle (chacune représentant une visualisation) sont reremplies avec les données les plus récentes du rapport, tandis que les nouvelles fenêtres qui ne sont pas présentes dans le modèle sous forme de feuilles à onglets sont ignorées. Toutes les autres feuilles à onglets du fichier de modèle restent inchangées.

En outre, si une macro est définie dans le fichier Excel du modèle et que vous souhaitez l’exécuter automatiquement lors de la génération du rapport, nommez la macro &quot;VSExport&quot;.
