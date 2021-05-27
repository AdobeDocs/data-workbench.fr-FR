---
description: L’application cliente Data Workbench prend désormais en charge le chinois simplifié.
title: Localisation du chinois simplifié
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# Localisation en chinois simplifié{#simplified-chinese-localization}

L’application cliente Data Workbench prend désormais en charge le chinois simplifié.

**Pour installer le chinois** simplifié :

Avant de configurer [!DNL Insight.exe] et les fichiers annexes, vous devez quitter l’application cliente.

1. Créez un raccourci qui transmet le paramètre de ligne de commande au fichier [!DNL insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configurez [!DNL Insight.cfg] pour prendre en charge les caractères de police à un et deux octets.

   Data Workbench prend actuellement en charge le chinois simplifié et l’anglais. Vous pouvez sélectionner des polices pour prendre en charge ces deux langues :

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Redémarrer [!DNL Insight.exe].

