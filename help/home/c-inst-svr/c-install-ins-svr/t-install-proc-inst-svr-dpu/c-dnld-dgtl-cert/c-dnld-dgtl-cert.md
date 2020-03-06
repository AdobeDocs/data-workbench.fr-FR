---
description: Informations générales sur les certificats numériques et procédures de téléchargement et d’installation.
solution: Insight
title: Téléchargement et installation des certificats numériques
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Téléchargement et installation des certificats numériques{#downloading-and-installing-the-digital-certificates}

Informations générales sur les certificats numériques et procédures de téléchargement et d’installation.

* [Présentation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificats verrouillés sur le noeud](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificats actuels](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Utilisation de certificats numériques sur des machines sans accès à Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procédures d’installation des certificats numériques](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Présentation des certificats numériques {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe utilise des certificats numériques X.509 pour identifier et authentifier les composants client et serveur qui constituent une implémentation.

Lorsque vous installez un composant de serveur ( [!DNL Insight Server] ou [!DNL Repeater]), vous devez installer le certificat numérique émis par Adobe pour le composant. Si vous devez migrer votre application Adobe vers un autre ordinateur, vous devez obtenir un nouveau certificat d’Adobe. Pour ce faire, contactez le service à la clientèle d’Adobe.

Le nom commun qui apparaît sur ce certificat identifie le serveur par un nom de domaine spécifié (par exemple, [!DNL vs001a.mycompany.com]). Lorsqu’un client de serveur se connecte à ce serveur, le serveur présente ce certificat comme la preuve qu’il s’agit bien du serveur demandé par le client.

De même, lorsque vous installez un client serveur (par exemple, [!DNL Insight] ou [!DNL Report]), vous devez installer le certificat numérique qui autorise une personne nommée (par exemple, Jane Smith) à utiliser l’application cliente installée. Si vous devez migrer votre application Adobe vers un autre ordinateur ou un autre utilisateur nommé, vous devez obtenir un nouveau certificat d’Adobe. Pour ce faire, contactez le service à la clientèle d’Adobe.

L’application cliente présente ce certificat numérique pour accéder à un composant serveur. Un administrateur du composant serveur peut restreindre l’accès aux ressources du serveur en fonction du nom commun ou des valeurs d’unité d’organisation qui apparaissent dans le certificat du client.

Les certificats numériques X.509 installés avec les applications Adobe permettent également à ses composants client et serveur d’échanger des informations via SSL (Secure Sockets Layer). SSL sécurise les transmissions via HTTP à l’aide d’un système de chiffrement de clé publique et privée. L’implémentation de SSL par Adobe prend en charge les clés RSA 1 024 bits et utilise un algorithme de chiffrement RC4 128 bits.

Outre la sécurité, les certificats numériques que vous installez fonctionnent également comme des clés de licence qui vous permettent d’exécuter le logiciel Adobe installé. Pour fonctionner correctement, un certificat numérique doit être verrouillé par un noeud et à jour, sinon l’application ne démarre pas.

## Chiffrement de chaîne {#section-8abe6b2d95704d38a04137d5c4602f0b}

Voir Chiffrement de [chaînes](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) pour chiffrer des mots de passe.

## Certificats verrouillés sur le noeud {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Un certificat verrouillé par un noeud est un certificat numérique qui a été enregistré sur l’ordinateur sur lequel il est installé. Le verrouillage de noeud associe de manière permanente un certificat à un identifiant de noeud spécifique (une valeur qui identifie de manière unique un ordinateur particulier). Pour verrouiller votre certificat par un noeud, votre ordinateur doit disposer d’un accès Internet au serveur Adobe License Server ou à un serveur proxy qui a accès au serveur License Server.

Si vous effectuez l’installation sur une machine qui ne peut pas accéder à Internet, vous devez obtenir et installer un certificat préverrouillé spécial, comme décrit dans [Utilisation de certificats numériques sur des machines sans accès](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)à Internet.

Si vous effectuez l’installation sur une machine qui peut accéder à Internet, votre certificat numérique est verrouillé automatiquement au niveau du noeud lors du premier démarrage de votre produit Adobe. Une fois le certificat verrouillé sur un noeud, il ne peut plus être utilisé sur un autre ordinateur. Si vous devez migrer votre produit Adobe vers un autre ordinateur, vous devez obtenir un nouveau certificat déverrouillé d’Adobe.

## Certificats actuels {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Outre le fait d’être verrouillé sur un noeud, un certificat numérique doit être à jour. Pour rester à jour, votre certificat doit être régulièrement revalidé (généralement tous les 30 jours, mais peut varier selon votre accord avec Adobe). Si votre machine a accès à Internet, le processus de revalidation est complètement transparent. Votre produit Adobe se connecte automatiquement au serveur de licences et révalide le certificat si nécessaire. Si votre ordinateur n’a pas accès à Internet, vous devez installer manuellement les certificats mis à jour, comme décrit dans la section suivante.

## Utilisation de certificats numériques sur des machines sans accès à Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Si vous effectuez l’installation sur une machine qui ne peut pas accéder à Internet, vous devez demander un certificat pré-verrouillé pour votre installation de [!DNL Insight Server]. Un certificat pré-verrouillé est un certificat numérique qu’Adobe verrouille manuellement sur l’identifiant de noeud de l’ordinateur.

Pour demander un certificat pré-verrouillé, vous devez envoyer l’identifiant de noeud et le numéro de votre certificat au service à la clientèle Adobe. Pour obtenir l’identifiant de noeud pour votre ordinateur, contactez le service à la clientèle d’Adobe pour demander l’utilitaire Adobe Node Identifier. Vous pouvez également obtenir l’identifiant de noeud à partir de l’alerte indiquant que le logiciel Adobe génère des problèmes lorsqu’il tente de se connecter au serveur de licences et qu’il ne le peut pas.

Lorsque vous recevez le certificat préverrouillé, installez-le comme décrit dans les deux dernières étapes des procédures [d’installation des certificats](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)numériques. Lorsque le certificat doit être revalidé, vous devez télécharger un nouveau certificat validé à partir du serveur de licences et le réinstaller sur votre ordinateur.

## Procédures d’installation des certificats numériques {#section-19f31676aad344a98e26e4fca1fad03b}

**Pour télécharger et installer le certificat numérique**

1. Ouvrez votre navigateur Web pour [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Votre navigateur peut vous inviter à présenter un certificat numérique à ce stade. Si tel est le cas, il vous suffit de cliquer **[!UICONTROL Cancel]** pour fermer la boîte de dialogue.

1. Dans l’écran de connexion, saisissez le **[!UICONTROL Account Name]** et le nom **[!UICONTROL Password]** que vous avez reçus d’Adobe, puis cliquez sur **[!UICONTROL login]**.

1. Localisez le certificat qui a été émis pour votre [!DNL Insight Server]compte, puis cliquez sur l’icône associée à ce certificat.

   >[!NOTE]
   >
   >Notez le nom commun attribué à ce certificat. Vous utiliserez ce nom à une étape ultérieure.

1. Lorsque vous êtes invité à enregistrer le certificat, cliquez sur **[!UICONTROL Save]**. (Notez que le nom du fichier correspond au nom commun associé au certificat.)
1. Téléchargez le fichier dans le [!DNL Certificates] dossier du répertoire dans lequel vous avez installé [!DNL Insight Server]. Ce dossier contient déjà un fichier de certificat nommé [!DNL trust_ca_cert.pem]. Ce fichier de certificat doit toujours être présent.

1. Renommez le fichier de certificat téléchargé en :

[!DNL server_cert.pem]

