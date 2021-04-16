---
description: Lorsqu’un serveur Web se déconnecte en raison d’une défaillance, la solution est simple et requiert un utilisateur Data Workbench disposant des privilèges appropriés pour ouvrir le fichier Log Processing Mode.cfg et ajouter l’identifiant du capteur (dans notre exemple, WEB2) à la section "Offline Sources".
title: Résolution du problème
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Résolution du problème{#solving-the-problem}

Lorsqu’un serveur Web se déconnecte en raison d’une défaillance, la solution est simple et requiert un utilisateur Data Workbench disposant des privilèges appropriés pour ouvrir le fichier Log Processing Mode.cfg et ajouter l’identifiant du capteur (dans notre exemple, WEB2) à la section &quot;Offline Sources&quot;.

Cette section du fichier indique à [!DNL data workbench server] qu&#39;elle ne doit plus s&#39;attendre à ce que cette source lui fournisse des données, car elle est en fait hors ligne.

>[!NOTE]
>
>Cette modification n&#39;a pas besoin d&#39;être effectuée par un consultant en Adobe. Toute personne disposant des droits appropriés pour ouvrir le fichier [!DNL Log Processing Mode.cfg] peut apporter cette modification.

Si WEB2 recommence à envoyer des données, le [!DNL data workbench server] remet la source en ligne et ajuste le champ A partir de la date de la dernière réception des données de toutes les sources dont il a connaissance. En d&#39;autres termes, les nouvelles données qui entrent dans le système l&#39;emportent sur ce qui est écrit dans le [!DNL Log Processing Mode.cfg file].

Si WEB2 est de nouveau hors ligne, l’événement A partir de maintenant s’arrête de nouveau et vous devrez modifier à nouveau le fichier [!DNL Log Processing Mode.cfg] même si WEB2 peut déjà être répertorié comme source hors ligne. Il s&#39;agit d&#39;un artefact de la conception du produit, conformément à la définition de &quot;A partir du moment&quot; : la dernière fois que le système contient des données pour toutes les sources connues.

Lorsque vous ajoutez d’autres serveurs Web (WEB4, WEB5, WEB6) et qu’ils commencent à envoyer des données à [!DNL data workbench server], vous n’avez rien à faire pour que [!DNL data workbench server] reconnaisse les nouvelles sources. Le système se rend simplement compte qu&#39;il devrait s&#39;attendre à des données provenant de ces nouvelles sources, comme décrit ci-dessus.
