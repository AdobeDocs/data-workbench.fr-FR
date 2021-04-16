---
description: Le masquage désigne la sélection d’un sous-ensemble de vos données ou d’un sous-ensemble des éléments d’une dimension.
title: Masquer les données
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# Masquer les données{#mask-data}

Le masquage désigne la sélection d’un sous-ensemble de vos données ou d’un sous-ensemble des éléments d’une dimension.

Vous masquez ou masquez les éléments que vous ne souhaitez pas inclure dans l’analyse.

Data Workbench fournit deux méthodes pour masquer les éléments de dimension. La première méthode utilise les options disponibles dans le menu [!DNL Mask]. Les options de menu [!DNL Mask] vous permettent de sélectionner les éléments à afficher ou à masquer à l&#39;aide de la souris ou d&#39;afficher les éléments de premier rang lorsque vous triez les données par mesure. La deuxième méthode de masquage des éléments de dimension utilise une recherche.

**Pour masquer les données**

1. Cliquez avec le bouton droit de la souris sur un élément ou l&#39;étiquette de la dimension souhaitée, puis cliquez sur **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Cliquez sur l’une des options suivantes :

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** ou  **[!UICONTROL 500]** des éléments affichés triés par mesure
   * **[!UICONTROL Show top > All Positive]** pour afficher uniquement les valeurs supérieures à zéro (0)
   * **[!UICONTROL Display “X more”]** pour afficher le nombre d’éléments masqués actuellement
   * **[!UICONTROL At least one >]***&lt;>>*(disponible uniquement en cas d’utilisation d’une dimension Denormal)**[!UICONTROL countable dimension name]**

      Lorsque vous utilisez une dimension Denormal, cette option vous permet de masquer une dimension par une dimension dénombrable. Lorsqu’il est sélectionné, le tableau affiche uniquement les éléments qui comportent au moins un élément de la dimension dénombrable que vous avez sélectionnée. Le tableau affiche jusqu’à 1 023 éléments.

>[!NOTE]
>
>Comme l’Adobe [!DNL Platform] traite les données dans un ordre aléatoire, lorsqu’au moins un masquage génère plus de 1 023 éléments, les éléments les plus courants et les plus volumineux ont plus de chances d’être inclus dans le tableau.

Lorsque vous masquez par Afficher en haut ou Au moins un, l’ordre dans le tableau correspond par défaut aux valeurs affectées par la sélection à ce moment. Si vous modifiez ultérieurement la sélection, l’ordre ne change pas par rapport à l’ordre d’origine, sauf si le tableau est réutilisé ou si vous activez la sélection dynamique. Lorsque vous cliquez sur **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, le tableau est réutilisé chaque fois que vous modifiez la sélection.

**Pour masquer des données à l’aide d’une recherche**

* Vous pouvez masquer les données à l’aide de l’une des options de recherche suivantes :

   * Cliquez avec le bouton droit de la souris sur un élément ou l&#39;étiquette de la dimension souhaitée, cliquez sur **[!UICONTROL Mask]**, puis, dans la zone [!DNL Search], tapez l&#39;expression pour laquelle vous souhaitez effectuer une recherche.

      ![](assets/mnu_Table_MaskSearch.png)

   * Cliquez avec le bouton droit de la souris sur un élément ou sur l’étiquette de la dimension souhaitée, cliquez sur **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, puis, dans la zone de recherche qui s’affiche dans la cellule d’étiquette de dimension, tapez l’expression pour laquelle vous souhaitez effectuer une recherche.

      ![](assets/vis_Table_Mask_searchBar.png)

      Lorsque vous tapez une expression de recherche, le Data Workbench met à jour la dimension pour refléter les correspondances.

Pour limiter davantage le masquage au cours d’une recherche, utilisez l’une des méthodes suivantes :

* Vous pouvez taper &quot;re:&quot; dans la zone ou la barre [!DNL search] pour que l&#39;expression de recherche soit interprétée comme une expression ordinaire. Vous pouvez utiliser n’importe quelle syntaxe associée aux expressions régulières dans votre phrase de recherche. Pour plus d&#39;informations sur les expressions régulières, consultez l&#39;annexe Expression régulière du *Guide de configuration des ensembles de données*.
* Vous pouvez taper le symbole $ comme premier caractère dans votre chaîne de recherche pour trouver les expressions qui commencent par la chaîne que vous avez saisie ou comme dernier caractère pour trouver les expressions qui se terminent par la chaîne que vous avez saisie.
* Vous pouvez entrer un espace comme premier caractère dans votre chaîne de recherche pour trouver les mots d&#39;une phrase qui commencent par la chaîne que vous avez saisie ou comme dernier caractère pour trouver des mots d&#39;une phrase qui se terminent par la chaîne que vous avez saisie.

Vous trouverez ci-dessous des exemples de différentes manières de masquer un tableau à l’aide de la chaîne &quot;on&quot; dans une recherche :

* La saisie de &quot;on&quot; affiche chaque expression contenant la chaîne &quot;on&quot; n’importe où dans l’expression : &quot;**on** line banking&quot;, &quot;c **on** tact achers&quot;, &quot;bulli **on** coins&quot;, &quot;bank **on** line&quot;, &quot;gold opti **on** s&quot; et &quot;silver bulli **on a11/>.&quot;**
* La saisie de &quot;$on&quot; affiche chaque expression commençant par la chaîne &quot;on&quot; :

   &quot;**on** line banking&quot; et &quot;**on**-line pay&quot;.

* La saisie de &quot;on$&quot; affiche chaque expression se terminant par la chaîne &quot;on&quot; :

   &quot;bulli argenté&#x200B;**on**&quot; et &quot;gold opti **on**&quot;.

* La saisie de &quot;on&quot; affiche chaque expression contenant un mot commençant par la chaîne &quot;on&quot; :

   &quot;**on** line banking&quot; et &quot;bank **on** line banking&quot;.

* La saisie de &quot;on&quot; affiche chaque expression contenant un mot se terminant par la chaîne &quot;on&quot; :

   &quot;bulli **on** pièces&quot; et &quot;bulli argenté&#x200B;**on**&quot;.

* L’utilisation de &quot;on&quot; affiche chaque expression contenant la chaîne &quot;on&quot; sous la forme d’un mot :

   &quot;**on** line banking&quot; et &quot;bank **on** line.&quot;
