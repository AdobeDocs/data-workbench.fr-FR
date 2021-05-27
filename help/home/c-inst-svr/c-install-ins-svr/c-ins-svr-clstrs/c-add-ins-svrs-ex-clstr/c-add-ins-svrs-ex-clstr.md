---
description: Dans certains cas, il peut s’avérer nécessaire d’ajouter une machine de serveur Insight à une grappe de serveurs Insight existante.
title: Ajout de serveurs Insight à un cluster existant
uuid: 951bd6fe-14e4-4192-917c-342fde7b43ba
exl-id: 9845c13b-781c-43e9-aaa1-e31418c93ef0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 12%

---

# Ajout de serveurs Insight à un cluster existant{#adding-insight-servers-to-an-existing-cluster}

Dans certains cas, il peut s’avérer nécessaire d’ajouter une machine de serveur Insight à une grappe de serveurs Insight existante.

Lorsque vous ajoutez un FSU [!DNL Insight Server] ou [!DNL Insight Server] à une grappe, vous devez mettre à jour les fichiers de configuration sur le [!DNL Insight Server] maître afin d’inclure les informations d’adresse pour la ou les nouvelles machines et configurer le nouveau DPU ou FSU.

>[!NOTE]
>
>Les procédures décrites dans cette section requièrent [!DNL Insight]. Si vous n’avez pas installé [!DNL Insight], suivez les instructions du * [!DNL Insight] Guide de l’utilisateur* avant de continuer.
