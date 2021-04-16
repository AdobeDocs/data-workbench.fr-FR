---
description: Par défaut, Insight Server écoute les ports 80 (HTTP) et 443 (HTTPS).
title: Vérification des paramètres de port
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# Vérification des paramètres de port{#checking-the-port-settings}

Par défaut, Insight Server écoute les ports 80 (HTTP) et 443 (HTTPS).

Si ces ports sont déjà alloués par un autre processus sur l&#39;ordinateur sur lequel vous avez installé [!DNL Insight Server], utilisez la procédure suivante pour modifier les affectations de port [!DNL Insight Server’s].

**Pour modifier les affectations de port**

1. Accédez au dossier [!DNL Components] dans le répertoire où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Ouvrez le fichier [!DNL Communications.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Recherchez les entrées Port et Port SSL, comme indiqué ci-dessous :

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. S&#39;il ne s&#39;agit pas des ports que [!DNL Insight Server] doit utiliser, modifiez les affectations de port, puis enregistrez et fermez le fichier.
