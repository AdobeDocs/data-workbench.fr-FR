---
description: Pour modifier le serveur d’outils de données avec lequel un capteur communique (le serveur de cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs Web sur lesquels Sensor est installé.
title: Modification du serveur Data Workbench cible
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Modification du serveur Data Workbench cible{#changing-the-target-data-workbench-server}

Pour modifier le serveur d’outils de données avec lequel un capteur communique (le serveur de cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs Web sur lesquels Sensor est installé.

**Pour passer à la cible[!DNL data workbench server]**

1. Arrêtez à la fois le serveur de cible d’origine et le nouveau serveur de cible.
1. Copiez le fichier [!DNL .vsl] le plus récent du serveur de cible d’origine sur le nouveau serveur de cible. Lorsque vous redémarrez le nouveau serveur de cibles à une étape ultérieure, toutes les nouvelles données [!DNL Sensor] sont ajoutées au fichier [!DNL .vsl] existant actuel au lieu de créer un nouveau fichier [!DNL .vsl]. Pour ce faire, procédez comme suit :

   1. Sur le serveur de cible d’origine, accédez au dossier [!DNL \Logs] dans le répertoire d’installation de [!DNL data workbench server].

   1. Copiez le fichier [!DNL .vsl] le plus récent du dossier.
   1. Sur le nouveau serveur de cibles, recherchez le dossier [!DNL \Logs] dans le répertoire d&#39;installation de [!DNL data workbench server] et collez le fichier [!DNL .vsl] dans ce dossier.

1. Sur l’un des serveurs Web sur lesquels [!DNL Sensor] est installé, ouvrez et modifiez le fichier [!DNL txlogd.conf]. Pour ce faire, procédez comme suit :

   1. Accédez au répertoire d&#39;installation de [!DNL Sensor] et ouvrez le fichier [!DNL txlogd.conf] dans un éditeur de texte.

   1. Recherchez le paramètre ServerAddress et modifiez-le pour refléter l’adresse du nouveau serveur de cibles.
   1. Enregistrez et fermez le fichier.

1. Répétez les étapes 2 à 3 sur tous les serveurs Web restants sur lesquels [!DNL Sensor] est installé.
1. Redémarrez le serveur de cible d’origine (s’il doit encore être utilisé) et le nouveau serveur de cible.
1. Les données commenceront à être transmises au nouveau serveur de cibles que vous avez spécifié.
