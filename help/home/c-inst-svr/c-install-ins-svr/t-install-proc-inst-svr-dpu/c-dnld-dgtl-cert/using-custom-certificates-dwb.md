---
description: Instructions relatives à l’utilisation des certificats personnalisés.
title: Utilisation de certificats personnalisés dans les outils de données
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Utilisation de certificats personnalisés dans les outils de données{#using-custom-certificates-in-data-workbench}

Instructions relatives à l’utilisation des certificats personnalisés.

Un certificat utilisé par le client ou le serveur Outils de données doit être signé par une autorité de certification approuvée. Les clients des outils de données reçoivent des certificats signés par l’autorité de certification Visual Sciences. Ces certificats sont approuvés par le logiciel Outils de données, car le [!DNL trust_ca_cert.pem] (fourni avec le logiciel Insight et stocké dans le répertoire **Certificats** des serveurs et des clients) contient un certificat *d’autorité de certification* racine pour l’autorité de certification Visual Sciences. Ces certificats sont utilisés à la fois pour la licence du logiciel et pour l’authentification lorsque les clients et les serveurs communiquent entre eux à l’aide de SSL. Seuls les certificats émis par l&#39;autorité de certification Visual Sciences peuvent être utilisés pour la licence, mais d&#39;autres certificats peuvent être utilisés pour la communication et l&#39;authentification. Les certificats émis par des autorités de certification autres que Visual Sciences sont appelés ci-dessous certificats *personnalisés.*

**Remarque importante :** Pour les serveurs et les clients, le logiciel Outils de données utilise les fichiers de certificat installés dans le répertoire **Certificats** du client ou du serveur ou les certificats explicitement identifiés dans sa configuration. Cependant, vous pouvez également utiliser le magasin [de certificats](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) Windows pour les clients.

Les instructions suivantes décrivent les procédures à suivre pour utiliser des certificats personnalisés pour la communication entre les clients et les serveurs des outils de données. Tous les détails ne sont pas une exigence difficile et différentes variantes du processus peuvent être utilisées. Toutefois, les procédures ci-dessous ont été testées pour fonctionner.

## Configuration des certificats client personnalisés {#section-2083fd41973e451fa404e7a4ae4da591}

1. Ajoutez le certificat de l’autorité de certification émettrice à la [!DNL trust_cert_ca.pem], qui est installé dans le répertoire **Certificats** du client et celui de chaque serveur de chaque grappe à laquelle vous souhaitez accéder à l’aide de ce certificat personnalisé.

1. Obtenez un certificat personnalisé pour chaque serveur de la grappe avec les conditions suivantes :

   1. Le certificat est formaté en tant que [!DNL .pem] certificat.
   1. Le certificat contient sa clé et n’est pas chiffré (c.-à-d. qu’il ne comporte aucun mot de passe/phrase de passe).

      Un certificat contient sa clé avec l’une des lignes suivantes :

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Pour supprimer l’expression de mot de passe d’un [!DNL .pem] certificat, procédez comme suit :

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat a le CN, O, OU, etc. comme requis pour ce client dans le [!DNL Access Control.cfg] fichier des serveurs.
   1. Le certificat a été émis avec une *finalité **** du *client* (ou des deux *serveur* **et  client).****

      Pour vérifier qu’un certificat comporte un code d’objectif du serveur et/ou du client, vous pouvez utiliser les commandes suivantes :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour un certificat de serveur, les deux commandes doivent générer les résultats suivants :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande est nécessaire pour obtenir [!DNL OK].

1. Placez le certificat dans le répertoire **Certificats** du client.
1. Dans [!DNL Insight.cfg] sous *serverInfo* pour chaque grappe que vous souhaitez utiliser ce certificat, assurez-vous que le certificat *client* personnalisé est nommé, par exemple :

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configuration de certificats de serveur personnalisés {#setting-up-custom-server-certificates}

Cette section suppose que vous disposez d’une grappe en cours d’exécution, à l’aide de certificats émis par Visual Sciences, et que la configuration suit les pratiques courantes (par exemple, le répertoire *Composants pour les serveurs* de traitement sur le serveur maître est synchronisé avec les répertoires *Composants* de tous les processeurs de traitement).

1. Ajoutez le certificat de l’autorité de certification émettrice au certificat [!DNL trust_cert_ca.pem] qui est installé sur chaque serveur de la grappe et chaque client qui doit communiquer avec cette grappe.
1. Obtenez un certificat personnalisé pour chaque serveur de la grappe en respectant les exigences suivantes :

   1. Le certificat personnalisé est formaté en tant que [!DNL .pem] certificat.
   1. Le certificat contient sa clé et n’est pas chiffré (c.-à-d. qu’il ne comporte aucun mot de passe/phrase de passe).

      Un certificat contient sa clé s’il comporte une ligne telle que :

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Pour supprimer l’expression de mot de passe d’un [!DNL .pem] certificat, procédez comme suit :

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat possède le même CN que celui [!DNL server_cert.pem] actuellement installé sur le serveur.
   1. Le certificat a été émis dans le but de *serveur* et de *client*.

      Pour vérifier qu’un certificat comporte un code d’objectif du serveur et/ou du client, vous pouvez utiliser les commandes suivantes :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour un certificat de serveur, les deux commandes doivent générer les résultats suivants :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande est nécessaire pour obtenir [!DNL OK].

1. Installez le certificat personnalisé de chaque serveur dans le répertoire **Certificats** du serveur en tant que [!DNL custom_communications_cert.pem].

1. Dans un éditeur de texte, ajoutez la ligne suivante au fichier **Communications.cfg** dans les répertoires *Composants* et *Composants pour les serveurs* de traitement, directement sous la première ligne ([!DNL component = CommServer]) :

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Redémarrez tous les serveurs.

**A propos de l’avertissement d’échec de certificat**

Lorsque le serveur ou le client Insight recherche un certificat de **licence** dans le répertoire **Certificates** , il tente de valider tous les certificats (sauf [!DNL trust_ca_cert.pem]) par rapport à une copie codée en dur du certificat de l’autorité de certification Insight, qui échoue sur tout certificat personnalisé présent dans le répertoire. Le serveur émet cet avertissement :

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Cet avertissement peut être ignoré en toute sécurité.
