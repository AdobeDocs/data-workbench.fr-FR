---
description: Procédure permettant de s’assurer que le retraitement ou la retransformation se déroule en douceur et se termine à temps pour que les utilisateurs des outils de données puissent reprendre le travail
title: Préparation du retraitement ou de la retransformation
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Préparation du retraitement ou de la retransformation{#preparing-for-reprocessing-or-retransformation}

Procédure permettant de s’assurer que le retraitement ou la retransformation se déroule en douceur et se termine à temps pour que les utilisateurs des outils de données puissent reprendre le travail

1. Déterminez le temps écoulé du traitement ou de la transformation précédent en vérifiant le profil de données [!DNL Processing Mode History] dans l&#39;interface [!DNL Detailed Status].

   1. Lorsque vous travaillez dans votre profil de jeux de données, ouvrez l&#39;interface [!DNL Detailed Status].
   1. Cliquez sur **[!UICONTROL Processing Status]** > *&lt; &lt;a2/&quot;* > **[!UICONTROL Processing Mode History]** pour vue les temps écoulés du traitement ou de la transformation précédents.**[!UICONTROL dataset profile name]**

      * Entrée rapide est le temps total nécessaire au traitement du journal.
      * La fusion rapide est le temps total nécessaire à la transformation.
      * La somme des deux fois (Entrée rapide + Fusion rapide) correspond au temps total nécessaire au traitement du jeu de données.

      L&#39;exemple ci-dessous indique que le traitement du journal a pris environ 43 secondes, tandis que la transformation a pris moins de 2 minutes.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Pour plus d&#39;informations sur l&#39;interface [!DNL Detailed Status], consultez le *Guide de l&#39;utilisateur Data Workbench*.


1. Planifiez et planifiez le retraitement. Etant donné que les utilisateurs des outils de données n’ont pas accès aux données pendant la phase de traitement du journal, veillez à programmer le retraitement pour qu’il se produise au moment approprié, par exemple pendant le week-end.
1. Surveillez l&#39;avancement du retraitement et de la retransformation à l&#39;aide des champs du [!DNL Processing Legend.] Pour plus d&#39;informations sur [!DNL Processing Legend], consultez le *Guide de l&#39;utilisateur Data Workbench*.
