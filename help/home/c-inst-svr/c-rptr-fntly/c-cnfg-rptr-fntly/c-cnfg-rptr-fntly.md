---
description: La fonctionnalité Répéteur permet à un FSU de serveur Insight de recevoir les données d’événement acquises par Capteur d’une ou plusieurs sources et de répliquer les données sur un ou plusieurs FSU de serveur Insight exécutant le service de réplication de serveur Insight.
title: Configuration de la fonctionnalité Répéteur
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Configuration de la fonctionnalité Répéteur{#configuring-repeater-functionality}

{{eol}}

La fonctionnalité Répéteur permet à un FSU de serveur Insight de recevoir les données d’événement acquises par Capteur d’une ou plusieurs sources et de répliquer les données sur un ou plusieurs FSU de serveur Insight exécutant le service de réplication de serveur Insight.

Voir [Service de réplication du serveur Insight](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Cette fonctionnalité permet la réplication des données vers des installations redondantes à des fins de reprise sur sinistre. Les serveurs cibles agissent comme des clients réseau, se connectant au FSU source pour demander des copies des données d’événement à inclure dans plusieurs jeux de données.

Vous pouvez utiliser la fonctionnalité de répéteur dans les infrastructures réseau avec plusieurs couches de pare-feu pour établir des communications entre des composants séparés par des pare-feu à port unique et à port unique.

Pour plus d’informations sur la configuration système requise pour l’installation, la configuration et le fonctionnement [!DNL Repeater], reportez-vous à la section *Configuration système minimale* document.

Pour installer [!DNL Repeater], vous devez effectuer les étapes répertoriées pour les deux procédures suivantes :

* [Configuration d’un FSU de serveur Insight pour Répéteur](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configuration du contrôle d’accès pour les machines cibles](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Si les pare-feu réseau permettent d’accéder à [!DNL Repeater] de [!DNL Insight], vous pouvez créer une connexion comme décrit dans la section [Création d’une connexion entre Insight et Répéteur](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
