---
description: Pour modifier le serveur Data Workbench avec lequel un capteur communique (le serveur cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs web sur lesquels le capteur est installé.
title: Modification du serveur Data Workbench cible
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Modification du serveur Data Workbench cible{#changing-the-target-data-workbench-server}

Pour modifier le serveur Data Workbench avec lequel un capteur communique (le serveur cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs web sur lesquels le capteur est installé.

**Pour changer de cible[!DNL data workbench server]**

1. Arrêtez le serveur cible d’origine et le nouveau serveur cible.
1. Copiez le fichier [!DNL .vsl] le plus récent du serveur cible d’origine vers le nouveau serveur cible. Lorsque vous redémarrez le nouveau serveur cible à une étape ultérieure, toutes les nouvelles données [!DNL Sensor] sont alors ajoutées au fichier [!DNL .vsl] existant au lieu de créer un nouveau fichier [!DNL .vsl]. Pour ce faire, procédez comme suit :

   1. Sur le serveur cible d’origine, accédez au dossier [!DNL \Logs] dans le répertoire d’installation de [!DNL data workbench server].

   1. Copiez le fichier [!DNL .vsl] le plus récent du dossier.
   1. Sur le nouveau serveur cible, accédez au dossier [!DNL \Logs] dans le répertoire d’installation de [!DNL data workbench server] et collez le fichier [!DNL .vsl] dans ce dossier.

1. Sur l’un des serveurs Web sur lequel [!DNL Sensor] est installé, ouvrez et modifiez le fichier [!DNL txlogd.conf]. Pour ce faire, procédez comme suit :

   1. Accédez au répertoire d’installation de [!DNL Sensor] et ouvrez le fichier [!DNL txlogd.conf] dans un éditeur de texte.

   1. Localisez le paramètre ServerAddress et modifiez-le pour refléter l’adresse du nouveau serveur cible.
   1. Enregistrez le fichier, puis fermez-le.

1. Répétez les étapes 2 à 3 sur tous les serveurs web restants sur lesquels [!DNL Sensor] est installé.
1. Redémarrez le serveur cible d&#39;origine (s&#39;il doit encore être utilisé) et le nouveau serveur cible.
1. Les données commenceront à être transmises au nouveau serveur cible que vous avez spécifié.
