---
description: valeur nulle
solution: Analytics
title: Initialisation et mise à jour de la définition de schéma d’un profil
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Initialisation et mise à jour de la définition de schéma d’un profil{#initializing-and-updating-a-profile-s-schema-definition}

1. Ouvrez le profil **[!UICONTROL Schema Builder]** que vous souhaitez configurer.
1. Un **[!UICONTROL Loading]** message s’affiche pendant la récupération du schéma à partir du profil Insight. La durée de chargement du schéma dépend de la complexité du profil en cours de chargement.
1. Une fois l’opération terminée, vous verrez un résumé des différences entre le **[!UICONTROL Insight Schema]** volet de gauche et le **[!UICONTROL Dashboard Schema]** volet de droite. Ce résumé s’affiche dans la partie inférieure gauche de la **[!UICONTROL Schema Builder]** fenêtre.

   >[!NOTE]
   >
   >Lors de la configuration initiale du schéma, chaque mesure, dimension et filtre est répertorié différemment du schéma du tableau de bord. En effet, les objets de schéma de tableau de bord n’existent pas pour le moment.

   ![](assets/schema_builder2.png)

1. Cliquez sur le **[!UICONTROL Synchronize with Schema]** bouton pour synchroniser toutes les mesures, dimensions et filtres de la vue Schéma Insight avec la vue Schéma du tableau de bord.
1. Une fois l’opération terminée, vous devriez voir un message indiquant qu’aucune différence n’a été trouvée :

   ![](assets/diff_found.png)

1. Si le schéma du tableau de bord comporte des erreurs (mesures et dimensions en double, par exemple), vous devez les corriger manuellement avant de pouvoir les enregistrer.

   >[!NOTE]
   >
   >Vous pouvez supprimer de manière sélective toutes les mesures, dimensions ou filtres du tableau de **[!UICONTROL Dashboard Schema]** bord que vous ne souhaitez pas afficher aux utilisateurs finaux. Vous recevrez un avertissement indiquant que les éléments ne sont pas présents dans le schéma du tableau de bord, mais cela ne vous empêchera pas d’enregistrer.

1. Une fois prêt, cliquez **[!UICONTROL Save]** pour enregistrer vos modifications dans le schéma du tableau de bord.
1. Le système de tableaux de bord utilisera cette définition de schéma pour renseigner les dimensions, les mesures et les filtres disponibles pour les utilisateurs finaux de l’interface du tableau de bord.
