---
description: Instructions pour l’utilisation de certificats personnalisés.
title: Utilisation de certificats personnalisés dans Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Utilisation de certificats personnalisés dans Data Workbench{#using-custom-certificates-in-data-workbench}

{{eol}}

Instructions pour l’utilisation de certificats personnalisés.

Un certificat utilisé par le client ou le serveur du Data Workbench doit être signé par une autorité de certification approuvée. Les clients Data Workbench reçoivent des certificats signés par l’autorité de certification Visual Sciences. Ces certificats sont approuvés par le logiciel du Data Workbench, car la variable [!DNL trust_ca_cert.pem] (fourni avec le logiciel Insight et stocké dans la variable **Certificats** Le répertoire des serveurs et des clients) contient un *Certificat d’autorité de certification racine* pour l’autorité de certification Visual Sciences. Ces certificats sont utilisés à la fois pour la licence du logiciel et pour l’authentification lorsque les clients et les serveurs communiquent entre eux à l’aide du protocole SSL. Seuls les certificats émis par l’autorité de certification Visual Sciences peuvent être utilisés pour les licences, mais d’autres certificats peuvent être utilisés pour la communication et l’authentification. Les certificats délivrés par des autorités de certification autres que Visual Sciences sont appelés ci-dessous *certificats personnalisés.*

**Remarque importante :** Pour les serveurs et les clients, le logiciel Data Workbench utilise les fichiers de certificat installés dans le client ou le serveur **Certificats** répertoire ou certificats explicitement identifiés dans sa configuration. Cependant, vous pouvez également utiliser la variable [Boutique de certificats Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) pour les clients.

Les instructions suivantes décrivent les procédures à suivre pour utiliser des certificats personnalisés pour la communication entre les clients et les serveurs de Data Workbench. Tous les détails ne sont pas une exigence difficile et différentes variantes du processus peuvent être utilisées. Toutefois, les procédures ci-dessous ont été testées pour fonctionner.

## Configuration de certificats client personnalisés {#section-2083fd41973e451fa404e7a4ae4da591}

1. Ajoutez le certificat de l’autorité de certification émettrice au [!DNL trust_cert_ca.pem], qui est installé dans le **Certificats** du client et de chaque serveur de chaque grappe à laquelle il est possible d’accéder à l’aide de ce certificat personnalisé.

1. Obtenez un certificat personnalisé pour chaque serveur de la grappe avec les conditions suivantes :

   1. Le certificat est formaté en tant que [!DNL .pem] certificat.
   1. Le certificat contient sa clé et n’est pas chiffré (c’est-à-dire qu’il ne comporte pas de mot de passe/expression de passe).

      Un certificat contient sa clé avec l’une des lignes suivantes :

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Une méthode pour supprimer l’expression de mot de passe d’une [!DNL .pem] certificate:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat a le CN, l&#39;O, l&#39;OU, etc. comme requis pour ce client dans le [!DNL Access Control.cfg] fichier .
   1. Un certificat a été émis avec une *objectif&#42;&#42;&#42;* de *client* (ou les deux) *server* **et** *client*).

      Pour vérifier qu’un certificat comporte un code d’objectif de serveur et/ou de client, les commandes suivantes peuvent être utilisées :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour les certificats de serveur, les deux commandes doivent générer :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande doit être renvoyée. [!DNL OK].

1. Placez le certificat dans le **Certificats** répertoire .
1. Dans [!DNL Insight.cfg] sous le *serverInfo* pour chaque grappe que vous souhaitez utiliser ce certificat, assurez-vous que la variable *certificat client personnalisé* est nommé, par exemple :

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configuration de certificats de serveur personnalisés {#setting-up-custom-server-certificates}

Cette section suppose que vous disposez d’une grappe en cours d’exécution, qui utilise des certificats émis par Visual Sciences et que la configuration suit les pratiques courantes (telles que *Composants des serveurs de traitement* sur le gabarit est synchronisé avec la fonction *Composants* Répertoires de tous les DPU).

1. Ajoutez le certificat de l’autorité de certification émettrice au [!DNL trust_cert_ca.pem] qui est installé sur chaque serveur de la grappe et sur chaque client qui doit communiquer avec cette grappe.
1. Obtenez un certificat personnalisé pour chaque serveur de la grappe en respectant les exigences suivantes :

   1. Le certificat personnalisé est formaté en tant que [!DNL .pem] certificat.
   1. Le certificat contient sa clé et n’est pas chiffré (c’est-à-dire qu’il ne comporte pas de mot de passe/expression de passe).

      Un certificat contient sa clé s’il comporte une ligne du type :

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Une méthode pour supprimer l’expression de mot de passe d’une [!DNL .pem] certificate:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat possède le même CN que le certificat [!DNL server_cert.pem] actuellement installé sur le serveur.
   1. Le certificat a été délivré dans le but *server* et *client*.

      Pour vérifier qu’un certificat comporte un code d’objectif de serveur et/ou de client, les commandes suivantes peuvent être utilisées :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour les certificats de serveur, les deux commandes doivent générer :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande doit être renvoyée. [!DNL OK].

1. Installez le certificat personnalisé de chaque serveur dans le **Certificats** répertoire du serveur en tant que [!DNL custom_communications_cert.pem].

1. Dans un éditeur de texte, ajoutez la ligne suivante à la **Communications.cfg** dans le fichier *Composants* et *Composants des serveurs de traitement* répertoires, directement sous la première ligne ([!DNL component = CommServer]) :

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Redémarrez tous les serveurs.

**À propos de l’avertissement d’échec de certificat**

Lorsque le serveur ou le client Insight recherche une **license** du certificat dans la variable **Certificats** , il tente de valider tous les certificats (sauf [!DNL trust_ca_cert.pem]), par rapport à une copie codée en dur du certificat de l’autorité de certification Insight, qui échoue sur tout certificat personnalisé présent dans le répertoire. Le serveur émet cet avertissement :

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Cet avertissement peut être ignoré en toute sécurité.
