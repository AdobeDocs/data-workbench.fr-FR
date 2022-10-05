---
description: Adobe utilise des certificats numériques au format X.509 pour identifier et authentifier les composants de client et de serveur qui constituent une implémentation.
title: Compréhension des certificats numériques
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 54%

---

# Compréhension des certificats numériques{#understanding-digital-certificates}

{{eol}}

Adobe utilise des certificats numériques au format X.509 pour identifier et authentifier les composants de client et de serveur qui constituent une implémentation.

Lors de l’installation [!DNL Report Server], vous devez installer le certificat numérique qui autorise une personne nommée (par exemple Jane Smith) à utiliser l’application client installée.

>[!NOTE]
>
>Si vous devez migrer [!DNL Report Server] sur une autre machine ou un autre utilisateur nommé, vous devez obtenir un nouveau certificat auprès d’Adobe. Pour ce faire, contactez le service clientèle d’Adobe.

[!DNL Report Server] présente ce certificat numérique pour accéder à un composant de serveur. Un administrateur du composant de serveur peut limiter l’accès aux ressources du serveur selon le nom commun ou les valeurs d’unité organisationnelle apparaissant dans le certificat du client.

Les certificats numériques X.509 installés avec des applications Adobe permettent également à ses composants de client et de serveur d’échanger des informations par le biais du protocole SSL (Secure Sockets Layer). Le protocole SSL sécurise les transmissions par HTTP à l’aide d’un système de cryptage de clé public et privé. La mise en œuvre du protocole SSL par Adobe prend en charge les clés RSA 1 024 bits et utilise un algorithme de chiffrement RC4 128 bits.

Outre la sécurité, le certificat numérique que vous installez fonctionne également comme une clé de licence qui vous permet d’exécuter la [!DNL Report Server]. Pour fonctionner correctement, un certificat numérique doit être fixe et en cours, sinon l’application ne démarre pas.

## Certificats fixes {#section-3338f1558e7844888dced8f395888744}

Un certificat fixe est un certificat numérique enregistré sur la machine sur laquelle il est installé. Le processus de fixation associe de manière permanente un certificat à un identifiant fixe spécifique (une valeur qui identifie de manière unique une machine en particulier). Pour fixer votre certificat, votre machine doit disposer d’un accès Internet au serveur de licences Adobe ou à un serveur proxy ayant accès au serveur de licences.

Si vous effectuez l’installation sur une machine sans accès à Internet, vous devez obtenir et installer un certificat préverrouillé spécial, comme décrit dans la section [Utilisation de certificats numériques sur des machines sans accès à Internet](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) sur cette page.

Si vous effectuez l’installation sur une machine qui peut accéder à Internet, votre certificat numérique est automatiquement verrouillé la première fois que vous démarrez. [!DNL Report Server]. Une fois le processus de fixation terminé, le certificat ne peut être utilisé sur aucune autre machine. Si vous devez migrer [!DNL Report Server] sur une autre machine, vous devez obtenir un nouveau certificat déverrouillé depuis Adobe.

## Certificats en cours {#section-b4053ab714514dfb97ea7f61bbb8da1e}

En plus d’être fixe, un certificat numérique doit être en cours. Pour rester à jour, votre certificat doit être régulièrement revalidé (généralement tous les 30 jours, mais cela peut varier en fonction de votre contrat avec Adobe). Si votre machine dispose d’un accès Internet, le processus de revalidation est entièrement transparent. [!DNL Report Server] se connecte automatiquement au serveur de licences et revalide le certificat si nécessaire. Si votre machine ne dispose pas d’un accès à Internet, vous devez installer manuellement les certificats à jour comme le décrit la section suivante.

## Utilisation de certificats numériques sur des machines sans accès à Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Si vous effectuez l’installation sur une machine sans accès à Internet, vous devez demander un certificat préverrouillé pour votre installation d’[!DNL Report Server]. Un certificat préverrouillé est un certificat numérique verrouillé manuellement par Adobe sur l’identifiant fixe de la machine.

Pour demander un certificat préverrouillé, vous devez envoyer l’identifiant fixe ainsi que votre numéro de certificat au service clientèle d’Adobe. Pour obtenir l’identifiant de noeud de votre ordinateur, contactez l’assistance clientèle d’Adobe pour demander l’Adobe. [!DNL Node Identifier] Utilitaire. Vous pouvez également obtenir l’identifiant de noeud à partir de l’alerte qui [!DNL Report Server] des problèmes lorsqu’il tente de se connecter au serveur de licences et ne le peut pas. Lorsque vous recevez le certificat préverrouillé, procédez à son installation comme la décrivent les deux dernières étapes des [Procédures d’installation des certificats numériques](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

Lorsque le certificat doit être revalidé, vous devez télécharger un nouveau certificat validé à partir du serveur de licences et le réinstaller sur votre machine (sauf si votre accord avec des états Adobes le prévoit).
