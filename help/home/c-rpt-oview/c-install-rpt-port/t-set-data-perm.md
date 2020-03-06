---
description: Pour permettre au portail des rapports d’écrire dans la base de données contenant les informations nécessaires à l’authentification des utilisateurs, vous devez définir les autorisations appropriées pour la base de données.
solution: Analytics
title: Définition des autorisations pour la base de données
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Définition des autorisations pour la base de données{#set-permissions-for-the-database}

Pour permettre au portail des rapports d’écrire dans la base de données contenant les informations nécessaires à l’authentification des utilisateurs, vous devez définir les autorisations appropriées pour la base de données.

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, accédez à \*PortalName*\data\users.mdb.
1. Cliquez avec le bouton droit sur le **[!UICONTROL users.mdb]** fichier et sélectionnez **[!UICONTROL Properties]**.
1. Dans l’ [!DNL Security] onglet Groupes ou noms d’utilisateur, cliquez sur **[!UICONTROL Users]**.
1. Dans [!DNL Permission for User]la ligne Ecriture, sélectionnez **[!UICONTROL Allow]**.
1. Cliquez sur **[!UICONTROL OK]** puis fermez la [!DNL Properties] boîte de dialogue.
