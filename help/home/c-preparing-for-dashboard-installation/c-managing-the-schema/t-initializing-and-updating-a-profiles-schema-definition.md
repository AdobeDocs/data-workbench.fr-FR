---
description: Initialisation et mise à jour d’une définition de schéma d’un profil
title: Initialisation et mise à jour d’une définition de schéma d’un profil
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Initialisation et mise à jour d’une définition de schéma d’un profil{#initializing-and-updating-a-profile-s-schema-definition}

1. Ouvrez la **[!UICONTROL Schema Builder]** correspondant au profil que vous souhaitez configurer.
1. Un message **[!UICONTROL Loading]** s’affiche pendant la récupération du schéma à partir du profil Insight. La durée du chargement du schéma dépend de la complexité du profil en cours de chargement.
1. Une fois l’opération terminée, vous verrez un résumé des différences entre **[!UICONTROL Insight Schema]** dans le volet de gauche et **[!UICONTROL Dashboard Schema]** dans le volet de droite. Ce résumé s’affiche dans la partie inférieure gauche de la fenêtre **[!UICONTROL Schema Builder]**.

   >[!NOTE]
   >
   >Lors de la configuration initiale du schéma, chaque mesure, dimension et filtre est répertorié différemment du schéma du tableau de bord. Cela est dû au fait que les objets de schéma de tableau de bord n’existent pas pour l’instant.

   ![](assets/schema_builder2.png)

1. Cliquez sur le bouton **[!UICONTROL Synchronize with Schema]** pour synchroniser toutes les mesures, dimensions et filtres de la vue Schéma Insight avec la vue Schéma du tableau de bord.
1. Une fois l’opération terminée, un message s’affiche indiquant qu’aucune différence n’a été trouvée :

   ![](assets/diff_found.png)

1. Si le schéma de tableau de bord comporte des erreurs (mesures et dimensions en double, par exemple), vous devez les corriger manuellement avant de pouvoir l’enregistrer.

   >[!NOTE]
   >
   >Vous pouvez supprimer de manière sélective les mesures, dimensions ou filtres de la **[!UICONTROL Dashboard Schema]** que vous ne souhaitez pas afficher aux utilisateurs finaux du tableau de bord. Vous recevrez un avertissement indiquant que les éléments ne sont pas présents dans le schéma de tableau de bord, mais cela ne vous empêchera pas d’enregistrer.

1. Une fois prêt, cliquez sur **[!UICONTROL Save]** pour enregistrer vos modifications dans le schéma du tableau de bord.
1. Le système de tableau de bord utilisera cette définition de schéma pour renseigner les dimensions, les mesures et les filtres disponibles pour les utilisateurs finaux dans l’interface du tableau de bord.
