---
description: Le fichier de configuration de Sensor, txlogd.conf, contient les paramètres utilisés par Sensor pour établir une connexion avec le serveur de l’outil de données.
solution: Insight
title: Modification du fichier txlogd.conf de Sensor
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Modification du fichier txlogd.conf de Sensor{#editing-the-sensor-txlogd-conf-file}

Le fichier de configuration de Sensor, txlogd.conf, contient les paramètres utilisés par Sensor pour établir une connexion avec le serveur de l’outil de données.

Ces paramètres comprennent l’adresse du serveur, le numéro de port et le protocole de communication (HTTP ou HTTPS). Le fichier de configuration contient également des options de filtrage du contenu du journal et des informations d’expérience contrôlée. Les expériences contrôlées permettent aux concepteurs du site d’effectuer des expériences afin de tester le contenu ou de concevoir des modifications sur un sous-ensemble de tous les visiteurs du site.

Lorsque vous modifiez d&#39;autres [!DNL txlogd.conf] paramètres, tels que l&#39;adresse IP du [!DNL data workbench server] ou le nom du [!DNL Sensor], vous pouvez simplement remplacer [!DNL txlogd.conf] par la version mise à jour et [!DNL Sensor] récupérer les modifications automatiquement. Sur certains systèmes, il est possible que vous ne puissiez pas modifier ou remplacer le fichier sans arrêter le serveur Web ou le processus d’émetteur.

**Pour ouvrir et modifier txlogd.conf**

1. Accédez au répertoire [!DNL Sensor] d’installation et ouvrez le [!DNL txlogd.conf] fichier dans un éditeur de texte.
1. Modifiez le fichier selon vos besoins.
1. Enregistrez et fermez le fichier.

   * L’emplacement du fichier de configuration d’expérience contrôlée (défini par le paramètre ExpFile dans le [!DNL txlogd.conf] fichier) doit se trouver dans un répertoire du serveur Web accessible aux développeurs de contenu Web ou contrôlé par votre système de gestion de contenu.
   * La valeur du paramètre ExpCookieURL est une page virtuelle utilisée pour tester des sites Web. Un nouvel ID de suivi sera attribué à un utilisateur visitant cette page.

Pour plus d’informations sur la manière de travailler avec [!DNL txlogd.conf], contactez les services de conseil Adobe.
