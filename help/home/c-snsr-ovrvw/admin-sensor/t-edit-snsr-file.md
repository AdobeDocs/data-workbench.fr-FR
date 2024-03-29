---
description: Le fichier de configuration de Capteur, txlogd.conf, contient les paramètres utilisés par Capteur pour établir une connexion avec le serveur Data Workbench.
title: Modification du fichier txlogd.conf de Capteur
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Modification du fichier txlogd.conf de Capteur{#editing-the-sensor-txlogd-conf-file}

{{eol}}

Le fichier de configuration de Capteur, txlogd.conf, contient les paramètres utilisés par Capteur pour établir une connexion avec le serveur Data Workbench.

Ces paramètres comprennent l’adresse, le numéro de port et le protocole de communication du serveur (HTTP ou HTTPS). Le fichier de configuration contient également des options de filtrage du contenu du journal et des informations d’expérience contrôlées. Les expériences contrôlées permettent aux concepteurs de site d’effectuer des expériences afin de tester le contenu ou de concevoir des modifications sur un sous-ensemble de tous les visiteurs du site.

Lors de la modification d’autres [!DNL txlogd.conf] , par exemple, l’adresse IP de la variable [!DNL data workbench server] ou le nom de la variable [!DNL Sensor], vous pouvez simplement remplacer [!DNL txlogd.conf] avec la version mise à jour et [!DNL Sensor] récupère automatiquement les modifications. Sur certains systèmes, il se peut que vous ne puissiez pas modifier ou remplacer le fichier sans arrêter le serveur web ou le processus de l&#39;émetteur.

**Pour ouvrir et modifier txlogd.conf**

1. Accédez au [!DNL Sensor] répertoire d’installation et ouvrez la [!DNL txlogd.conf] dans un éditeur de texte.
1. Modifiez le fichier selon vos besoins.
1. Enregistrez le fichier, puis fermez-le.

   * L’emplacement du fichier de configuration de l’expérience contrôlée (défini par le paramètre ExpFile dans la variable [!DNL txlogd.conf] ) doit se trouver dans un répertoire du serveur web accessible aux développeurs de contenu web ou contrôlé par votre système de gestion de contenu.
   * La valeur du paramètre ExpCookieURL est une page virtuelle utilisée pour tester les sites web. Un nouvel ID de suivi sera attribué à un utilisateur qui consulte cette page.

Pour plus d’informations sur l’utilisation de [!DNL txlogd.conf], veuillez contacter les services de conseil d’Adobe.
