---
description: Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de test en plus de la population témoin.
solution: Analytics
title: Comment les expériences contrôlées fonctionnent-elles ?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Comment les expériences contrôlées fonctionnent-elles ?{#how-do-controlled-experiments-work}

{{eol}}

Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de test en plus de la population témoin.

Lorsqu’une expérience est en cours, tous les visiteurs de votre site web deviennent membres de l’expérience, que ce soit dans le cadre d’un groupe de test ou d’un groupe témoin, dès qu’ils accèdent à une page impliquée dans l’expérience. Les visiteurs sont affectés de manière aléatoire à vos groupes d’expériences, selon des proportions définies lors de la configuration de l’expérience.

Les expériences contrôlées sont mises en oeuvre à l’aide de la méthode [!DNL Sensor] logiciel installé sur chacun des serveurs de contenu de votre grappe web. Lorsque les serveurs de contenu reçoivent des demandes, [!DNL Sensor] sélectionne de manière aléatoire les visiteurs de vos groupes de test et redirige leurs requêtes de page vers le contenu expérimental. When [!DNL Sensor] sélectionne un visiteur pour afficher le contenu du test, la barre d’adresses continue à répertorier l’URI initialement demandé, mais le visiteur est redirigé vers l’URI de test. Ce processus se déroulant en interne dans l’application serveur, les utilisateurs ne sont pas conscients du moment où ils sont testés, ce qui est une considération importante pour l’expérimentation impartiale.

[!DNL Sensor] transmet les URI de test, et non l’URI d’origine affiché pour l’utilisateur, aux fichiers journaux à utiliser dans l’analyse.

Les résultats des expériences peuvent être facilement analysés à l’aide de [!DNL Insight] pour déterminer si l’hypothèse expérimentale que vous avez testée est correcte.

>[!NOTE]
>
>Adobe recommande vivement que les expériences contrôlées soient coordonnées et exécutées avec l’entrée des personnes de votre entreprise chargées de configurer et de gérer vos jeux de données d’analyse.
