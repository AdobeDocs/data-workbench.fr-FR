---
description: Lors de la configuration de votre jeu de données, vous pouvez définir des variables, appelées paramètres, pour représenter des valeurs significatives.
title: Définition des paramètres dans les fichiers d’inclusion de jeux de données
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Définition des paramètres dans les fichiers d’inclusion de jeux de données{#defining-parameters-in-dataset-include-files}

Lors de la configuration de votre jeu de données, vous pouvez définir des variables, appelées paramètres, pour représenter des valeurs significatives.

Pour attribuer une valeur à un paramètre (c’est-à-dire pour définir le paramètre), vous ajoutez le nom et la valeur du paramètre au vecteur Paramètres dans un fichier de traitement de journal ou [!DNL Transformation Dataset Include] fichier . Une fois les paramètres définis, vous pouvez les référencer dans les fichiers de configuration de votre profil de jeu de données. La définition et le référencement de ces paramètres sont appelés substitution de paramètre. L’utilisation de la substitution des paramètres lors de la configuration de votre jeu de données vous permet de créer un emplacement centralisé pour vos définitions de paramètres. Lorsque vous devez mettre à jour un paramètre qui est référencé plusieurs fois ou dans plusieurs fichiers, vous ne devez apporter la modification qu’une seule fois.

>[!NOTE]
>
>Dans ce guide, le paramètre de terme a été utilisé pour faire référence au nom de tout paramètre dans un fichier de configuration (tel que Condition d’entrée au journal, Retraitement ou Transformations). Cependant, comme utilisé dans cette section, le paramètre fait spécifiquement référence à un membre du vecteur Paramètres d’un jeu de données dans un fichier d’inclusion et non au nom d’un paramètre dans un fichier de configuration.

Lorsque vous définissez un paramètre, tenez compte des points suivants :

* Un paramètre doit être défini une seule fois. Par conséquent, vous ne pouvez pas définir la même variable dans plusieurs fichiers d’inclusion de jeux de données.
* Tout paramètre que vous définissez est local pour les phases de traitement du journal ou de transformation, mais il est global dans plusieurs fichiers de configuration de jeux de données pour cette phase. Par exemple, si vous définissez un paramètre dans un fichier [!DNL Transformation Dataset Include] , le paramètre est défini pour toute la phase de transformation et vous pouvez le référencer dans le fichier [!DNL Transformation.cfg] et dans tous les autres fichiers [!DNL Transformation Dataset Include] pour les profils hérités. Le paramètre n’est pas défini pour le traitement du journal. par conséquent, toute référence au paramètre dans le fichier [!DNL Log Processing.cfg] ou un fichier [!DNL Log Processing Dataset Include] générerait une erreur de traitement.

**Pour définir un paramètre**

Vous pouvez définir des paramètres de chaîne, numériques et vectoriels dans les fichiers [!DNL Log Processing] et [!DNL Transformation Include].

1. Dans la fenêtre Data Workbench du fichier [!DNL Log Processing] ou [!DNL Transformation Dataset Include], cliquez avec le bouton droit de la souris sur **[!UICONTROL Parameters]**, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Sélectionnez **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** ou **[!UICONTROL Vector Parameter]**, puis renseignez les paramètres Nom et Valeur comme décrit dans les sections suivantes.

1. Pour enregistrer le fichier d’inclusion du jeu de données dans lequel vous avez défini le paramètre, cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

>[!NOTE]
>
>N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

**Pour référencer un paramètre**

* Lorsque vous référencez un paramètre défini dans un autre fichier de configuration de jeu de données, vous devez saisir son nom en tant que [!DNL $(parameter name)].

Les sections suivantes décrivent les types de paramètres que vous pouvez définir.

* [Paramètres de chaîne et numériques](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Paramètres vectoriels](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
