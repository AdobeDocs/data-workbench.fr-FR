---
description: Nouvelles fonctionnalités introduites dans Data Workbench 6.0.4, y compris les correctifs de bogues et les problèmes connus.
title: Notes de mise à jour Data Workbench 6.0
uuid: b348425e-3304-4db7-a280-479a34452bdb
exl-id: be69b3be-24e7-4a8c-9dc8-1360a9b6fb3a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1679'
ht-degree: 2%

---

# Notes de mise à jour Data Workbench 6.0

Nouvelles fonctionnalités introduites dans Data Workbench 6.0.4, y compris les correctifs de bogues et les problèmes connus.

## Nouvelles fonctionnalités {#section-1225066ea8f44cf68e42e019d0bca816}

Les outils de données (Insight 6.0) comprennent ces nouvelles fonctionnalités et visualisations pour ajouter des fonctionnalités de rapports et des outils d’analyse prédictive.

| Fonctionnalités du Data Workbench | Description |
|---|---|
| [Rapport de visualisation entonnoir](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | La visualisation Entonnoir vous permet de définir le flux de processus séquentiel de vos clients et de visualiser les abandons des visiteurs à chaque étape du processus. |
| [Clusterisation de visiteur](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | La mise en grappe vous permet d’exploiter les caractéristiques des clients afin de classer de manière dynamique les visiteurs et de générer des jeux de clusters en fonction des entrées de données sélectionnées pour l’analyse et le ciblage des clients. |
| [Analyse des corrélations](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | L’Analyse de la corrélation vous permet d’identifier rapidement les relations de données pertinentes afin d’étendre et d’améliorer votre analyse. |
| [Distribution DeviceAtlas mise à jour](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | Le fichier JSON DeviceAtlas sera désormais distribué dans un fichier .bundle (un fichier .tar.gz renommé) avec DeviceAtlas.dll et DeviceAtlas64.dll. |

## Exigences de mise à niveau du client {#section-f316103b48374b6eac77e8feb5c47ecf}

Suivez les tâches de mise à niveau suivantes pour les fonctionnalités client des outils de données (Insight 6.0) :

**Mise à jour du fichier .zbin pour le client**

Les outils de données prennent désormais en charge un éditeur de méthode d’entrée (IME) en tant que processus de saisie de texte secondaire qui vous permet de saisir des caractères internationaux à partir du clavier à l’aide d’une zone de texte flottante. Les outils de données prennent en charge l’anglais par défaut, mais vous permettent également de charger d’autres fichiers pour prendre en charge des langues internationales, comme un clavier chinois virtuel (Pinyin IME).

Un nouveau fichier de dictionnaire (un fichier .zbin) est requis par l&#39;application cliente avant la mise à jour vers la version 6.0. Vous pouvez obtenir le fichier .zbin requis à partir du profil Software and Docs (Softdocs).

Conditions préalables:

* Avant la mise à niveau vers le client Insight 6.0 et Report Server 6.0, l’administrateur Insight doit d’abord effectuer la mise à niveau vers Insight Server 6.0.
* L’administrateur d’Insight devra choisir un fichier zbin en fonction de la langue (en-us.zbin, zh-cn.zbin), copier le fichier de langue, le renommer en insight.zbin et placer le fichier renommé dans le répertoire racine du serveur de rapports où se trouve l’exécutable. Redémarrez ensuite le serveur de rapports Insight.

Pour plus d’informations sur la mise à niveau côté serveur, voir [Exigences de mise à niveau du serveur](../../../home/c-release-notes-insight/release-notes.md).

**Pour mettre à niveau le fichier zbin du client (de la version 5.x à la version 6.0)**

1. Pour vous assurer que le client n’est pas mis à jour à partir du serveur Insight pendant cette mise à niveau, définissez l’argument Insight.cfg sur false.

   ```
   Update Software = bool: false
   ```

1. Redémarrez le client Insight.
1. Accédez au profil Software and Docs (profil SoftDocs) et téléchargez le fichier **[!UICONTROL Insight.zbin]** requis : [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Copiez le fichier Insight.zbin dans le même dossier que le fichier Insight.exe.
1. Pour vous assurer que le client Insight est désormais mis à jour à partir du serveur Insight, définissez l’argument de fichier Insight.cfg sur true :

   ```
   Update Software = bool: true
   ```

1. Redémarrez le client.

   Votre client se synchronise avec le serveur et vous verrez un message indiquant que votre client est en train de télécharger. À la fin du téléchargement, vous recevrez un message vous demandant si vous souhaitez redémarrer votre client Insight.
1. Cliquez sur **OK** pour redémarrer le client.

   Le client va début et mettre à niveau vers la version 6.0.

1. Redémarrez le client pour que la synchronisation du client Insight.zbin prenne effet.

   Si vous obtenez le message suivant, cela signifie que le fichier zbin n’a pas été placé dans le dossier approprié à côté du fichier Insight.exe.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Pour corriger le problème, supprimez Insight.exe et renommez la dernière version de Insight.exe.old en Insight.exe, puis début à nouveau avec l’étape 1 ci-dessus.

## Exigences de mise à niveau du serveur {#section-d6edba8b36234957ba8d06b555667a5a}

Suivez les tâches de mise à niveau suivantes pour les fonctionnalités du serveur Insight 6.0 :

**Mettez à jour tous les packages** Insight Server 6.0. Insight 6.0 inclut des packages de serveurs qui doivent être mis à jour, y compris le nouveau profil Analyses prédictives.

>[!IMPORTANT]
>
>Il est recommandé aux utilisateurs de mettre à niveau leurs clusters de serveurs avec de nouvelles installations d’Insight Server 6.0 lors de la mise à jour.

Il est également recommandé aux clients de mettre à niveau leurs clusters de serveurs avec la nouvelle installation d’Insight Server 6.0.

## Mise à niveau de la grappe de serveurs

**Préparez le fichier de langue (fichier .zbin).** L’administrateur d’Insight sélectionne le  `<language>.zbin` fichier pour la langue requise (par exemple : en-us.zbin, zh-cn.zbin) situé dans le  `/localization/<language>.zbin` dossier. L’administrateur copie ensuite le fichier de langue et le renomme en &quot;insight.zbin&quot;.

Après avoir préparé le fichier de langue (.zbin), le client Insight et le serveur de rapports doivent tous deux être mis à jour. Le client Insight est mis à jour pendant le processus de mise à niveau du client [](../../../home/c-release-notes-insight/release-notes.md), mais dans la plupart des cas, l’administrateur Insight met à jour le serveur de rapports.

**Mettre à jour le serveur de rapports avec un fichier de langue (fichier .zbin)**.

Pour toutes les langues, Report Server 6.0 requiert le fichier &quot;insight.zbin&quot; copié dans le dossier racine du serveur de rapports.

Mettez à jour les fichiers de langue du serveur de rapports :

1. Ajoutez le fichier &quot;insight.zbin&quot; renommé dans le répertoire racine du serveur de rapports.
1. Le fichier de configuration du serveur de rapports (reportserver.cfg) requiert des paramètres de police pour les langues sur doublon-octets. Par exemple, le chinois nécessite l’ajout de polices à l’aide de SimSun :

   ```
   Report Server.cfg - Add Fonts 
   
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
   >Si aucun paramètre régional n’est spécifié, le serveur de rapports utilise par défaut la langue sélectionnée dans le fichier insight.zbin.

   Suivez les étapes pour lancer ReportServer en tant que service avec les paramètres régionaux :

   1. Lancez une invite de commandes en tant qu&#39;administrateur.
   1. Accédez au dossier d’installation de ReportServer.
   1. Saisissez la commande suivante pour début du service :

      * Pour l&#39;anglais : [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Pour le chinois : [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Pour vérifier si ReportServer s’exécute avec les paramètres corrects :

   1. Ouvrez le Gestionnaire de services Windows.
   1. Cliquez avec le bouton droit de la souris [!DNL Adobe Insight Report Server - Properties].

   Le chemin d&#39;accès à l&#39;exécutable contient les paramètres suivants :

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Modifiez le fichier de configuration de Profil pour les analyses** prédictives. L’administrateur d’Insight devra modifier le fichier profil.cfg personnalisé afin d’inclure le profil Analyses prédictives qui sera disponible dans Insight.

Exemple de l’entrée profil.cfg :

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**Mettez à jour le fichier** PAServer.cfg. Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le fichier PAServer.cfg pour gérer les envois de mise en grappe côté serveur.

Le profil personnalisé doit hériter du fichier PAServer.cfg du profil Predictive Analytics (Server\Profiles\Predictive Analytics\Dataset). Configurez et enregistrez PAServer.cfg pour chaque site d’implémentation.

>[!NOTE]
>
>Une fois que PAServer.cfg est configuré et enregistré sur un profil personnalisé, un redémarrage du serveur Insight est nécessaire sur l’ensemble du site.

**Mettre à niveau le serveur de rapports.** Vous devrez mettre à jour les polices et les paramètres de début pour le serveur de rapports.

Conditions préalables:

* Avant de mettre à niveau Report Server 6.0, l’administrateur Insight doit d’abord effectuer la mise à niveau vers Insight Server 6.0.
* Pour toutes les langues, Report Server 6.0 nécessite l’ajout d’Insight.zbin au dossier racine du serveur de rapports. Assurez-vous que `base/localization/<language>.zbin` est copié et renommé &quot;insight.zbin&quot;. Copiez-la à la racine du répertoire du serveur de rapports.

Mettez à jour les polices et les paramètres de Début :

1. Le serveur de rapports requiert un paramètre de police pour l’octet de doublon afin de produire une sortie dans différentes langues,

   par exemple :

   Report Server.cfg - Ajouter les polices

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Le paramètre de Report Server 6.0 doit être transmis dans la ligne de commande à des fins de localisation.

   Pour lancer le serveur de rapports en tant que service avec les paramètres régionaux :

   1. Arrêtez le service Report Server.
   1. Lancez une invite de commandes en tant qu&#39;administrateur.
   1. Accédez au dossier d’installation de Report Server.
   1. Saisissez la commande suivante pour début du service :

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Pour vérifier si le serveur de rapports s’exécute avec les paramètres corrects :

1. Ouvrir Windows Service Manager
1. Cliquez avec le bouton droit de la souris [!DNL Adobe Insight Report Server - Properties].
1. Le chemin d&#39;accès à l&#39;exécutable contient les paramètres suivants :

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Mettez à niveau le flux de données de SiteCatalyst pour Insight 6.0**. Le format du nom de fichier du flux de données de SiteCatalyst pour Insight 6.0 a été modifié.

Format actuel du nom de fichier :

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Nouveau format de nom de fichier :

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Cette modification n’affecte pas les utilisateurs actuellement déployés avec la version *wbench/ecom* du flux de données du SiteCatalyst.

La modification du format de fichier permet l’utilisation complète des déclarations Début Insight et Heure de fin pendant le traitement du journal. Cela permet au processus d’évaluer si le contenu du fichier doit être lu, plutôt que de filtrer tous les fichiers source à l’aide d’une recherche ligne par ligne.

Dans la plupart des cas, un processus de changement de nom a été mis en oeuvre à la réception du fichier afin de permettre l&#39;utilisation intégrale de cette fonctionnalité. Cette modification fournit par défaut la convention d’affectation de nom requise, sans nécessiter ni surcharge d’un processus secondaire.

Pour utiliser le nouveau flux de données de SiteCatalyst :

1. Déterminez comment le processus de réception va gérer le nouveau format de nom de fichier.

   Les scripts standard de changement de nom/déplacement déployés lors de l’implémentation déplacent les fichiers avec l’extension &quot;.gz&quot; et n’effectuent un changement de nom que si le nom de fichier correspond au format de nom de fichier avec le RSID précédent.

   Le nouveau format de nom de fichier :

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Evaluez les chemins d&#39;accès définis à la source du journal pour vous assurer que tous les fichiers seront lus.

   Si un script de changement de nom est déjà implémenté, vous définissez déjà vos sources de journal pour lire ce nouveau format de nom de fichier.

## Correctifs {#section-203f917dd6224114a1f801309c4c2cee}

* Désormais, la combinaison de clés permettant de quitter un espace de travail sans enregistrer les modifications a été mise à jour en **[!UICONTROL `<Ctrl>`+`<Backspace>`]**. Auparavant, vous aviez annulé les modifications et fermé un espace de travail en appuyant sur `<Ctrl>` + `<Delete>`.

## Notes de mise à jour Data Workbench 6.0.4{#data-workbench-release-notes}

Nouvelles fonctionnalités introduites dans Data Workbench 6.0.4, y compris les correctifs de bogues et les problèmes connus.

Pour vue les fonctionnalités et correctifs antérieurs de chaque version précédente, consultez les [archives des notes de mise à jour](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/release-notes/release-notes.html).

## Nouvelles fonctionnalités {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.0.4 inclut ces nouvelles fonctionnalités et visualisations pour ajouter des fonctionnalités de rapports et des outils d’analyse prédictive.

**Visualisation** du score de propension. Les outils de données calculent les scores pour chaque visiteur sous la forme d’une probabilité estimée qu’un événement spécifique se produise. La visualisation du score du Visiteur vous permet de créer une dimension de score qui donne une probabilité d’un événement spécifié pour chaque visiteur intéressé en fonction des variables d’entrée.

![](assets/visitor_scoring_visual.png)

Voir [Score de propension](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) pour plus d’informations sur cette fonctionnalité.

## Conditions requises pour la mise à niveau {#section-08bd6fe3da8740fcb19688e8cac6f223}

**L&#39;ID de source du journal doit être défini**. À partir de la version 6.04, si l&#39;ID de source du journal n&#39;est pas défini, vous obtenez l&#39;erreur suivante :

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

L&#39;enregistrement des lignes par source de journal a été ajouté dans le Data Workbench 6.0 et peut être défini dans le fichier Traitement du journal de profil personnalisé.cfg en ajoutant un identifiant de source de journal nommé de manière unique. Si vous disposez d&#39;un ID de source de journal vide, vous pouvez voir des problèmes de traitement du journal tels que la lecture incomplète des données de source de journal et d&#39;autres incohérences.

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**Capacité à déléguer les ressources de l&#39;UFS**

Dans [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg], vous pouvez désormais spécifier des unités de serveur de fichiers distinctes (FSU) pour les serveurs de normalisation et de Liste source. Ces services ne sont plus liés au Principal FSU.

>[!NOTE]
>
>Si le serveur de Listes n&#39;est pas spécifié, le serveur de Listes hérite des paramètres de configuration du serveur de normalisation.

Exemple dans le fichier [!DNL cluster.cfg].

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## Corrections de bogues {#section-3b4b85a35f534288adf8a5246ef028cc}

* Dans Data Workbench 6.0, la matrice de corrélation et le créateur de clusters ne prenaient pas en charge l’option Calculer en arrière-plan. Ceci est maintenant corrigé dans la version 6.0.4.
* Auparavant, si vous aviez une sélection dans l’entonnoir et que vous aviez supprimé une étape, une violation d’accès pouvait se produire. Ce problème a été résolu.
* Correction d’une condition de verrouillage potentielle dans l’exportation de segment qui pouvait provoquer des problèmes dans des conditions de charge importante.
