---
description: Cette section décrit les étapes à suivre pour que le retraitement ou la retransformation se déroule sans problème et se termine à temps pour que les utilisateurs des outils de données puissent reprendre le travail.
solution: Analytics
title: Préparation au retraitement ou à la retransformation
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Préparation au retraitement ou à la retransformation{#preparing-for-reprocessing-or-retransformation}

Cette section décrit les étapes à suivre pour que le retraitement ou la retransformation se déroule sans problème et se termine à temps pour que les utilisateurs des outils de données puissent reprendre le travail.

1. Déterminez le temps écoulé du traitement ou de la transformation précédent en vérifiant le profil du jeu de données [!DNL Processing Mode History] dans l’ [!DNL Detailed Status] interface.

   1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez l’ [!DNL Detailed Status] interface.
   1. Cliquez sur **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** pour afficher les temps écoulés du traitement ou de la transformation précédents.

      * Entrée rapide est le temps total nécessaire au traitement du journal.
      * La fusion rapide est le temps total nécessaire à la transformation.
      * La somme des deux fois (entrée rapide + fusion rapide) correspond au temps total nécessaire au traitement du jeu de données.
      L&#39;exemple ci-dessous indique que le traitement du journal a pris environ 43 secondes, tandis que la transformation a pris moins de 2 minutes.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Pour plus d’informations sur l’ [!DNL Detailed Status] interface, consultez le Guide *de l’utilisateur des outils de* données.


1. Planifiez et planifiez le retraitement. Etant donné que les utilisateurs des outils de données n’ont pas accès aux données pendant la phase de traitement du journal, veillez à programmer le retraitement pour qu’il se produise au bon moment, par exemple pendant le week-end.
1. Surveillez la progression du retraitement et de la retransformation à l’aide des champs de la section [!DNL Processing Legend.] Pour plus d’informations sur le [!DNL Processing Legend], consultez le Guide *de l’utilisateur des outils de* données.
