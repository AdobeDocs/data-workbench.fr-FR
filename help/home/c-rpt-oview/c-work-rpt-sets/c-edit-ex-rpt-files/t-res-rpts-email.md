---
description: Procédure de renvoi des rapports par courriel.
title: Envoyer à nouveau des rapports par e-mail
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Envoyer à nouveau des rapports par e-mail{#resending-reports-by-email}

Procédure de renvoi des rapports par courriel.

Si le paramètre **[!UICONTROL Allow Report Regeneration]** du fichier [!DNL Report.cfg] est défini sur [!DNL True], lorsque vous apportez des modifications à un fichier [!DNL Report.cfg] et que vous le réenregistrez sur le serveur, Report Server génère automatiquement de nouveau les rapports dans cet ensemble. Les rapports ne sont pas renvoyés par courrier électronique.

1. Sous l&#39;onglet [!DNL Reports], sélectionnez le sous-dossier (sous-répertoire de tabulation ou de liste déroulante) du jeu de rapports que vous souhaitez renvoyer.
1. Cliquez sur **[!UICONTROL Report.cfg]**. Les paramètres de [!DNL Report.cfg] pour ce jeu de rapports s&#39;affichent.
1. Modifiez le paramètre **[!UICONTROL Start Date]** en fonction de l’heure de renvoi des rapports.
1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL Report.cfg (modified)]** en haut des paramètres et en cliquant sur **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]***.
Les rapports de ce jeu se régénèrent et sont envoyés par courrier électronique aux destinataires spécifiés.
