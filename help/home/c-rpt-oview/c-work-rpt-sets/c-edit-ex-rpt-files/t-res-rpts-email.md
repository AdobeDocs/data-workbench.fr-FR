---
description: Procédure de renvoi des rapports par courrier électronique.
title: Envoyer à nouveau des rapports par e-mail
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Envoyer à nouveau des rapports par e-mail{#resending-reports-by-email}

Procédure de renvoi des rapports par courrier électronique.

Si le paramètre **[!UICONTROL Allow Report Regeneration]** du fichier [!DNL Report.cfg] est défini sur [!DNL True], lorsque vous apportez des modifications à un fichier [!DNL Report.cfg] et que vous le réenregistrez sur le serveur, le serveur de rapports génère automatiquement à nouveau les rapports de cet ensemble. Les rapports ne sont pas renvoyés par courrier électronique.

1. Sous l’onglet [!DNL Reports] , sélectionnez le sous-dossier (sous-répertoire de tabulation ou de liste déroulante) du jeu de rapports que vous souhaitez renvoyer.
1. Cliquez sur **[!UICONTROL Report.cfg]**. Les paramètres de [!DNL Report.cfg] de ce jeu de rapports s’affichent.
1. Remplacez le paramètre **[!UICONTROL Start Date]** par l’heure future à laquelle vous souhaitez que les rapports soient renvoyés.
1. Enregistrez le fichier en cliquant avec le bouton droit de la souris sur **[!UICONTROL Report.cfg (modified)]** en haut des paramètres et en cliquant sur **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]***.
Les rapports de ce jeu se régénèrent et sont renvoyés par e-mail aux destinataires spécifiés.
