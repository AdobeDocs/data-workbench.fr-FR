---
description: La fonctionnalité Repeater permet à un FSU d’Insight Server de recevoir des données de événement acquises par Sensor à partir d’une ou de plusieurs sources et de répliquer les données sur un ou plusieurs FSU d’Insight Server exécutant le service de réplication d’Insight Server.
title: Configuration de la fonctionnalité Répéteur
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Configuration de la fonctionnalité Répéteur{#configuring-repeater-functionality}

La fonctionnalité Repeater permet à un FSU d’Insight Server de recevoir des données de événement acquises par Sensor à partir d’une ou de plusieurs sources et de répliquer les données sur un ou plusieurs FSU d’Insight Server exécutant le service de réplication d’Insight Server.

Voir [Service de réplication du serveur Insight](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Cette fonctionnalité permet la réplication des données vers des installations redondantes à des fins de reprise après sinistre. Les serveurs de cible agissent en tant que clients réseau, se connectant au FSU source pour demander des copies des données du événement à inclure dans plusieurs jeux de données.

Vous pouvez utiliser la fonctionnalité de répéteur dans les infrastructures réseau avec plusieurs couches de pare-feu pour obtenir des communications à port unique entre des composants séparés par des pare-feu.

Pour plus d&#39;informations sur la configuration système requise pour l&#39;installation, la configuration et l&#39;exploitation de [!DNL Repeater], consultez le document *Configuration minimale requise*.

Pour installer [!DNL Repeater], vous devez exécuter les étapes indiquées pour les deux procédures suivantes :

* [Configuration d’un FSU de serveur Insight pour Répéteur](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configuration du contrôle d’accès pour les machines cibles](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Si les pare-feu réseau permettent d&#39;accéder à [!DNL Repeater] à partir de [!DNL Insight], vous pouvez créer une connexion comme décrit dans [Création d&#39;une connexion entre Insight et Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
