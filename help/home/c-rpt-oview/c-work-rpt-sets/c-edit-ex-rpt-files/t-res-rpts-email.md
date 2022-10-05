---
description: Procédure de renvoi des rapports par courrier électronique.
title: Envoyer à nouveau des rapports par e-mail
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Envoyer à nouveau des rapports par e-mail{#resending-reports-by-email}

{{eol}}

Procédure de renvoi des rapports par courrier électronique.

Si la variable **[!UICONTROL Allow Report Regeneration]** du paramètre [!DNL Report.cfg] est défini sur [!DNL True], lorsque vous apportez des modifications à une [!DNL Report.cfg] et réenregistrez ce fichier sur le serveur. Le serveur de rapports génère automatiquement à nouveau les rapports de cet ensemble. Les rapports ne sont pas renvoyés par courrier électronique.

1. Sur le [!DNL Reports] , sélectionnez le sous-dossier (sous-répertoire de tabulation ou de liste déroulante) du jeu de rapports que vous souhaitez renvoyer.
1. Cliquez sur **[!UICONTROL Report.cfg]**. Les paramètres de la variable [!DNL Report.cfg] pour ce jeu de rapports.
1. Modifiez la variable **[!UICONTROL Start Date]** à l’heure future à laquelle les rapports doivent être renvoyés.
1. Enregistrez le fichier en cliquant avec le bouton droit de la souris **[!UICONTROL Report.cfg (modified)]** en haut des paramètres et en cliquant sur **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Les rapports de ce jeu se régénèrent et sont renvoyés par e-mail aux destinataires spécifiés.
