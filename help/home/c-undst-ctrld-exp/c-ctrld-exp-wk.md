---
description: Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de tests en plus de la Population témoin.
solution: Analytics,Analytics
title: Comment les expériences contrôlées fonctionnent-elles ?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---


# Comment les expériences contrôlées fonctionnent-elles ?{#how-do-controlled-experiments-work}

Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de tests en plus de la Population témoin.

Lorsqu&#39;une expérience est en cours, tous les visiteurs de votre site Web font partie de l&#39;expérience, que ce soit dans le cadre d&#39;un groupe de test ou de la Population témoin, dès qu&#39;ils accèdent à une page de l&#39;expérience. Les visiteurs sont répartis aléatoirement sur vos groupes d’expériences, en proportions définies lors de la configuration de l’expérience.

Les expériences contrôlées sont mises en oeuvre à l’aide du [!DNL Sensor] logiciel installé sur chacun des serveurs de contenu de votre grappe Web. À mesure que les serveurs de contenu reçoivent des requêtes, sélectionne [!DNL Sensor] de manière aléatoire les visiteurs de vos groupes de tests et redirige leurs requêtes de page vers le contenu expérimental. Lorsque [!DNL Sensor] sélectionne un visiteur pour vue du contenu du test, la barre d’adresse continue à liste l’URI initialement demandé, mais le visiteur est acheminé vers l’URI de test. Ce processus se déroulant en interne dans l’application serveur, les utilisateurs n’ont pas connaissance du moment où ils sont testés, ce qui est une considération importante pour une expérimentation impartiale.

[!DNL Sensor] transmet les URI de test, et non l’URI d’origine affiché à l’utilisateur, aux fichiers journaux pour utilisation en analyse.

Les résultats des expériences peuvent être analysés facilement en utilisant [!DNL Insight] pour déterminer si l&#39;hypothèse expérimentale que vous testiez est correcte.

>[!NOTE]
>
>L&#39;Adobe recommande vivement que les expériences contrôlées soient coordonnées et exécutées avec l&#39;apport des personnes de votre organisation qui sont responsables de la configuration et de la maintenance de vos jeux de données d&#39;analyse.

