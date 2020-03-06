---
description: Si Insight ne parvient pas à se connecter aux serveurs Insight à l’aide des paramètres spécifiés, un noeud rouge apparaît dans le Gestionnaire de serveurs.
title: Résolution des problèmes de connexion
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Résolution des problèmes de connexion{#connection-troubleshooting}

Si Insight ne parvient pas à se connecter aux serveurs Insight à l’aide des paramètres spécifiés, un noeud rouge apparaît dans le Gestionnaire de serveurs.

Cela peut se produire, par exemple, si vous configurez la connexion de manière incorrecte ou si vous n’êtes pas autorisé à afficher l’ [!DNL Insight Server’s] état.

**Pour déterminer pourquoi Insight n’est pas en mesure d’établir une connexion**

1. Cliquez avec le bouton droit sur le noeud de serveur rouge, puis cliquez sur **[!UICONTROL Detailed Status]**.
1. Dans l’ [!DNL Detailed Status] interface, cliquez sur **[!UICONTROL Network Connections]** et développez les éléments numérotés. Le [!DNL Status] paramètre fournit des informations sur les raisons pour lesquelles Insight n’est pas en mesure d’établir une connexion :

   * Un code d’état dans les années 500 indique une erreur de configuration.
   * Un code d’état 403 indique généralement que vous n’êtes pas autorisé à afficher l’état du serveur.

Vous pouvez afficher des informations d’état supplémentaires dans le [!DNL insight.log] fichier. Ce fichier journal se trouve dans le [!DNL Trace] dossier du répertoire dans lequel vous avez installé Insight. Pour afficher le fichier, ouvrez-le dans un éditeur de texte tel que le Bloc-notes.

Si vous avez besoin d&#39;aide pour comprendre les informations contenues dans le [!DNL insight.log] fichier, contactez d&#39;abord votre administrateur système. Si vous avez besoin d’une assistance supplémentaire, contactez le service à la clientèle d’Adobe.
