---
description: Pour modifier le serveur de l’outil de données avec lequel un capteur communique (le serveur cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs Web sur lesquels Sensor est installé.
solution: Insight
title: Modification du serveur Target Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du serveur Target Data Workbench{#changing-the-target-data-workbench-server}

Pour modifier le serveur de l’outil de données avec lequel un capteur communique (le serveur cible), vous devez modifier le fichier txlogd.conf sur chacun des serveurs Web sur lesquels Sensor est installé.

**Pour changer en cible[!DNL data workbench server]**

1. Arrêtez le serveur cible d’origine et le nouveau serveur cible.
1. Copiez le [!DNL .vsl] fichier le plus récent du serveur cible d’origine vers le nouveau serveur cible. Lorsque vous redémarrez le nouveau serveur cible à une étape ultérieure, toutes les nouvelles [!DNL Sensor] données sont ajoutées au [!DNL .vsl] fichier existant actuel au lieu de créer un nouveau [!DNL .vsl] fichier. Pour ce faire, procédez comme suit :

   1. Sur le serveur cible d’origine, accédez au [!DNL \Logs] dossier du répertoire [!DNL data workbench server] d’installation.

   1. Copiez le [!DNL .vsl] fichier le plus récent du dossier.
   1. Sur le nouveau serveur cible, accédez au [!DNL \Logs] dossier du répertoire [!DNL data workbench server] d’installation et collez le [!DNL .vsl] fichier dans ce dossier.

1. Sur l’un des serveurs Web sur lesquels [!DNL Sensor] est installé, ouvrez et modifiez le [!DNL txlogd.conf] fichier. Pour ce faire, procédez comme suit :

   1. Accédez au répertoire [!DNL Sensor] d’installation et ouvrez le [!DNL txlogd.conf] fichier dans un éditeur de texte.

   1. Localisez le paramètre ServerAddress et modifiez-le pour refléter l’adresse du nouveau serveur cible.
   1. Enregistrez et fermez le fichier.

1. Répétez les étapes 2 à 3 sur tous les autres serveurs Web sur lesquels [!DNL Sensor] est installé.
1. Redémarrez le serveur cible d’origine (s’il doit encore être utilisé) et le nouveau serveur cible.
1. Les données commencent à être transmises au nouveau serveur cible que vous avez spécifié.
