---
description: Pour toutes les langues, Report Server 6.0 et versions ultérieures requiert le fichier "insight.zbin" copié dans le dossier racine du serveur de rapports.
solution: Analytics
title: Mettre à jour le serveur de rapports avec un fichier de langue (.zbin)
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mettre à jour le serveur de rapports avec un fichier de langue (.zbin){#update-report-server-with-a-language-file-zbin-file}

Pour toutes les langues, Report Server 6.0 et versions ultérieures requiert le fichier &quot;insight.zbin&quot; copié dans le dossier racine du serveur de rapports.

Mettez à jour les fichiers de langue du serveur de rapports :

1. Ajoutez le fichier &quot;insight.zbin&quot; renommé dans le répertoire racine du serveur de rapports.
1. Le fichier de configuration du serveur de rapports (reportserver.cfg) requiert des paramètres de police pour les langues codées sur deux octets. Par exemple, le chinois nécessite l’ajout de polices à l’aide de SimSun :

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Un paramètre pour Report Server 6.0 doit être transmis dans la ligne de commande pour la localisation, par exemple :

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Si aucun paramètre régional n’est spécifié, le serveur de rapports utilise l’anglais par défaut.

   Suivez les étapes pour lancer ReportServer en tant que service avec les paramètres régionaux :

   1. Lancez une invite de commande en tant qu’administrateur.
   1. Accédez au dossier d’installation de ReportServer.
   1. Saisissez la commande suivante pour démarrer le service :

      * Pour l&#39;anglais : [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Pour le chinois : [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Pour vérifier si ReportServer est exécuté avec les paramètres corrects :

   1. Ouvrez le Gestionnaire de services Windows.
   1. Right-click [!DNL Adobe Insight Report Server - Properties].
   Le chemin d&#39;accès au fichier exécutable contient les paramètres suivants :

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

