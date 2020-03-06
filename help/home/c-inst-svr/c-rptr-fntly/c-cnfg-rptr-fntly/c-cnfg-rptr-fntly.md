---
description: La fonctionnalité Répéter permet à un FSU de serveur Insight de recevoir les données d’événement acquises par Sensor d’une ou de plusieurs sources et de répliquer les données sur un ou plusieurs FSU de serveur Insight exécutant le service de réplication de serveur Insight.
solution: Insight
title: Configuration de la fonctionnalité Répéter
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de la fonctionnalité Répéter{#configuring-repeater-functionality}

La fonctionnalité Répéter permet à un FSU de serveur Insight de recevoir les données d’événement acquises par Sensor d’une ou de plusieurs sources et de répliquer les données sur un ou plusieurs FSU de serveur Insight exécutant le service de réplication de serveur Insight.

Voir Service [de réplication](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)Insight Server. Cette fonctionnalité permet la réplication des données vers des installations redondantes à des fins de reprise après sinistre. Les serveurs cible agissent comme des clients réseau, se connectant au FSU source pour demander des copies des données d’événement pour les inclure dans plusieurs jeux de données.

Vous pouvez utiliser la fonctionnalité de répéteur dans les infrastructures réseau avec plusieurs couches de pare-feu pour obtenir des communications de port unique à port unique entre des composants séparés par des pare-feu.

Pour plus d’informations sur la configuration système requise pour l’installation, la configuration et le fonctionnement [!DNL Repeater], voir le document Configuration système requise ** minimale.

Pour installer [!DNL Repeater], vous devez effectuer les étapes répertoriées pour les deux procédures suivantes :

* [Configuration d’un FSU de serveur Insight pour Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configuration du contrôle d’accès pour les machines Target](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Si les pare-feu réseau permettent d’accéder à votre [!DNL Repeater] application à partir de [!DNL Insight], vous pouvez créer une connexion comme décrit dans [Création d’une connexion entre Insight et Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
