---
description: Le serveur Insight (InsightServer64.exe) vous permet de définir des dimensions personnalisées à partir de données d’événement ou de données de recherche.
title: À propos des dimensions étendues
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# À propos des dimensions étendues{#about-extended-dimensions}

{{eol}}

Le serveur Insight (InsightServer64.exe) vous permet de définir des dimensions personnalisées à partir de données d’événement ou de données de recherche.

Toutes les dimensions personnalisées que vous définissez sont appelées des dimensions étendues. Vous pouvez les utiliser pour créer des visualisations, créer des mesures étendues ou effectuer des analyses afin de comprendre les opérations et les problèmes liés à votre canal d’entreprise. Vous pouvez définir plusieurs types de dimensions étendues dans la variable [!DNL Transformation.cfg] ou dans [!DNL Transformation Dataset Include] fichiers .

Une dimension étendue représente une relation entre les valeurs de champ de journal et une dimension parente. Une dimension parente peut être n’importe quelle dimension dénombrable définie par l’utilisateur. Voir [Dimensions dénombrables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Vous spécifiez le parent lors de la définition de la dimension dans la variable [!DNL Transformation.cfg] ou un [!DNL Transformation Dataset Include] fichier . Le parent d’une dimension est le même que son niveau. Par exemple, si vous définissez une dimension avec un parent de Session, cette dimension est une dimension de niveau session.

>[!NOTE]
>
>Les valeurs des champs du journal peuvent provenir des valeurs inhérentes disponibles dans le journal ( [!DNL .vsl]) ou d’autres sources de données d’événement ou des champs de journal étendus créés à l’aide de transformations.

Pour ajouter une dimension étendue à une visualisation, vous pouvez y accéder à partir de la liste Étendue de la section [!DNL Select Dimension] . Par exemple, pour ajouter une dimension étendue à une visualisation graphique, cliquez avec le bouton droit de la souris dans l’espace de travail, puis cliquez sur **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Si vous souhaitez organiser la liste de vos dimensions étendues dans l’interface de Data Workbench, vous pouvez déplacer les dimensions étendues dans les sous-dossiers que vous créez. Voir le chapitre Interfaces administratives de la section *Guide de l’utilisateur de Data Workbench*. Dans ce cas, les noms des sous-dossiers s’affichent également dans le menu, comme dans Ajouter une visualisation > Graphique > Étendu > &lt;*nom du sous-dossier*> &lt;*nom de la dimension*>.

Pour afficher toutes les dimensions qui ont été définies pour votre profil de jeu de données et la taille de la mémoire tampon pour chacune d’elles, ouvrez le [!DNL Detailed Status] dans data workbench et cliquez sur **[!UICONTROL Performance]**, puis **[!UICONTROL Dimensions]** pour développer les noeuds. La taille de la mémoire tampon, qui contrôle les temps de requête, est exprimée en Mo. Pour plus d’informations sur la variable [!DNL Detailed Status] , voir le guide Administration et installation du serveur .
