---
description: Étapes permettant de garantir que le retraitement ou la retransformation se déroule sans problème et se termine à temps pour que les utilisateurs de Data Workbench puissent reprendre le travail
title: Préparation du retraitement ou de la retransformation
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Préparation du retraitement ou de la retransformation{#preparing-for-reprocessing-or-retransformation}

{{eol}}

Étapes permettant de garantir que le retraitement ou la retransformation se déroule sans problème et se termine à temps pour que les utilisateurs de Data Workbench puissent reprendre le travail

1. Déterminer le temps écoulé du traitement ou de la transformation précédent en vérifiant le rapport [!DNL Processing Mode History] dans le [!DNL Detailed Status] .

   1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la variable [!DNL Detailed Status] .
   1. Cliquez sur **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** pour afficher les temps écoulés du traitement ou de la transformation précédente.

      * Une entrée rapide est le temps total nécessaire au traitement des logs.
      * La fusion rapide est le temps total nécessaire à la transformation.
      * La somme des deux fois (entrée rapide + fusion rapide) correspond à la durée totale nécessaire au traitement du jeu de données.

      L’exemple ci-dessous indique que le traitement du journal a duré environ 43 secondes, tandis que la transformation a duré moins de 2 minutes.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Pour plus d’informations sur la variable [!DNL Detailed Status] , voir *Guide de l’utilisateur de Data Workbench*.


1. Planifiez et planifiez le retraitement. Étant donné que les utilisateurs de Data Workbench n’ont pas accès aux données pendant la phase de traitement du journal, veillez à planifier le retraitement pour qu’il se produise au moment approprié, par exemple pendant le week-end.
1. Surveillez la progression du retraitement et de la retransformation à l’aide des champs du [!DNL Processing Legend.] Pour plus d’informations sur la variable [!DNL Processing Legend], reportez-vous à la section *Guide de l’utilisateur de Data Workbench*.
