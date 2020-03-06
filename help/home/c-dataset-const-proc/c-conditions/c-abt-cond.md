---
description: Les transformations et dimensions utilisent des conditions pour déterminer quand certaines instructions ou actions s’appliquent aux champs du journal.
solution: Analytics
title: A propos des conditions
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# A propos des conditions{#about-conditions}

Les transformations et dimensions utilisent des conditions pour déterminer quand certaines instructions ou actions s’appliquent aux champs du journal.

Le paramètre Condition d’entrée dans le journal utilise des conditions pour déterminer les entrées du journal qui doivent être incluses dans le processus de construction du jeu de données. Cette annexe décrit les différents types de conditions disponibles dans le serveur de l’outil de données.

Une condition se divise en deux catégories :

* **[!DNL Test Operations]:**[!DNL Compare],[!DNL Not Empty],[!DNL Range],[!DNL Regular Expression]et[!DNL String Match]des conditions sont utilisées pour tester différents états dans les champs du journal disponibles.

* **[!DNL Boolean Operations]:**Les conditions[!DNL And],[!DNL Or]et[!DNL Neither]sont utilisées pour combiner les opérations de test décrites ci-dessus. Par exemple, si vous avez une[!DNL Range]condition et une[!DNL String Match]condition qui doivent toutes deux être fausses pour exécuter l’action appropriée, vous devez faire de ces deux opérations des enfants de la[!DNL Neither]condition. Notez que la[!DNL And]condition est utilisée comme racine de tous les tests de condition dans le système.

