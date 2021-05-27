---
description: Lorsqu’un serveur web est hors ligne en raison d’un échec, la solution est simple et requiert un utilisateur Data Workbench disposant des privilèges appropriés pour ouvrir le fichier Mode de traitement du journal.cfg et ajouter l’identifiant du capteur (dans notre exemple, WEB2) à la section "Sources hors ligne".
title: Résolution du problème
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Résolution du problème{#solving-the-problem}

Lorsqu’un serveur web est hors ligne en raison d’un échec, la solution est simple et requiert un utilisateur Data Workbench disposant des privilèges appropriés pour ouvrir le fichier Mode de traitement du journal.cfg et ajouter l’identifiant du capteur (dans notre exemple, WEB2) à la section &quot;Sources hors ligne&quot;.

Cette section du fichier indique à [!DNL data workbench server] qu’il ne doit plus attendre de données de cette source, car elle est, en fait, hors ligne.

>[!NOTE]
>
>Cette modification n’a pas besoin d’être effectuée par un consultant en Adobe. Toute personne disposant des privilèges appropriés pour ouvrir le fichier [!DNL Log Processing Mode.cfg] peut apporter cette modification.

Si WEB2 recommence à envoyer des données, la fonction [!DNL data workbench server] remet la source en ligne et ajuste le champ À partir du moment pour refléter la dernière fois où elle a reçu des données de toutes les sources dont elle est consciente. En d’autres termes, les nouvelles données qui entrent dans le système ont priorité sur ce qui est écrit dans la balise [!DNL Log Processing Mode.cfg file].

Si WEB2 est à nouveau hors ligne, l’état À partir du moment s’arrête à nouveau et vous devrez modifier à nouveau le fichier [!DNL Log Processing Mode.cfg] même s’il est possible que WEB2 soit déjà répertorié comme source hors ligne. Il s’agit d’un artefact de la conception du produit, conformément à la définition du champ À partir du moment : la dernière fois que le système contient des données pour toutes les sources connues.

Lorsque vous ajoutez d’autres serveurs Web (WEB4, WEB5, WEB6) et qu’ils commencent à envoyer des données à la [!DNL data workbench server], il n’est pas nécessaire de faire quoi que ce soit pour que [!DNL data workbench server] reconnaisse les nouvelles sources. Le système se rend simplement compte qu’il doit s’attendre à des données provenant de ces nouvelles sources, comme décrit ci-dessus.
