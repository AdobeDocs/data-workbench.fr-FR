---
description: Le fichier de configuration de Sensor, txlogd.conf, contient les paramètres utilisés par Sensor pour établir une connexion avec le serveur de l’outil de données.
title: Modification du fichier txlogd.conf de Capteur
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Modification du fichier txlogd.conf de Capteur{#editing-the-sensor-txlogd-conf-file}

Le fichier de configuration de Sensor, txlogd.conf, contient les paramètres utilisés par Sensor pour établir une connexion avec le serveur de l’outil de données.

Ces paramètres comprennent l’adresse du serveur, le numéro de port et le protocole de communication (HTTP ou HTTPS). Le fichier de configuration contient également des options de filtrage du contenu du journal et des informations d’expérience contrôlées. Les expériences contrôlées permettent aux concepteurs du site d&#39;effectuer des expériences pour tester le contenu ou les modifications de conception sur un sous-ensemble de tous les visiteurs du site.

Lorsque vous modifiez d&#39;autres paramètres [!DNL txlogd.conf], tels que l&#39;adresse IP de [!DNL data workbench server] ou le nom de [!DNL Sensor], vous pouvez simplement remplacer [!DNL txlogd.conf] par la version mise à jour et [!DNL Sensor] récupère automatiquement les modifications. Sur certains systèmes, il est possible que vous ne puissiez pas modifier ou remplacer le fichier sans arrêter le serveur Web ou le processus de l’émetteur.

**Pour ouvrir et modifier txlogd.conf**

1. Accédez au répertoire d&#39;installation de [!DNL Sensor] et ouvrez le fichier [!DNL txlogd.conf] dans un éditeur de texte.
1. Modifiez le fichier si nécessaire.
1. Enregistrez et fermez le fichier.

   * L&#39;emplacement du fichier de configuration d&#39;expérience contrôlée (défini par le paramètre ExpFile dans le fichier [!DNL txlogd.conf]) doit se trouver dans un répertoire du serveur Web accessible aux développeurs de contenu Web ou contrôlé par votre système de gestion de contenu.
   * La valeur du paramètre ExpCookieURL est une page virtuelle utilisée pour tester les sites Web. Un nouvel ID de suivi sera attribué à un utilisateur visitant cette page.

Pour plus d&#39;informations sur l&#39;utilisation de [!DNL txlogd.conf], veuillez contacter les Services de conseil en Adobe.
