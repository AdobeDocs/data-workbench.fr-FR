---
description: L’application cliente de l’outil de données prend désormais en charge le chinois simplifié.
solution: Analytics
title: Localisation en chinois simplifié
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Localisation en chinois simplifié{#simplified-chinese-localization}

L’application cliente de l’outil de données prend désormais en charge le chinois simplifié.

**Pour installer le chinois** simplifié :

Avant de configurer [!DNL Insight.exe] et de prendre en charge les fichiers, vous devez quitter l’application cliente.

1. Créez un raccourci qui transmet le paramètre de ligne de commande au [!DNL insight.exe] fichier.

   ```
   Insight.exe -zh-cn
   ```

1. Configurez [!DNL Insight.cfg] pour prendre en charge les caractères de police sur un et deux octets.

   Les outils de données prennent actuellement en charge l’anglais et le chinois simplifié. Vous pouvez sélectionner des polices pour prendre en charge les deux langues suivantes :

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Redémarrer [!DNL Insight.exe].

