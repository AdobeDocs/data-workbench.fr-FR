---
description: Les transformations et les dimensions utilisent des conditions pour déterminer quand certaines instructions ou actions s’appliquent aux champs de journal.
title: À propos des conditions
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# À propos des conditions{#about-conditions}

Les transformations et les dimensions utilisent des conditions pour déterminer quand certaines instructions ou actions s’appliquent aux champs de journal.

Le paramètre Condition d&#39;entrée de journal utilise des conditions pour déterminer les entrées de journal à inclure dans le processus de construction du jeu de données. Cette annexe décrit les différents types de conditions disponibles dans le serveur de l’outil de données.

Une condition se retrouve dans l’une des deux catégories suivantes :

* **[!DNL Test Operations]:** [!DNL Compare],  [!DNL Not Empty],  [!DNL Range],  [!DNL Regular Expression]et  [!DNL String Match] conditions sont utilisés pour tester différents états dans les champs de journal disponibles.

* **[!DNL Boolean Operations]:** Les  [!DNL And],  [!DNL Or]et  [!DNL Neither] conditions sont utilisées pour combiner les opérations de test décrites ci-dessus. Par exemple, si vous disposez d’une condition [!DNL Range] et d’une condition [!DNL String Match] qui doivent toutes deux être fausses pour exécuter l’action appropriée, ces deux opérations sont des enfants de la condition [!DNL Neither]. Notez que la condition [!DNL And] est utilisée comme racine de tous les tests de condition dans le système.
