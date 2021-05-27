---
description: Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de test en plus de la population témoin.
solution: Analytics,Analytics
title: Comment les expériences contrôlées fonctionnent-elles ?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Comment les expériences contrôlées fonctionnent-elles ?{#how-do-controlled-experiments-work}

Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de test en plus de la population témoin.

Lorsqu’une expérience est en cours, tous les visiteurs de votre site web deviennent membres de l’expérience, que ce soit dans le cadre d’un groupe de test ou d’un groupe témoin, dès qu’ils accèdent à une page impliquée dans l’expérience. Les visiteurs sont affectés de manière aléatoire à vos groupes d’expériences, selon des proportions définies lors de la configuration de l’expérience.

Les expériences contrôlées sont mises en oeuvre à l’aide du logiciel [!DNL Sensor] installé sur chacun des serveurs de contenu de votre grappe web. À mesure que les serveurs de contenu reçoivent des requêtes, [!DNL Sensor] sélectionne de manière aléatoire les visiteurs de vos groupes de test et redirige leurs requêtes de page vers le contenu expérimental. Lorsque [!DNL Sensor] sélectionne un visiteur pour afficher le contenu du test, la barre d’adresse continue à répertorier l’URI initialement demandé, mais le visiteur est acheminé vers l’URI de test. Ce processus se déroulant en interne dans l’application serveur, les utilisateurs ne sont pas conscients du moment où ils sont testés, ce qui est une considération importante pour l’expérimentation impartiale.

[!DNL Sensor] transmet les URI de test, et non l’URI d’origine affiché pour l’utilisateur, aux fichiers journaux à utiliser dans l’analyse.

Les résultats des expériences peuvent être facilement analysés à l’aide de [!DNL Insight] pour déterminer si l’hypothèse expérimentale que vous avez testée est correcte.

>[!NOTE]
>
>Adobe recommande vivement que les expériences contrôlées soient coordonnées et exécutées avec l’entrée des personnes de votre entreprise chargées de configurer et de gérer vos jeux de données d’analyse.
