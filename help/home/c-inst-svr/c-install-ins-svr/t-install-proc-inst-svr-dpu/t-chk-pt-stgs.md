---
description: Par défaut, Insight Server écoute les ports 80 (pour HTTP) et 443 (pour HTTPS).
solution: Insight
title: Vérification des paramètres de port
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vérification des paramètres de port{#checking-the-port-settings}

Par défaut, Insight Server écoute les ports 80 (pour HTTP) et 443 (pour HTTPS).

Si ces ports sont déjà alloués par un autre processus sur l&#39;ordinateur sur lequel vous avez installé [!DNL Insight Server], procédez comme suit pour modifier les affectations de [!DNL Insight Server’s] port.

**Pour modifier les affectations de port**

1. Accédez au [!DNL Components] dossier du répertoire dans lequel vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Ouvrez le [!DNL Communications.cfg] fichier dans un éditeur de texte tel que le Bloc-notes.
1. Localisez le port et les entrées de port SSL, comme illustré ci-dessous :

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

1. S&#39;il ne s&#39;agit pas des ports que vous souhaitez [!DNL Insight Server] utiliser, modifiez les affectations de ports, puis enregistrez et fermez le fichier.
