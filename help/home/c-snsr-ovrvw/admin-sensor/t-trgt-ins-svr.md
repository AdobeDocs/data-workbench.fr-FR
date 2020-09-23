---
description: Pour modifier le serveur d’outils de données avec lequel un capteur communique (le serveur de cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs Web sur lesquels Sensor est installé.
solution: Analytics
title: Modification du serveur Data Workbench cible
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---


# Modification du serveur Data Workbench cible{#changing-the-target-data-workbench-server}

Pour modifier le serveur d’outils de données avec lequel un capteur communique (le serveur de cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs Web sur lesquels Sensor est installé.

**Pour passer à la cible[!DNL data workbench server]**

1. Arrêtez à la fois le serveur de cible d’origine et le nouveau serveur de cible.
1. Copiez le [!DNL .vsl] fichier le plus récent du serveur de cibles d’origine sur le nouveau serveur de cibles. Lorsque vous redémarrez le nouveau serveur de cibles à une étape ultérieure, toutes les nouvelles données [!DNL Sensor] sont ajoutées au [!DNL .vsl] fichier existant actuel au lieu de créer un nouveau [!DNL .vsl] fichier. Pour ce faire, procédez comme suit :

   1. Sur le serveur de cible d’origine, accédez au [!DNL \Logs] dossier situé dans le répertoire [!DNL data workbench server] d’installation.

   1. Copiez le [!DNL .vsl] fichier le plus récent du dossier.
   1. Sur le nouveau serveur de cibles, recherchez le [!DNL \Logs] dossier situé dans le répertoire [!DNL data workbench server] d’installation et collez le [!DNL .vsl] fichier dans ce dossier.

1. Sur l’un des serveurs Web sur lesquels [!DNL Sensor] est installé, ouvrez et modifiez le [!DNL txlogd.conf] fichier. Pour ce faire, procédez comme suit :

   1. Accédez au répertoire [!DNL Sensor] d’installation et ouvrez le [!DNL txlogd.conf] fichier dans un éditeur de texte.

   1. Recherchez le paramètre ServerAddress et modifiez-le pour refléter l’adresse du nouveau serveur de cibles.
   1. Enregistrez et fermez le fichier.

1. Répétez les étapes 2 à 3 sur tous les autres serveurs Web sur lesquels [!DNL Sensor] est installé.
1. Redémarrez le serveur de cible d’origine (s’il doit encore être utilisé) et le nouveau serveur de cible.
1. Les données commenceront à être transmises au nouveau serveur de cibles que vous avez spécifié.
