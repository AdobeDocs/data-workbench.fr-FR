---
description: Informations générales concernant les certificats numériques, ainsi que les procédures de téléchargement et d’installation.
title: Téléchargement et installation des certificats numériques
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
exl-id: 8aae9b63-7df0-4725-9833-711246bbe746
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 100%

---

# Téléchargement et installation des certificats numériques {#downloading-and-installing-the-digital-certificates}

Informations générales concernant les certificats numériques, ainsi que les procédures de téléchargement et d’installation.

* [Compréhension des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificats fixes](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificats en cours](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Utilisation de certificats numériques sur des machines sans accès à Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procédures d’installation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Compréhension des certificats numériques {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe utilise des certificats numériques au format X.509 pour identifier et authentifier les composants de client et de serveur qui constituent une implémentation.

Lorsque vous installez un composant de serveur ( [!DNL Insight Server] ou [!DNL Repeater]), vous devez installer le certificat numérique émis par Adobe pour le composant. Si vous devez faire migrer votre application Adobe vers une autre machine, vous devez obtenir un nouveau certificat auprès d’Adobe. Pour ce faire, contactez le service clientèle d’Adobe.

Le nom commun qui apparaît sur ce certificat identifie le serveur par un nom de domaine spécifié (par exemple [!DNL vs001a.mycompany.com]). Lorsqu’un client de serveur se connecte à ce serveur, le serveur présente ce certificat comme preuve indiquant qu’il est bien le serveur demandé par le client.

De la même façon, lorsque vous installez un client de serveur (par exemple [!DNL Insight] ou [!DNL Report]), vous devez installer le certificat numérique qui autorise une personne nommée (par exemple Jane Smith) à utiliser l’application client installée. Si vous devez faire migrer votre application Adobe vers une autre machine ou vers un autre utilisateur, vous devez obtenir un nouveau certificat auprès d’Adobe. Pour ce faire, contactez le service clientèle d’Adobe.

L’application client présente ce certificat numérique pour accéder à un composant de serveur. Un administrateur du composant de serveur peut limiter l’accès aux ressources du serveur selon le nom commun ou les valeurs d’unité organisationnelle apparaissant dans le certificat du client.

Les certificats numériques X.509 installés avec des applications Adobe permettent également à ses composants de client et de serveur d’échanger des informations par le biais du protocole SSL (Secure Sockets Layer). Le protocole SSL sécurise les transmissions par HTTP à l’aide d’un système de cryptage de clé public et privé. La mise en œuvre du protocole SSL par Adobe prend en charge les clés RSA 1 024 bits et utilise un algorithme de chiffrement RC4 128 bits.

Outre la sécurité, les certificats numériques que vous installez fonctionnent également en tant que clés de licence qui vous permettent d’exécuter le logiciel Adobe installé. Pour fonctionner correctement, un certificat numérique doit être fixe et en cours : sans cela, l’application ne se lance pas.

## Chiffrement de chaîne {#section-8abe6b2d95704d38a04137d5c4602f0b}

Voir [Chiffrement de chaîne](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) pour le chiffrement des mots de passe.

## Certificats fixes {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Un certificat fixe est un certificat numérique enregistré sur la machine sur laquelle il est installé. Le processus de fixation associe de manière permanente un certificat à un identifiant fixe spécifique (une valeur qui identifie de manière unique une machine en particulier). Pour fixer votre certificat, votre machine doit disposer d’un accès Internet au serveur de licences Adobe ou à un serveur proxy ayant accès au serveur de licences.

Si vous effectuez l’installation sur une machine sans accès à Internet, vous devez obtenir et installer un certificat préverrouillé spécial comme décrit dans la section [Utilisation de certificats numériques sur des machines sans accès à Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

Si vous effectuez l’installation sur une machine avec accès à Internet, votre certificat numérique est automatiquement fixé dès que vous lancez votre produit Adobe pour la première fois. Une fois le processus de fixation terminé, le certificat ne peut être utilisé sur aucune autre machine. Si vous devez faire migrer votre produit Adobe vers une autre machine, vous devez obtenir un nouveau certificat déverrouillé auprès d’Adobe.

## Certificats en cours {#section-15aabaa8625c46edaa7436e1f3fc29c5}

En plus d’être fixe, un certificat numérique doit être en cours. Pour rester en cours, votre certificat doit être régulièrement revalidé (en général tous les 30 jours, mais cette durée peut varier selon l’accord passé avec Adobe). Si votre machine dispose d’un accès Internet, le processus de revalidation est entièrement transparent. Votre produit Adobe se connecte automatiquement au serveur de licences et revalide le certificat dès que nécessaire. Si votre machine ne dispose pas d’un accès à Internet, vous devez installer manuellement les certificats à jour comme le décrit la section suivante.

## Utilisation de certificats numériques sur des machines sans accès à Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Si vous effectuez l’installation sur une machine sans accès à Internet, vous devez demander un certificat préverrouillé pour votre installation d’[!DNL Insight Server]. Un certificat préverrouillé est un certificat numérique verrouillé manuellement par Adobe sur l’identifiant fixe de la machine.

Pour demander un certificat préverrouillé, vous devez envoyer l’identifiant fixe ainsi que votre numéro de certificat au service clientèle d’Adobe. Pour obtenir l’identifiant fixe de votre machine, contactez le service clientèle d’Adobe pour demander l’utilitaire d’identifiant fixe Adobe. Vous pouvez également obtenir l’identifiant fixe depuis l’alerte émise par le logiciel Adobe lorsqu’il ne parvient pas à se connecter au serveur de licences.

Lorsque vous recevez le certificat préverrouillé, procédez à son installation comme la décrivent les deux dernières étapes des [Procédures d’installation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). Lorsque le certificat doit être revalidé, vous devez télécharger un nouveau certificat validé depuis le serveur de licences et le réinstaller sur votre machine.

## Procédures d’installation des certificats numériques {#section-19f31676aad344a98e26e4fca1fad03b}

**Télécharger et installer le certificat numérique**

1. Ouvrez votre navigateur web à l’adresse suivante : [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >À ce stade, votre navigateur peut vous inviter à présenter un certificat numérique. Si tel est le cas, il vous suffit de cliquer sur **[!UICONTROL Cancel]** pour fermer la boîte de dialogue.

1. Sur l’écran de connexion, saisissez l’**[!UICONTROL Account Name]** et le **[!UICONTROL Password]** que vous envoyés par Adobe, puis cliquez sur **[!UICONTROL login]**.

1. Recherchez le certificat émis pour votre [!DNL Insight Server], puis cliquez sur l’icône associée à ce certificat.

   >[!NOTE]
   >
   >Consignez le nom commun attribué à ce certificat : il vous sera utile lors d’une prochaine étape.

1. Lorsque vous êtes invité à enregistrer le certificat, cliquez sur **[!UICONTROL Save]**. (Remarque : le nom du fichier correspond au nom commun associé au certificat.)
1. Téléchargez le fichier dans le dossier [!DNL Certificates] du répertoire où [!DNL Insight Server] est installé. Ce dossier contient déjà un fichier de certificat intitulé [!DNL trust_ca_cert.pem]. Ce fichier de certificat doit toujours être présent.

1. Renommez le fichier de certificat téléchargé :

[!DNL server_cert.pem]
