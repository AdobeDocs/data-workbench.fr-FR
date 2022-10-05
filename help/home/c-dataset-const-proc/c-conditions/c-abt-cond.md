---
description: Les transformations et les dimensions utilisent des conditions pour déterminer quand certaines instructions ou actions s’appliquent aux champs de journal.
title: À propos des conditions
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# À propos des conditions{#about-conditions}

{{eol}}

Les transformations et les dimensions utilisent des conditions pour déterminer quand certaines instructions ou actions s’appliquent aux champs de journal.

Le paramètre Condition d’entrée du journal utilise des conditions pour déterminer quelles entrées de journal doivent être incluses dans le processus de construction du jeu de données. Cette annexe décrit les différents types de conditions disponibles dans le serveur Data Workbench.

Une condition est classée dans l’une des deux catégories suivantes :

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression], et [!DNL String Match] Les conditions sont utilisées pour tester différents états dans les champs de journal disponibles.

* **[!DNL Boolean Operations]:** Le [!DNL And], [!DNL Or], et [!DNL Neither] sont utilisées pour combiner les opérations de test décrites ci-dessus. Par exemple, si vous avez une [!DNL Range] condition et une [!DNL String Match] qui doit être définie sur false pour effectuer l’action appropriée, vous devez faire de ces deux opérations des enfants de la condition [!DNL Neither] condition. Notez que la variable [!DNL And] est utilisée comme racine de tous les tests de condition dans le système.
