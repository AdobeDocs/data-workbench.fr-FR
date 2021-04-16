---
description: Insight Server (InsightServer64.exe) vous permet de définir des dimensions personnalisées à partir de données de événement ou de données de recherche.
title: À propos des dimensions étendues
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# À propos des dimensions étendues{#about-extended-dimensions}

Insight Server (InsightServer64.exe) vous permet de définir des dimensions personnalisées à partir de données de événement ou de données de recherche.

Toutes les dimensions personnalisées que vous définissez sont appelées dimensions étendues. Vous pouvez les utiliser pour créer des visualisations, créer des mesures étendues ou effectuer des analyses afin de comprendre les opérations et les problèmes associés à votre canal d’entreprise. Vous pouvez définir plusieurs types de dimensions étendues dans le fichier [!DNL Transformation.cfg] ou dans les fichiers [!DNL Transformation Dataset Include].

Une dimension étendue représente une relation entre les valeurs de champ de journal et une dimension parent. Une dimension parent peut être n’importe quelle dimension dénombrable définie par l’utilisateur. Voir [Dimensions dénombrables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Vous spécifiez le parent lors de la définition de la dimension dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include]. Le parent d’une dimension est identique à son niveau. Par exemple, si vous définissez une dimension avec un parent de Session, cette dimension est une dimension de niveau session.

>[!NOTE]
>
>Les valeurs de champ de journal peuvent provenir des valeurs inhérentes disponibles dans les fichiers de journal ( [!DNL .vsl]) ou d&#39;autres sources de données de événement ou des champs de journal étendus créés à l&#39;aide de transformations.

Pour ajouter une dimension étendue à une visualisation, vous pouvez y accéder à partir de la liste étendue dans le menu [!DNL Select Dimension]. Par exemple, pour ajouter une dimension étendue à une visualisation graphique, cliquez avec le bouton droit de la souris dans l’espace de travail et cliquez sur **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]***. Si vous souhaitez organiser la liste de vos dimensions étendues dans l’interface de l’outil de données, vous pouvez déplacer les dimensions étendues dans les sous-dossiers que vous créez. Consultez le chapitre Interfaces administratives du *Guide de l&#39;utilisateur Data Workbench*. Dans ce cas, les noms des sous-dossiers s’affichent également dans le menu, comme dans Visualisation Ajoutée > Graphique > Étendu > &quot;a0/>nom du sous-dossier&lt;a1/&quot; > &quot;a2/>nom de la dimension&lt;a3/&quot;.****

Pour afficher toutes les dimensions qui ont été définies pour votre profil de données et la taille de la mémoire tampon pour chacune d&#39;elles, ouvrez l&#39;interface [!DNL Detailed Status] dans l&#39;outil de données, puis cliquez sur **[!UICONTROL Performance]**, puis sur **[!UICONTROL Dimensions]** pour développer les noeuds. La taille de la mémoire tampon, qui contrôle le temps de requête, est exprimée en Mo. Pour plus d&#39;informations sur l&#39;interface [!DNL Detailed Status], consultez le Guide d&#39;administration et d&#39;installation des serveurs.
