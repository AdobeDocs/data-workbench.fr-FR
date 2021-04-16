---
description: L’application cliente de l’outil de données prend désormais en charge le chinois simplifié.
title: Localisation en chinois simplifié
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# Localisation en chinois simplifié{#simplified-chinese-localization}

L’application cliente de l’outil de données prend désormais en charge le chinois simplifié.

**Pour installer le chinois** simplifié :

Avant de configurer [!DNL Insight.exe] et les fichiers de prise en charge, vous devez quitter l’application cliente.

1. Créez un raccourci qui passe dans le paramètre de ligne de commande au fichier [!DNL insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configurez [!DNL Insight.cfg] pour qu’il prenne en charge les caractères de police sur un et doublon octet.

   Les outils de données prennent actuellement en charge l’anglais et le chinois simplifié. Vous pouvez sélectionner des polices pour les deux langues suivantes :

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Redémarrer [!DNL Insight.exe].

