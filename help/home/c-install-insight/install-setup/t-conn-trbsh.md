---
description: Si Insight ne parvient pas à se connecter au ou aux serveurs Insight à l’aide des paramètres spécifiés, un noeud rouge apparaît dans le Gestionnaire de serveurs.
title: Dépannage de la connexion
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Dépannage de la connexion{#connection-troubleshooting}

{{eol}}

Si Insight ne parvient pas à se connecter au ou aux serveurs Insight à l’aide des paramètres spécifiés, un noeud rouge apparaît dans le Gestionnaire de serveurs.

Cela peut se produire, par exemple, si vous configurez la connexion de manière incorrecte ou si vous ne disposez pas des autorisations nécessaires pour afficher la variable [!DNL Insight Server’s] statut.

**Pour déterminer pourquoi Insight n’est pas en mesure d’établir une connexion**

1. Cliquez avec le bouton droit sur le noeud de serveur rouge, puis cliquez sur **[!UICONTROL Detailed Status]**.
1. Dans le [!DNL Detailed Status] interface, cliquez sur **[!UICONTROL Network Connections]** et développez les éléments numérotés. Le [!DNL Status] Le paramètre fournit des informations sur les raisons pour lesquelles Insight ne parvient pas à établir une connexion :

   * Un code d’état dans les années 500 indique une erreur de configuration.
   * Un code d’état 403 indique généralement que vous n’êtes pas autorisé à afficher l’état du serveur.

Vous pouvez afficher des informations d’état supplémentaires dans le [!DNL insight.log] fichier . Ce fichier journal se trouve dans la variable [!DNL Trace] dans le répertoire où vous avez installé Insight. Pour afficher le fichier, ouvrez-le dans un éditeur de texte tel que le Bloc-notes.

Si vous avez besoin d’aide pour comprendre les informations de la section [!DNL insight.log] contactez d’abord votre administrateur système. Si vous avez besoin d’une assistance supplémentaire, contactez l’assistance clientèle d’Adobe.
