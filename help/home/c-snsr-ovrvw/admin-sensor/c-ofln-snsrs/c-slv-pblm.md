---
description: Lorsqu’un serveur web est hors ligne en raison d’un échec, la solution est simple et requiert un utilisateur Data Workbench disposant des privilèges appropriés pour ouvrir le fichier Mode de traitement du journal.cfg et ajouter l’identifiant du capteur (dans notre exemple, WEB2) à la section "Sources hors ligne".
title: Résolution du problème
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Résolution du problème{#solving-the-problem}

{{eol}}

Lorsqu’un serveur web est hors ligne en raison d’un échec, la solution est simple et requiert un utilisateur Data Workbench disposant des privilèges appropriés pour ouvrir le fichier Mode de traitement du journal.cfg et ajouter l’identifiant du capteur (dans notre exemple, WEB2) à la section &quot;Sources hors ligne&quot;.

Cette section du fichier indique au [!DNL data workbench server] qu’elle ne doit plus attendre de données de cette source, car elle est, en fait, hors ligne.

>[!NOTE]
>
>Cette modification n’a pas besoin d’être effectuée par un consultant en Adobe. Toute personne disposant des privilèges appropriés pour ouvrir la variable [!DNL Log Processing Mode.cfg] peut apporter cette modification.

Si WEB2 recommence à envoyer des données, la variable [!DNL data workbench server] remet la source en ligne et ajuste le champ À partir du moment pour refléter la dernière fois où elle a reçu des données de toutes les sources dont elle est consciente. En d’autres termes, les nouvelles données qui entrent dans le système ont la priorité sur ce qui est écrit dans la variable [!DNL Log Processing Mode.cfg file].

Si WEB2 est à nouveau hors ligne, le champ À partir du moment s’arrête à nouveau et vous devrez modifier la variable [!DNL Log Processing Mode.cfg] de nouveau, même si WEB2 est peut-être déjà répertorié comme source hors ligne. Il s’agit d’un artefact de la conception du produit, conformément à la définition du champ À partir du moment : la dernière fois que le système contient des données pour toutes les sources connues.

Lorsque vous ajoutez d’autres serveurs web (WEB4, WEB5, WEB6), et qu’ils commencent à envoyer des données à la variable [!DNL data workbench server], vous n’avez rien à faire pour que la variable [!DNL data workbench server] reconnaître les nouvelles sources. Le système se rend simplement compte qu’il doit s’attendre à des données provenant de ces nouvelles sources, comme décrit ci-dessus.
