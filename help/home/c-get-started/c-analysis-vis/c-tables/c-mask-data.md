---
description: Le masquage consiste à sélectionner un sous-ensemble de vos données ou un sous-ensemble des éléments d’une dimension.
title: Masquer les données
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# Masquer les données{#mask-data}

{{eol}}

Le masquage consiste à sélectionner un sous-ensemble de vos données ou un sous-ensemble des éléments d’une dimension.

Vous masquez ou masquez les éléments que vous ne souhaitez pas inclure dans l’analyse.

Data Workbench fournit deux méthodes pour masquer les éléments de dimension. La première méthode utilise les options disponibles dans la variable [!DNL Mask] . En utilisant la variable [!DNL Mask] vous pouvez utiliser la souris pour sélectionner les éléments à afficher ou à masquer ou afficher les éléments de premier rang lorsque vous triez les données par mesure. La deuxième méthode de masquage des éléments de dimension utilise une recherche.

**Masquer les données**

1. Cliquez avec le bouton droit de la souris sur un élément ou sur le libellé de la dimension souhaitée, puis cliquez sur **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Cliquez sur l’une des options suivantes :

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** ou **[!UICONTROL 500]** des éléments affichés triés par mesure
   * **[!UICONTROL Show top > All Positive]** pour afficher uniquement les valeurs supérieures à zéro (0)
   * **[!UICONTROL Display “X more”]** pour afficher le nombre d’éléments masqués actuellement
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(disponible uniquement lorsque vous utilisez une dimension non normalisée)

      Lorsque vous utilisez une dimension Denormal, cette option vous permet de masquer une dimension par une dimension dénombrable. Lorsqu’il est sélectionné, le tableau n’affiche que les éléments comportant au moins un élément de la dimension dénombrable que vous avez sélectionnée. Le tableau contient jusqu’à 1 023 éléments.

>[!NOTE]
>
>Parce que l&#39;Adobe [!DNL Platform] traite les données de manière aléatoire, lorsque au moins un masquage génère plus de 1 023 éléments, les éléments les plus courants et les plus volumineux ont de meilleures chances d’être inclus dans le tableau.

Lorsque vous masquez par Afficher en haut ou Au moins une, par défaut l&#39;ordre dans le tableau correspond aux valeurs affectées par la sélection à ce moment-là. Si vous modifiez ultérieurement la sélection, l’ordre ne change pas par rapport à l’ordre d’origine, sauf si le tableau est réinitialisé ou si vous activez la sélection dynamique. Lorsque vous cliquez sur **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, le tableau est réinitialisé chaque fois que vous modifiez la sélection.

**Pour masquer des données à l’aide d’une recherche**

* Vous pouvez masquer les données à l’aide de l’une des options de recherche suivantes :

   * Cliquez avec le bouton droit de la souris sur un élément ou sur le libellé de la dimension souhaitée, puis cliquez sur **[!UICONTROL Mask]**, puis dans la variable [!DNL Search] saisissez l’expression à rechercher.

      ![](assets/mnu_Table_MaskSearch.png)

   * Cliquez avec le bouton droit de la souris sur un élément ou sur le libellé de la dimension souhaitée, puis cliquez sur **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, puis, dans la zone de recherche qui s’affiche dans la cellule d’étiquette de dimension, saisissez l’expression à rechercher.

      ![](assets/vis_Table_Mask_searchBar.png)

      Lorsque vous saisissez une expression de recherche, Data Workbench met à jour la dimension pour qu’elle reflète les correspondances.

Pour limiter davantage le masquage lors d’une recherche, vous pouvez utiliser l’une des méthodes suivantes :

* Vous pouvez saisir &quot;re:&quot; dans la variable [!DNL search] pour que l’expression de recherche soit interprétée comme une expression régulière. Vous pouvez utiliser n’importe quelle syntaxe associée à des expressions régulières dans votre expression de recherche. Pour plus d’informations sur les expressions régulières, reportez-vous à l’annexe Expression régulière de la section *Guide de configuration des jeux de données*.
* Vous pouvez saisir le symbole $ comme premier caractère de votre chaîne de recherche pour rechercher les expressions qui commencent par la chaîne que vous avez saisie, ou comme dernier caractère pour trouver les expressions qui se terminent par la chaîne que vous avez saisie.
* Vous pouvez saisir un espace comme premier caractère de votre chaîne de recherche pour trouver les mots d’une expression commençant par la chaîne que vous avez saisie, ou comme dernier caractère pour trouver les mots d’une expression se terminant par la chaîne que vous avez saisie.

Vous trouverez ci-dessous des exemples de différentes manières de masquer un tableau à l’aide de la chaîne &quot;on&quot; dans une recherche :

* Saisissez &quot;on&quot; pour afficher chaque expression contenant la chaîne &quot;on&quot; n’importe où dans l’expression : &quot;**on** line banking, c **on** acheteurs de tact, bulli **on** les pièces de monnaie&quot;, &quot;banque **on** line, or opti **on** s,&quot; et &quot;bulli d’argent **on**.&quot;
* Saisissez &quot;$on&quot; pour afficher chaque expression commençant par la chaîne &quot;on&quot; :

   &quot;**on** banque de ligne et **on** paiement en ligne.&quot;

* Saisissez &quot;on$&quot; pour afficher chaque expression se terminant par la chaîne &quot;on&quot; :

   &quot;bulle d&#39;argent **on**&quot; et &quot;gold opti **on**.&quot;

* Saisissez &quot;on&quot; pour afficher chaque expression contenant un mot commençant par la chaîne &quot;on&quot; :

   &quot;**on**&quot;line banking&quot; et &quot;bank&quot; **on** line.&quot;

* Saisissez &quot;on&quot; pour afficher chaque expression contenant un mot qui se termine par la chaîne &quot;on&quot; :

   &quot;bulli **on** les pièces de monnaie et les &quot;bulli d&#39;argent&quot;**on**.&quot;

* L’utilisation de &quot;on&quot; affiche sous la forme d’un mot chaque expression contenant la chaîne &quot;on&quot; :

   &quot;**on** &quot;line banking&quot; et &quot;bank&quot; **on** line.&quot;
