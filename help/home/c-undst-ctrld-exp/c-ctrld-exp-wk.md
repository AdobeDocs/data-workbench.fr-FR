---
description: Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de test en plus du groupe de contrôle.
solution: Insight,Analytics
title: Comment fonctionnent les expériences contrôlées ?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comment fonctionnent les expériences contrôlées ?{#how-do-controlled-experiments-work}

Dans une expérience, vous pouvez définir n’importe quel nombre de groupes de test en plus du groupe de contrôle.

Lorsqu’une expérience est en cours, tous les visiteurs de votre site Web font partie de l’expérience, soit dans le cadre d’un groupe de test, soit dans le cadre d’un groupe de contrôle, dès qu’ils accèdent à une page impliquée dans l’expérience. Les visiteurs sont affectés de manière aléatoire à vos groupes d’expériences, selon des proportions définies lors de la configuration de l’expérience.

Les expériences contrôlées sont implémentées à l’aide du [!DNL Sensor] logiciel installé sur chacun des serveurs de contenu de votre grappe Web. Lorsque les serveurs de contenu reçoivent des requêtes, sélectionne [!DNL Sensor] de manière aléatoire les visiteurs de vos groupes de tests et redirige leurs requêtes de page vers le contenu expérimental. Lorsque [!DNL Sensor] sélectionne un visiteur pour afficher le contenu du test, la barre d’adresse continue à répertorier l’URI initialement demandé, mais le visiteur est dirigé vers l’URI du test. Ce processus se déroulant en interne dans l’application serveur, les utilisateurs ne sont pas conscients du moment où ils sont testés, ce qui est une considération importante pour une expérimentation impartiale.

[!DNL Sensor] transmet les URI de test, et non l’URI d’origine affiché à l’utilisateur, aux fichiers journaux en vue de les utiliser dans l’analyse.

Les résultats des expériences peuvent être facilement analysés en utilisant [!DNL Insight] pour déterminer si l&#39;hypothèse expérimentale que vous testiez est correcte.

>[!NOTE]
>
>Adobe recommande vivement que les expériences contrôlées soient coordonnées et exécutées avec l’apport des personnes de votre entreprise chargées de configurer et de gérer vos jeux de données d’analyse.

