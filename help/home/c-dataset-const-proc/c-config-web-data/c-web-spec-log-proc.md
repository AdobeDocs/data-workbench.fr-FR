---
description: Informations sur les paramètres spécifiques au Web définis dans le jeu de données de traitement des journaux Incluez les fichiers fournis avec les profils Adobe pour le site.
solution: Analytics
title: Paramètres spécifiques au Web pour le traitement du journal
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Paramètres spécifiques au Web pour le traitement du journal{#web-specific-settings-for-log-processing}

Informations sur les paramètres spécifiques au Web définis dans le jeu de données de traitement des journaux Incluez les fichiers fournis avec les profils Adobe pour le site.

Le filtrage défini par ces paramètres se produit une fois que les entrées du journal ont quitté les décodeurs et que les transformations sont appliquées, mais avant l’évaluation par le [!DNL Log Entry Condition]serveur.

* [Filtrage de l’état HTTP](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Filtrage des robots](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## Filtrage de l’état HTTP {#section-ac66acdcb6aa467d81c3721199e540fd}

Vous pouvez configurer votre implémentation de [!DNL Site] pour supprimer des entrées de journal avec des codes sc-status de 400 ou plus du jeu de données. Les demandes réussies comportent des codes d’état inférieurs à 400. Votre implémentation par défaut comprend un [!DNL Log Processing Dataset Include] fichier dans lequel le filtrage d’état HTTP est configuré.

**Pour modifier les paramètres de configuration du filtrage d’état HTTP**

1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] fichier.

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres du fichier selon vos besoins. Utilisez l’exemple suivant comme guide.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Pour plus d’informations sur la [!DNL Range] condition, voir [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Enregistrez le [!DNL HTTP Status Filter.cfg] fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

## Filtrage des robots {#section-7f43681dfbc64b969619cb88f97d5ad5}

Vous pouvez configurer votre implémentation de [!DNL Site] pour utiliser des fichiers de recherche afin de supprimer les entrées de journal générées par des robots connus, des scripts de test et des adresses IP pour les utilisateurs internes de votre jeu de données. Votre implémentation par défaut comprend un [!DNL Log Processing Dataset Include] fichier dans lequel le filtrage des robots est configuré.

**Pour modifier les paramètres de configuration du filtrage robotisé**

1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] fichier.

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Examinez ou modifiez les paramètres du fichier à l’aide de l’exemple et des informations suivants comme guides :

   ![](assets/cfg_WebParameters_RobotFilter.png)

   Le fichier comprend un [!DNL NotRobotCondition] qui est défini par les trois paramètres suivants :

   * **Filtrage des robots non sensible à la casse :** True ou false. Si la valeur est true, la casse de la lettre (supérieure/inférieure) n’est pas prise en compte dans le filtrage des robots.
   * **Fichier de recherche Robot, ligne de base :** Chemin d’accès et nom de fichier du fichier texte qui contient une liste des agents utilisateur du navigateur connus pour être des robots et qui doivent être filtrés hors du jeu de données. Adobe fournit le fichier de recherche robot de base. Si vous ne spécifiez pas de chemin d’accès, le serveur de l’outil de données recherche ce fichier dans le répertoire de recherche du répertoire d’installation du serveur de l’outil de données.
   * **Fichier de recherche Robot, étendu :** Chemin d’accès et nom de fichier d’un fichier texte facultatif contenant une liste des agents utilisateur ou des adresses IP du navigateur qui définissent des robots spécifiques à votre implémentation. Cette liste peut inclure des robots de surveillance interne, des scripts de test et des adresses IP pour les utilisateurs internes qui doivent être filtrés hors du jeu de données. Si vous ne spécifiez pas de chemin d’accès, le serveur de l’outil de données recherche ce fichier dans le répertoire de recherche du répertoire d’installation du serveur de l’outil de données.
   Si l’agent utilisateur du navigateur d’une entrée de journal n’est répertorié dans aucun fichier de recherche, l’entrée de journal est considérée comme étant générée par un visiteur réel et n’est pas filtrée à partir du jeu de données.

   >[!NOTE]
   >
   >La correspondance dans les fichiers de recherche robotisés utilise des sous-chaînes à comparer aux champs c-ip et cs(user-agent) log. Si la chaîne de recherche commence par &quot;$&quot;, elle doit correspondre au recto de la chaîne en cours de test et si elle se termine par &quot;$&quot;, la chaîne de recherche doit correspondre à la fin de la chaîne en cours de test. Si la chaîne de recherche commence par &quot;$&quot; et se termine par &quot;$&quot;, les chaînes doivent correspondre exactement pour que l’entrée du journal soit filtrée. Par exemple, pour tester toutes les adresses IP d’un bloc de classe C, utilisez une chaîne telle que $231.78.123. pour forcer une correspondance au début de la chaîne. Cela correspondrait aux adresses 231.78.123.0 à 231.78.123.255.

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

   >[!NOTE]
   >
   >S’il est essentiel que les entrées du journal sous-jacent utilisées pour construire un jeu de données ne changent pas (même si les transformations utilisées pour construire et mettre à jour le jeu de données et ses dimensions changent), le fichier de recherche Robot, le fichier de base et le fichier de recherche Robot, le fichier de recherche Robot, le fichier étendu, doivent être contrôlés. Le fait de placer un numéro de version sur ces fichiers permet de s’assurer que les mises à jour apportées aux fichiers de recherche robotisés par défaut ne modifient pas involontairement les jeux de données de rapports créés précédemment en ajoutant ou en supprimant des entrées dans ces fichiers.

