---
description: Lorsqu’un serveur Web est hors ligne en raison d’un échec, la solution est simple et requiert un utilisateur des outils de données disposant des privilèges appropriés pour ouvrir le fichier Log Processing Mode.cfg et ajouter l’ID du capteur (dans notre exemple, WEB2) à la section "Offline Sources".
solution: Insight
title: Résoudre le problème
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Résoudre le problème{#solving-the-problem}

Lorsqu’un serveur Web est hors ligne en raison d’un échec, la solution est simple et requiert un utilisateur des outils de données disposant des privilèges appropriés pour ouvrir le fichier Log Processing Mode.cfg et ajouter l’ID du capteur (dans notre exemple, WEB2) à la section &quot;Offline Sources&quot;.

Cette section du fichier indique [!DNL data workbench server] qu’elle ne doit plus attendre de données provenant de cette source car elle est, en fait, hors ligne.

>[!NOTE]
>
>Cette modification n’a pas besoin d’être effectuée par un consultant Adobe. Toute personne disposant des privilèges appropriés pour ouvrir le [!DNL Log Processing Mode.cfg] fichier peut effectuer cette modification.

Si WEB2 commence à envoyer de nouveau des données, la [!DNL data workbench server] source revient en ligne et ajuste le champ A partir du moment afin de refléter la dernière fois qu’elle a reçu des données de toutes les sources dont elle a connaissance. En d&#39;autres termes, les nouvelles données qui entrent dans le système ont préséance sur ce qui est écrit dans le [!DNL Log Processing Mode.cfg file].

Si WEB2 est de nouveau hors ligne, l’événement A partir de maintenant s’arrête de nouveau et vous devrez modifier à nouveau le [!DNL Log Processing Mode.cfg] fichier, même si WEB2 est déjà répertorié comme source hors ligne. Il s’agit d’un artefact de la conception du produit, conformément à la définition de &quot;A partir du moment&quot; : la dernière fois que le système dispose de données pour toutes les sources connues.

Lorsque vous ajoutez d’autres serveurs Web (WEB4, WEB5, WEB6) et qu’ils commencent à envoyer des données à la [!DNL data workbench server], il n’est pas nécessaire de faire quoi que ce soit pour que les [!DNL data workbench server] nouvelles sources soient reconnues. Le système se rend tout simplement compte qu&#39;il devrait s&#39;attendre à des données provenant de ces nouvelles sources, comme décrit ci-dessus.
