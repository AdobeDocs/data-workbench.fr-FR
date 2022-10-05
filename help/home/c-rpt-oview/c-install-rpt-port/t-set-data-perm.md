---
description: Pour permettre au portail de rapports d’écrire dans la base de données contenant les informations nécessaires à l’authentification des utilisateurs, vous devez définir les autorisations appropriées pour la base de données.
title: Définir les autorisations pour la base de données
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Définir les autorisations pour la base de données{#set-permissions-for-the-database}

{{eol}}

Pour permettre au portail de rapports d’écrire dans la base de données contenant les informations nécessaires à l’authentification des utilisateurs, vous devez définir les autorisations appropriées pour la base de données.

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, accédez à \*PortalName*\data\users.mdb.
1. Cliquez avec le bouton droit de la souris sur le **[!UICONTROL users.mdb]** et sélectionnez **[!UICONTROL Properties]**.
1. Sur le [!DNL Security] dans Groupes ou noms d’utilisateur, cliquez sur **[!UICONTROL Users]**.
1. Dans [!DNL Permission for User], dans la ligne Ecriture , sélectionnez **[!UICONTROL Allow]**.
1. Cliquez sur **[!UICONTROL OK]** et fermez la [!DNL Properties] de la boîte de dialogue
