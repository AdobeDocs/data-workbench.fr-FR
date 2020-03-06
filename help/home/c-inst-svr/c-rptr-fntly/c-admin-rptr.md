---
description: Les tâches d’administration de la fonctionnalité de répéteur sont très similaires à celles d’Insight Server.
solution: Insight
title: Administration du répéteur
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Administration du répéteur{#administering-repeater}

Les tâches d’administration de la fonctionnalité de répéteur sont très similaires à celles d’Insight Server.

Les tâches administratives suivantes s&#39;appliquent; les exceptions ou modifications que vous devez apporter afin que le [!DNL Insight Server] DPU puisse être utilisé avec le serveur de répétition sont notées après chaque étape.

* [Nouvelle validation du certificat numérique](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Confirmation de l’exécution](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) du service Dans la liste des services du panneau de configuration Services, recherchez &quot;Répéteur&quot;.

* [Configuration du contrôle d&#39;accès](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Surveillance de l&#39;espace disque](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) Les types de données qui s&#39;appliquent au serveur répéteur sont les données d&#39;événement, de système d&#39;exploitation et de système. Si vous utilisez le serveur de répétition pour le stockage de sauvegarde et qu’il devient nécessaire de libérer de l’espace de stockage de données sur l’ordinateur, vous pouvez déplacer tous les fichiers journaux de la journée, à l’exception des fichiers les plus récents, vers un autre ordinateur ou un autre support de stockage de données (lecteur zip, bande, etc.). Le déplacement des données n’exige pas que vous arrêtiez le service de répéteur.

   >[!NOTE]
   >
   >Vous devez vérifier l’intégrité des copies de sauvegarde de vos [!DNL .vsl] fichiers avant de les supprimer de Repeater.

* [Configuration des alertes administratives](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Contrôle des événements administratifs](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Surveillance des journaux d’audit](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Configuration des communications](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Le redémarrage de la fonctionnalité Service](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)[!DNL Repeater] est conçu pour s’exécuter en continu. Si vous redémarrez l’ordinateur, le répéteur redémarre automatiquement. Si vous devez démarrer et arrêter manuellement le répéteur, vous pouvez le faire à l’aide du panneau de configuration Services de Windows.

