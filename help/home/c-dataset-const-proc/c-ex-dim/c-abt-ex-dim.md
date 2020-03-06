---
description: Le serveur Insight (InsightServer64.exe) vous permet de définir des dimensions personnalisées à partir de données d’événement ou de recherche.
solution: Analytics
title: A propos des dimensions étendues
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# A propos des dimensions étendues{#about-extended-dimensions}

Le serveur Insight (InsightServer64.exe) vous permet de définir des dimensions personnalisées à partir de données d’événement ou de recherche.

Toutes les dimensions personnalisées que vous définissez sont appelées dimensions étendues. Vous pouvez les utiliser pour créer des visualisations, créer des mesures étendues ou effectuer des analyses afin de comprendre les opérations et les problèmes associés à votre canal d’entreprise. Vous pouvez définir plusieurs types de dimensions étendues dans le [!DNL Transformation.cfg] fichier ou [!DNL Transformation Dataset Include] dans les fichiers.

Une dimension étendue représente une relation entre les valeurs de champ de journal et une dimension parent. Une dimension parent peut être n’importe quelle dimension dénombrable définie par l’utilisateur. Voir Dimensions [dénombrables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Vous spécifiez le parent lors de la définition de la dimension dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier. Le parent d’une dimension est le même que son niveau. Par exemple, si vous définissez une dimension avec un parent de Session, cette dimension est une dimension de niveau session.

>[!NOTE]
>
>Les valeurs de champ de journal peuvent provenir des valeurs inhérentes disponibles dans les fichiers de journal ( [!DNL .vsl]) ou d’autres sources de données d’événement ou des champs de journal étendus créés à l’aide de transformations.

Pour ajouter une dimension étendue à une visualisation, vous y accédez à partir de la liste Etendue du [!DNL Select Dimension] menu. Par exemple, pour ajouter une dimension étendue à une visualisation graphique, cliquez avec le bouton droit de la souris dans l’espace de travail et cliquez sur **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Si vous souhaitez organiser la liste de vos dimensions étendues dans l’interface de l’outil de données, vous pouvez déplacer les dimensions étendues dans les sous-dossiers que vous créez. Voir le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données. Dans ce cas, les noms des sous-dossiers s’affichent également dans le menu, comme dans Ajouter une visualisation > Graphique > Étendu > &lt;nom *du* sous-dossier> > &lt;nom *de* la dimension>.

Pour afficher toutes les dimensions définies pour votre profil de jeu de données et la taille de la mémoire tampon pour chacune d’elles, ouvrez l’ [!DNL Detailed Status] interface dans l’outil de données, puis cliquez sur **[!UICONTROL Performance]**, **[!UICONTROL Dimensions]** pour développer les noeuds. La taille de la mémoire tampon, qui contrôle les temps de requête, est exprimée en Mo. Pour plus d’informations sur l’ [!DNL Detailed Status] interface, voir le guide Administration et installation des serveurs.
