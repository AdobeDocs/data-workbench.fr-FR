---
description: Initialisation et mise à jour d’une définition de schéma d’un profil
title: Initialisation et mise à jour d’une définition de schéma d’un profil
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Initialisation et mise à jour d’une définition de schéma d’un profil{#initializing-and-updating-a-profile-s-schema-definition}

1. Ouvrez **[!UICONTROL Schema Builder]** pour le profil que vous souhaitez configurer.
1. Un message **[!UICONTROL Loading]** s’affiche pendant la récupération du schéma à partir du profil Insight. La durée de chargement du schéma dépend de la complexité du profil en cours de chargement.
1. Une fois terminé, vous verrez un résumé des différences entre **[!UICONTROL Insight Schema]** dans le volet de gauche et **[!UICONTROL Dashboard Schema]** dans le volet de droite. Ce résumé s&#39;affiche dans la partie inférieure gauche de la fenêtre **[!UICONTROL Schema Builder]**.

   >[!NOTE]
   >
   >Lors de la configuration du schéma pour la première fois, chaque mesure, dimension et filtre est répertorié différemment du schéma du tableau de bord. Ceci est dû au fait que les objets de schéma de tableau de bord n’existent pas pour le moment.

   ![](assets/schema_builder2.png)

1. Cliquez sur le bouton **[!UICONTROL Synchronize with Schema]** pour synchroniser toutes les mesures, dimensions et filtres de la vue de Schéma Insight avec la vue de Tableau de bord.
1. Une fois l’opération terminée, vous devriez voir un message indiquant qu’aucune différence n’a été détectée :

   ![](assets/diff_found.png)

1. Si le Schéma de Tableau de bord comporte des erreurs, telles que des mesures et des dimensions de duplicata, vous devez les corriger manuellement avant de pouvoir les enregistrer.

   >[!NOTE]
   >
   >Vous pouvez supprimer de manière sélective les mesures, dimensions ou filtres de **[!UICONTROL Dashboard Schema]** que vous ne souhaitez pas afficher aux utilisateurs finaux du tableau de bord. Vous recevrez un avertissement indiquant que les éléments ne sont pas présents dans le Schéma du Tableau de bord, mais cela n’empêchera pas l’enregistrement.

1. Une fois prêt, cliquez sur **[!UICONTROL Save]** pour enregistrer vos modifications dans le schéma du tableau de bord.
1. Le système de tableau de bord utilisera cette définition de schéma pour renseigner les dimensions, les mesures et les filtres disponibles pour les utilisateurs finaux de l&#39;interface de tableau de bord.
