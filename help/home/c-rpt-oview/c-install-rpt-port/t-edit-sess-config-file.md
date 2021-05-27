---
description: Le portail de rapports utilise les informations d’un fichier de configuration nommé global.asa pour initialiser les sessions utilisateur.
title: Modifier le fichier de configuration de la session
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Modifier le fichier de configuration de la session{#edit-the-session-configuration-file}

Le portail de rapports utilise les informations d’un fichier de configuration nommé global.asa pour initialiser les sessions utilisateur.

Lorsque vous installez [!DNL Report Portal], vous devez modifier ce fichier comme indiqué. Le fichier [!DNL global.asa] se trouve dans le dossier \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ne modifiez aucun autre paramètre de ce fichier de configuration.

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le fichier [!DNL global.asa] dans un éditeur de texte tel que Notepad.
1. Facultatif. Pour permettre aux utilisateurs d’accéder à [!DNL Report Portal] sans authentification, définissez la valeur du paramètre Session(&quot;In&quot;) sur true. La valeur par défaut est false, ce qui authentifie tous les utilisateurs qui tentent d’accéder à [!DNL Report Portal].
1. Si votre [!DNL Report Portal] est installé sur un lecteur autre que le lecteur C, remplacez la valeur du paramètre Session(&quot;Drive&quot;) par l’emplacement de lecteur approprié.
1. Pour le paramètre Session(&quot;DBPath&quot;), modifiez la valeur afin de refléter le chemin d’accès à la base de données contenant les informations nécessaires à l’authentification des utilisateurs [!DNL Report Portal]. N’incluez pas la lettre de lecteur, mais veillez à inclure une barre oblique.

   Exemple : [!DNL /Inetpub/wwwroot/Portal/data/]

1. Enregistrez le fichier.
1. Pour vérifier que les fichiers [!DNL Report Portal] ont été installés correctement et qu’ils peuvent être atteints via leur répertoire virtuel désigné, ouvrez la page suivante dans votre navigateur :

   http://*YourServerAddress*/*YourPortalName*

   Exemple : [!DNL http://localhost/VisualReportPortal]

   Si les [!DNL Report Portal] ASP ont été installés correctement, la page de connexion au portail devrait s’afficher. Si vous ne voyez pas cette page, vérifiez que les ASP sont activés sur votre IIS et vérifiez deux fois les mappages de vos répertoires virtuels.
