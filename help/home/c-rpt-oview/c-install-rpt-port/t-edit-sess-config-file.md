---
description: Le portail de rapports utilise les informations d’un fichier de configuration nommé global.asa pour initialiser les sessions utilisateur.
title: Modifier le fichier de configuration de la session
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Modifier le fichier de configuration de la session{#edit-the-session-configuration-file}

{{eol}}

Le portail de rapports utilise les informations d’un fichier de configuration nommé global.asa pour initialiser les sessions utilisateur.

Lors de l’installation [!DNL Report Portal], vous devez modifier ce fichier comme indiqué. Le [!DNL global.asa] réside dans le dossier \*PortalName*\PortalASP\.

>[!NOTE]
>
>Ne modifiez aucun autre paramètre de ce fichier de configuration.

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL global.asa] dans un éditeur de texte tel que le Bloc-notes.
1. Facultatif. Pour permettre aux utilisateurs d’accéder à [!DNL Report Portal] sans authentification, remplacez la valeur du paramètre Session(&quot;In&quot;) par true. La valeur par défaut est false, ce qui authentifie tous les utilisateurs qui tentent d’accéder à [!DNL Report Portal].
1. Si votre [!DNL Report Portal] est installé sur un lecteur autre que le lecteur C, remplacez la valeur du paramètre Session(&quot;Drive&quot;) par l’emplacement de lecteur approprié.
1. Pour le paramètre Session(&quot;DBPath&quot;), modifiez la valeur afin de refléter le chemin d’accès à la base de données contenant les informations nécessaires à l’authentification. [!DNL Report Portal] utilisateurs. N’incluez pas la lettre de lecteur, mais veillez à inclure une barre oblique.

   Exemple : [!DNL /Inetpub/wwwroot/Portal/data/]

1. Enregistrez le fichier.
1. Pour vérifier que la variable [!DNL Report Portal] Les fichiers ont été installés correctement et peuvent être atteints via leur répertoire virtuel désigné, ouvrez la page suivante dans votre navigateur :

   https://*YourServerAddress*/*YourPortalName*

   Exemple : [!DNL https://localhost/VisualReportPortal]

   Si la variable [!DNL Report Portal] Les ASP ont été installés correctement, la page de connexion du portail devrait s’afficher. Si vous ne voyez pas cette page, vérifiez que les ASP sont activés sur votre IIS et vérifiez deux fois les mappages de vos répertoires virtuels.
