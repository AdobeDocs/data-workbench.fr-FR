---
description: Exportation de segments à l’aide de l’assistant d’exportation de segments
title: Assistant d’exportation de segments
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Segment export wizard{#segment-export-wizard}

Exportation de segments à l’aide de l’assistant d’exportation de segments

L’assistant d’exportation de segments fournit un processus détaillé pour configurer et exporter des segments au lieu d’ [exporter des segments à partir d’un tableau](https://docs.adobe.com/content/help/en/data-workbench/using/client/export-data/c-sgmt-expt.html)détaillé.

## Exportation de segments à l’aide de l’assistant {#section-b30f2699dbc7490bad18512b91cb0cb3}

Pour ouvrir l’assistant, cliquez avec le bouton droit de la souris dans un espace de travail et sélectionnez **Admin** > **Assistants** > Assistant **d’exportation de** segments.

>[!NOTE]
>
>Seuls les segments appliqués avant l’ouverture de l’assistant sont capturés. En outre, les exportations de segments créées à partir de l’assistant ne peuvent pas générer de commandes externes.

1. Sélectionnez les différents niveaux parents des dimensions et des mesures à ajouter à votre exportation.

   Les niveaux affichés dépendent du profil sélectionné. Vous pouvez sélectionner plusieurs niveaux de dimension en fonction du profil.

   ![](assets/seg_wizard_1.png)

1. Cliquez sur **Suivant**.
1. Sélectionnez la dimension et les mesures pour les niveaux sélectionnés.

   Par exemple, après avoir sélectionné Page vue comme niveau parent, vous pouvez sélectionner les dimensions et mesures enfants disponibles pour l’exportation.

1. Cliquez sur **Suivant**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Sélectionnez le format d’exportation et saisissez le nom du fichier d’exportation.

   ![](assets/seg_wizard_3.png)

   Les types CSV, TSV, Exportation de segments et Exportation de segments avec en-tête ne nécessitent aucune configuration supplémentaire. Toutefois, les options Profils et Exportation d’audience, Service d’enregistrement personnalisé et Exportation Adobe Target doivent être configurées à l’étape 3. Par exemple, voir les champs de configuration pour l’exportation Profils et audience. Configurez ces types d’exportation et cliquez sur **Suivant**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Configurez le type d’exportation sélectionné.

   En-tête (Header): si l&#39;en-tête est True, nommez le champ Fichier **de** sortie.

   Champ d’échappement (Escape Field): défini sur **True** ou **False**.

   Ordre des champs (Order of Fields): sélectionnez un champ et déplacez-le vers le haut ou vers le bas pour définir l&#39;ordre dans le fichier d&#39;exportation.

   ![](assets/seg_wizard_4.png)

   Cliquez sur **Suivant**.

1. Affichez le niveau et les filtres appliqués dans cette boîte de dialogue. Cliquez sur **Suivant**. ![](assets/seg_wizard_5.png)

1. Si **CSV**, **TSV**, Exportation de **segments ou Exportation de** **segments avec en-tête est sélectionné, trois options sont disponibles :**

   Exportation générique : le fichier de sortie sera généré par le serveur dans le dossier Server/Export.

   ![](assets/seg_wizard_6.png)

   Exportation FTP : le fichier de sortie sera transféré vers le serveur sélectionné. (La liste du serveur sera sélectionnée dans le fichier FTPServerInfo.cfg.)

   ![](assets/seg_wizard_6_1.png)

   Exportation SFTP : le fichier de sortie sera transféré en toute sécurité sur le serveur sélectionné.

1. Cliquez sur **Suivant**

   **Remarque :** Si le type d’exportation sélectionné est **Profils et Exportation** d’audience, Service **d’enregistrement** personnalisé et Exportation **** Adobe Target, le texte sera statique en fonction de l’exportation sélectionnée.

1. Configurez les paramètres de planification.

   **Un plan** peut être défini sur True ou False.

   **La planification** avancée peut être activée ou désactivée en cliquant sur le bouton Configuration de la planification avancée.

   ![](assets/seg_wizard_7.png)

   Comme pour l’exportation à partir du tableau des détails, une prise de vue disparaît si le paramètre avancé est activé. Cliquez sur **Suivant**.

1. Affichez un aperçu du fichier d’exportation, puis cliquez sur **Exécuter l’exportation**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

Les types d’exportation suivants sont disponibles dans l’assistant :

**Types d’exportation de segments**

* Générique
* FTP
* SFTP

**Exportation de segments avec en-tête**

* Générique
* FTP
* SFTP

**Exportation CSV**

* Générique
* FTP
* SFTP

**Exportation TSV**

* Générique
* FTP
* SFTP

