---
description: Lors de la configuration de votre jeu de données, vous pouvez définir des variables, appelées paramètres, pour représenter des valeurs significatives.
solution: Analytics
title: Définition de paramètres dans le jeu de données Inclure des fichiers
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition de paramètres dans le jeu de données Inclure des fichiers{#defining-parameters-in-dataset-include-files}

Lors de la configuration de votre jeu de données, vous pouvez définir des variables, appelées paramètres, pour représenter des valeurs significatives.

Pour affecter une valeur à un paramètre (c&#39;est-à-dire pour définir le paramètre), vous ajoutez le nom et la valeur du paramètre au vecteur Paramètres dans un fichier ou un traitement de journal. [!DNL Transformation Dataset Include] Une fois les paramètres définis, vous pouvez les référencer dans les fichiers de configuration de votre profil de jeu de données. La définition et le référencement de ces paramètres sont appelés substitution de paramètres. L&#39;utilisation de la substitution de paramètres lors de la configuration de votre jeu de données vous permet de créer un emplacement centralisé pour vos définitions de paramètres. Lorsque vous devez mettre à jour un paramètre qui est référencé plusieurs fois ou dans plusieurs fichiers, vous devez effectuer la modification une seule fois.

>[!NOTE]
>
>Dans ce guide, le terme paramètre a été utilisé pour faire référence au nom d’un paramètre d’un fichier de configuration (tel que Condition d’entrée dans le journal, Retraitement ou Transformations). Cependant, comme utilisé dans cette section, le paramètre fait spécifiquement référence à un membre du vecteur Paramètres dans un jeu de données inclut un fichier et non au nom d’un paramètre dans un fichier de configuration.

Lorsque vous définissez un paramètre, tenez compte des points suivants :

* Un paramètre doit être défini exactement une fois. Par conséquent, vous ne pouvez pas définir la même variable dans plusieurs fichiers d’inclusion de jeux de données.
* Tout paramètre que vous définissez est local pour le traitement du journal ou les phases de transformation, mais il est global dans plusieurs fichiers de configuration de jeux de données pour cette phase. Par exemple, si vous définissez un paramètre dans un [!DNL Transformation Dataset Include] fichier, le paramètre est défini pour l’ensemble de la phase de transformation et vous pouvez le référencer dans le [!DNL Transformation.cfg] fichier et dans tous les autres [!DNL Transformation Dataset Include] fichiers pour les profils hérités. Le paramètre n&#39;est pas défini pour le traitement du journal. par conséquent, toute référence au paramètre dans le [!DNL Log Processing.cfg] fichier ou un [!DNL Log Processing Dataset Include] fichier générerait une erreur de traitement.

**Pour définir un paramètre**

Vous pouvez définir des paramètres de chaîne, numériques et vectoriels dans [!DNL Log Processing] et [!DNL Transformation Include] des fichiers.

1. Dans la fenêtre Outils de données du [!DNL Log Processing] fichier ou [!DNL Transformation Dataset Include] du fichier, cliquez avec le bouton droit **[!UICONTROL Parameters]**, puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Sélectionnez **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** ou **[!UICONTROL Vector Parameter]**, et renseignez les paramètres Nom et Valeur comme décrit dans les sections suivantes.

1. Pour enregistrer le fichier d’inclusion du jeu de données dans lequel vous avez défini le paramètre, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

>[!NOTE]
>
>N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

**Pour référencer un paramètre**

* Lorsque vous référencez un paramètre défini dans un autre fichier de configuration de jeu de données, vous devez taper son nom comme [!DNL $(parameter name)].

Les sections suivantes décrivent les types de paramètres que vous pouvez définir.

* [Paramètres de chaîne et de nombres](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Paramètres vectoriels](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

