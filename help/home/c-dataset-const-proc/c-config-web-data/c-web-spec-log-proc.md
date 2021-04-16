---
description: Informations sur les paramètres spécifiques au Web définis dans le jeu de données de traitement du journal Incluez les fichiers distribués avec les profils d'Adobe pour le site.
title: Paramètres spécifiques web pour le traitement des fichiers journaux
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
exl-id: abb6e6a7-011f-40d6-b778-16da2332af72
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Paramètres spécifiques web pour le traitement des fichiers journaux{#web-specific-settings-for-log-processing}

Informations sur les paramètres spécifiques au Web définis dans le jeu de données de traitement du journal Incluez les fichiers distribués avec les profils d&#39;Adobe pour le site.

Le filtrage défini par ces paramètres se produit une fois que les entrées du journal ont quitté les décodeurs et que les transformations sont appliquées, mais avant l&#39;évaluation par [!DNL Log Entry Condition].

* [Filtrage d’état HTTP](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Filtrage des robots](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## Filtrage d’état HTTP {#section-ac66acdcb6aa467d81c3721199e540fd}

Vous pouvez configurer votre implémentation de [!DNL Site] pour supprimer du jeu de données les entrées de journal dont le code sc-status est supérieur ou égal à 400. Les demandes réussies comportent des codes d’état inférieurs à 400. Votre implémentation par défaut comprend un fichier [!DNL Log Processing Dataset Include] dans lequel le filtrage d’état HTTP est configuré.

**Pour modifier les paramètres de configuration du filtrage d’état HTTP**

1. Ouvrez [!DNL Profile Manager] dans votre profil de jeux de données et ouvrez le fichier [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé l&#39;implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l&#39;emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres du fichier selon vos besoins. Utilisez l’exemple suivant comme guide.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Pour plus d&#39;informations sur la condition [!DNL Range], voir [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Enregistrez le fichier [!DNL HTTP Status Filter.cfg] en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

## Filtrage des robots {#section-7f43681dfbc64b969619cb88f97d5ad5}

Vous pouvez configurer votre implémentation de [!DNL Site] pour utiliser des fichiers de recherche afin de supprimer les entrées de journal générées par des robots connus, des scripts de test et des adresses IP pour les utilisateurs internes de votre jeu de données. Votre implémentation par défaut comprend un fichier [!DNL Log Processing Dataset Include] dans lequel le filtrage des robots est configuré.

**Pour modifier les paramètres de configuration du filtrage robotique**

1. Ouvrez [!DNL Profile Manager] dans votre profil de jeux de données et ouvrez le fichier [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé l&#39;implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l&#39;emplacement décrit.

1. Examinez ou modifiez les paramètres du fichier à l’aide de l’exemple et des informations suivants comme guides :

   ![](assets/cfg_WebParameters_RobotFilter.png)

   Le fichier comprend un [!DNL NotRobotCondition] défini par les trois paramètres suivants :

   * **Filtrage Robot Insensible à la casse :** Vrai ou Faux. Si la valeur est true, la casse de la lettre (supérieure/inférieure) n’est pas prise en compte dans le filtrage par robot.
   * **Fichier de recherche Robot, ligne de base :** chemin d’accès et nom de fichier du fichier texte qui contient une liste d’agents utilisateur de navigateur connus pour être des robots et qui doivent être filtrés hors du jeu de données. L&#39;Adobe fournit le fichier de recherche robot de base. Si vous ne spécifiez pas de chemin d’accès, le serveur d’outils de données recherche ce fichier dans le répertoire Lookups du répertoire d’installation du serveur d’outils de données.
   * **Fichier de recherche Robot, étendu :** chemin d’accès et nom de fichier d’un fichier texte facultatif contenant une liste d’agents utilisateur ou d’adresses IP du navigateur qui définissent des robots spécifiques à votre implémentation. Cette liste peut inclure des robots de surveillance interne, des scripts de test et des adresses IP pour les utilisateurs internes qui doivent être filtrés hors du jeu de données. Si vous ne spécifiez pas de chemin d’accès, le serveur d’outils de données recherche ce fichier dans le répertoire Lookups du répertoire d’installation du serveur d’outils de données.

   Si l&#39;agent utilisateur du navigateur d&#39;une entrée de journal n&#39;est répertorié dans aucun fichier de recherche, l&#39;entrée de journal est considérée comme étant générée par un véritable visiteur et n&#39;est pas filtrée à partir du jeu de données.

   >[!NOTE]
   >
   >La correspondance dans les fichiers de recherche de robots utilise des sous-chaînes à comparer aux champs c-ip et cs(user-agent) log. Si la chaîne de recherche début par &quot;$&quot;, elle doit correspondre à l&#39;avant de la chaîne en cours de test et si elle se termine par &quot;$&quot;, la chaîne de recherche doit correspondre à la fin de la chaîne en cours de test. Si la chaîne de recherche commence par &quot;$&quot; et se termine par &quot;$&quot;, les chaînes doivent correspondre exactement pour que l&#39;entrée du journal soit filtrée. Par exemple, pour tester toutes les adresses IP d&#39;un bloc de classe C, vous utiliseriez une chaîne telle que $231.78.123. pour forcer une correspondance à l&#39;avant de la chaîne. Cela correspondrait aux adresses 231.78.123.0 à 231.78.123.255.

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

   >[!NOTE]
   >
   >S&#39;il est essentiel que les entrées de journal sous-jacentes utilisées pour construire un jeu de données ne changent pas (même si les transformations utilisées pour construire et mettre à jour le jeu de données et ses dimensions changent), le fichier de recherche Robot, la ligne de base et le fichier de recherche Robot, étendu, doivent être contrôlés par la version. En plaçant un numéro de version sur ces fichiers, vous vous assurez que les mises à jour apportées aux fichiers de recherche de robots par défaut ne modifient pas involontairement les jeux de données de rapports créés précédemment en ajoutant ou en supprimant des entrées dans ces fichiers.
