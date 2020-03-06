---
description: Le portail des rapports utilise les informations contenues dans un fichier de configuration appelé global.asa pour initialiser les sessions utilisateur.
solution: Analytics
title: Modification du fichier de configuration de session
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du fichier de configuration de session{#edit-the-session-configuration-file}

Le portail des rapports utilise les informations contenues dans un fichier de configuration appelé global.asa pour initialiser les sessions utilisateur.

Lorsque vous installez [!DNL Report Portal], vous devez modifier ce fichier comme indiqué. Le [!DNL global.asa] fichier réside dans le dossier \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ne modifiez aucun autre paramètre de ce fichier de configuration.

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL global.asa] fichier dans un éditeur de texte tel que le Bloc-notes.
1. Facultatif. Pour permettre aux utilisateurs d’accéder [!DNL Report Portal] sans authentification, définissez la valeur du paramètre Session(&quot;In&quot;) sur true. La valeur par défaut est false, ce qui authentifie tous les utilisateurs qui tentent d’y accéder [!DNL Report Portal].
1. Si votre [!DNL Report Portal] ordinateur est installé sur un lecteur autre que le lecteur C, remplacez la valeur du paramètre Session(&quot;Drive&quot;) par l’emplacement du lecteur approprié.
1. Pour le paramètre Session(&quot;DBPath&quot;), modifiez la valeur afin de refléter le chemin d’accès à la base de données contenant les informations nécessaires à l’authentification des [!DNL Report Portal] utilisateurs. N’incluez pas la lettre du lecteur, mais veillez à inclure une barre oblique de fin.

   Exemple : [!DNL /Inetpub/wwwroot/Portal/data/]

1. Enregistrez le fichier.
1. Pour vérifier que les [!DNL Report Portal] fichiers ont été correctement installés et qu’ils peuvent être accessibles via leur répertoire virtuel désigné, ouvrez la page suivante dans votre navigateur :

   http://*YourServerAddress*/*YourPortalName*

   Exemple : [!DNL http://localhost/VisualReportPortal]

   Si les [!DNL Report Portal] ASP ont été correctement installés, vous devriez voir la page de connexion du portail. Si vous ne voyez pas cette page, vérifiez que les ASP sont activés sur vos services IIS et double-vérifiez vos mappages de répertoires virtuels.

