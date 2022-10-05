---
description: Guide rapide relatif aux étapes minimales requises pour valider et configurer des flux de données historiques.
title: Validation des flux de données historiques
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# Validation des flux de données historiques{#validating-historical-data-feeds}

{{eol}}

Guide rapide relatif aux étapes minimales requises pour valider et configurer des flux de données historiques.

## Étapes de validation de la cohérence des flux de données {#section-777b2c627a354627a02feb9461e23038}

1. Connectez-vous à *dreth* (https://oasis.omniture.com/drteeth/)
1. Accédez à Administration des SiteCatalysts -> Définition des flux de données (nouveau).
1. Accédez à l’emplacement du serveur (par exemple Dallas, Londres...) Selon l’emplacement de votre entreprise.
1. Fournissez le RSID et sélectionnez le type de flux Insight , puis cliquez sur *search*.

   ![](assets/dwb_impl_historical.png)

1. Identifiez le nom réel du flux pour votre client.
1. Cliquez sur Historique dans la section Actions . ![](assets/dwb_impl_historical1.png)

   Recherchez des erreurs dans le champ d’état. Dans le cas où un flux est en état d’erreur, sélectionnez-le et cliquez sur retraiter. Si l’erreur s’est produite pour plusieurs requêtes, envoyez un courrier électronique à *`dataworkbench@adobe.com`* avec les détails Identifiant du flux et Suite de rapports à retraiter.

1. La post-validation vérifie les journaux dans le dossier brut de l’emplacement NAS.
