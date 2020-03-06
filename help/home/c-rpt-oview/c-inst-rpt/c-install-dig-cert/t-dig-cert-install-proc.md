---
description: Procédure de téléchargement et d’installation du certificat numérique.
solution: Analytics
title: Procédures d’installation des certificats numériques
topic: Data workbench
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procédures d’installation des certificats numériques{#digital-certificate-installation-procedures}

Procédure de téléchargement et d’installation du certificat numérique.

1. Ouvrez votre navigateur Web pour [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Votre navigateur peut vous inviter à présenter un certificat numérique à ce stade. Si tel est le cas, il vous suffit de cliquer **[!UICONTROL Cancel]** pour fermer la boîte de dialogue.

1. Dans l’écran de connexion, saisissez le nom du compte et le mot de passe reçus d’Adobe, puis cliquez sur **[!UICONTROL login]**.
1. Recherchez le certificat qui a été émis pour votre instance de [!DNL Report] Server (*Votre nom*.pem) et cliquez sur l’ ![](assets/btn_save_certificatedownload.PNG) icône associée à ce certificat.
1. Lorsque vous êtes invité à enregistrer le certificat, cliquez sur **[!UICONTROL Save]**.
1. Téléchargez le fichier dans le dossier Certificates du répertoire dans lequel vous avez installé [!DNL Report Server].

   Ce dossier contient déjà un fichier de certificat nommé [!DNL trust_ca_cert.pem]. Les deux fichiers de certificat doivent toujours être présents pour que [!DNL Report] le serveur fonctionne.

