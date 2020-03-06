---
description: Adobe utilise des certificats numériques X.509 pour identifier et authentifier les composants client et serveur qui constituent une implémentation.
solution: Analytics
title: Présentation des certificats numériques
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation des certificats numériques{#understanding-digital-certificates}

Adobe utilise des certificats numériques X.509 pour identifier et authentifier les composants client et serveur qui constituent une implémentation.

Lors de l’installation [!DNL Report Server], vous devez installer le certificat numérique qui autorise une personne nommée (par exemple, Jane Smith) à utiliser l’application cliente installée.

>[!NOTE]
>
>Si vous devez effectuer la migration [!DNL Report Server] vers un autre ordinateur ou un autre utilisateur nommé, vous devez obtenir un nouveau certificat auprès d’Adobe. Pour ce faire, contactez le service à la clientèle d’Adobe.

[!DNL Report Server] présente ce certificat numérique pour accéder à un composant serveur. Un administrateur du composant serveur peut restreindre l’accès aux ressources du serveur en fonction du nom commun ou des valeurs d’unité d’organisation qui apparaissent dans le certificat du client.

Les certificats numériques X.509 installés avec les applications Adobe permettent également à ses composants client et serveur d’échanger des informations via SSL (Secure Sockets Layer). SSL sécurise les transmissions via HTTP à l’aide d’un système de chiffrement de clé publique et privée. L’implémentation de SSL par Adobe prend en charge les clés RSA 1 024 bits et utilise un algorithme de chiffrement RC4 128 bits.

Outre la sécurité, le certificat numérique que vous installez fonctionne également comme une clé de licence qui vous permet d’exécuter l’installation [!DNL Report Server]. Pour fonctionner correctement, un certificat numérique doit être verrouillé par un noeud et à jour, sinon l’application ne démarre pas.

## Certificats verrouillés sur le noeud {#section-3338f1558e7844888dced8f395888744}

Un certificat verrouillé par un noeud est un certificat numérique qui a été enregistré sur l’ordinateur sur lequel il est installé. Le verrouillage de noeud associe de manière permanente un certificat à un identifiant de noeud spécifique (une valeur qui identifie de manière unique un ordinateur particulier). Pour verrouiller votre certificat par un noeud, votre ordinateur doit disposer d’un accès Internet au serveur Adobe License Server ou à un serveur proxy qui a accès au serveur License Server.

Si vous effectuez l’installation sur une machine qui ne peut pas accéder à Internet, vous devez obtenir et installer un certificat préverrouillé spécial, comme décrit dans [Utilisation de certificats numériques sur des machines sans accès](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) à Internet sur cette page.

Si vous effectuez l’installation sur une machine qui peut accéder à Internet, votre certificat numérique est verrouillé automatiquement au niveau du noeud la première fois que vous démarrez [!DNL Report Server]. Une fois le certificat verrouillé sur un noeud, il ne peut plus être utilisé sur un autre ordinateur. Si vous devez effectuer la migration [!DNL Report Server] vers un autre ordinateur, vous devez obtenir un nouveau certificat déverrouillé auprès d’Adobe.

## Certificats actuels {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Outre le fait d’être verrouillé sur un noeud, un certificat numérique doit être à jour. Pour rester à jour, votre certificat doit être régulièrement revalidé (généralement tous les 30 jours, mais peut varier selon votre accord avec Adobe). Si votre machine a accès à Internet, le processus de revalidation est complètement transparent. [!DNL Report Server] se connecte automatiquement au serveur de licences et valide à nouveau le certificat si nécessaire. Si votre ordinateur n’a pas accès à Internet, vous devez installer manuellement les certificats mis à jour, comme décrit dans la section suivante.

## Utilisation de certificats numériques sur des machines sans accès à Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Si vous effectuez l’installation sur une machine qui ne peut pas accéder à Internet, vous devez demander un certificat pré-verrouillé pour votre installation de [!DNL Report Server]. Un certificat pré-verrouillé est un certificat numérique qu’Adobe verrouille manuellement sur l’identifiant de noeud de l’ordinateur.

Pour demander un certificat pré-verrouillé, vous devez envoyer l’identifiant de noeud et le numéro de votre certificat au service à la clientèle Adobe. Pour obtenir l’identifiant de noeud pour votre ordinateur, contactez le service à la clientèle d’Adobe pour demander l’ [!DNL Node Identifier] utilitaire Adobe. Vous pouvez également obtenir l’identifiant de noeud à partir de l’alerte qui [!DNL Report Server] survient lorsqu’il tente de se connecter au serveur de licences et ne peut pas le faire. Lorsque vous recevez le certificat préverrouillé, installez-le comme décrit dans les deux dernières étapes des procédures [d’installation des certificats](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d)numériques.

Lorsque le certificat doit être revalidé, vous devez télécharger un nouveau certificat validé à partir du serveur de licences et le réinstaller sur votre ordinateur (sauf si votre accord avec Adobe indique le contraire).
