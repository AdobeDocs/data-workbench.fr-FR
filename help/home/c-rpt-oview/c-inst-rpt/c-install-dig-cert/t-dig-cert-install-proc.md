---
description: Procédure de téléchargement et d’installation du certificat numérique.
title: Procédures d’installation des certificats numériques
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 33%

---

# Procédures d’installation des certificats numériques{#digital-certificate-installation-procedures}

Procédure de téléchargement et d’installation du certificat numérique.

1. Ouvrez votre navigateur web à l’adresse suivante : [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >À ce stade, votre navigateur peut vous inviter à présenter un certificat numérique. Si tel est le cas, il vous suffit de cliquer sur **[!UICONTROL Cancel]** pour fermer la boîte de dialogue.

1. Dans l’écran de connexion, saisissez le Nom du compte et le Mot de passe que vous avez reçu de l’Adobe, puis cliquez sur **[!UICONTROL login]**.
1. Localisez le certificat émis pour votre instance du serveur [!DNL Report] (*Votre nom*.pem) et cliquez sur l’icône ![](assets/btn_save_certificatedownload.PNG) associée à ce certificat.
1. Lorsque vous êtes invité à enregistrer le certificat, cliquez sur **[!UICONTROL Save]**.
1. Téléchargez le fichier dans le dossier Certificats du répertoire où vous avez installé [!DNL Report Server].

   Ce dossier contient déjà un fichier de certificat intitulé [!DNL trust_ca_cert.pem]. Les deux fichiers de certificat doivent toujours être présents pour que le serveur [!DNL Report] fonctionne.
