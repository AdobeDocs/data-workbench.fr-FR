---
description: Nouvelles fonctionnalités introduites dans les Outils de données version 6.0.4, y compris les correctifs et les problèmes connus.
solution: Analytics
title: Notes de mise à jour des outils de données version 6.0
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Notes de mise à jour des outils de données version 6.0

Nouvelles fonctionnalités introduites dans les Outils de données version 6.0.4, y compris les correctifs et les problèmes connus.

## Nouvelles fonctionnalités {#section-1225066ea8f44cf68e42e019d0bca816}

Les outils de données (Insight 6.0) incluent ces nouvelles fonctionnalités et visualisations pour ajouter des fonctionnalités de création de rapports et des outils d’analyse prédictive.

| Fonctionnalités des outils de données | Description |
|---|---|
| [Visualisation de l&#39;entonnoir](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | La visualisation Entonnoir vous permet de définir le flux de processus séquentiel de vos clients et d’afficher les abandons des visiteurs à chaque étape du processus. |
| [Clusterisation de visiteur](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | La mise en grappe vous permet d’exploiter les caractéristiques du client pour classer dynamiquement les visiteurs et générer des jeux de grappes en fonction des entrées de données sélectionnées pour l’analyse et le ciblage des clients. |
| [Analyse des corrélations](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | L’analyse des corrélations vous permet d’identifier rapidement les relations de données pertinentes afin d’étendre et d’améliorer votre analyse. |
| [Distribution DeviceAtlas mise à jour](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | Le fichier JSON DeviceAtlas sera désormais distribué dans un fichier .bundle (un fichier .tar.gz renommé), ainsi que DeviceAtlas.dll et DeviceAtlas64.dll. |

## Configuration requise pour la mise à niveau du client {#section-f316103b48374b6eac77e8feb5c47ecf}

Effectuez les tâches de mise à niveau suivantes pour les fonctionnalités du client Outils de données (Insight 6.0) :

**Mise à jour du fichier .zbin pour le client**

Les outils de données prennent désormais en charge un éditeur de méthode d’entrée (IME) en tant que processus secondaire de saisie de texte qui vous permet de saisir des caractères internationaux à partir du clavier à l’aide d’une zone de texte flottante. Les outils de données prennent en charge l’anglais par défaut, mais vous permettent également de charger d’autres fichiers pour prendre en charge des langues internationales, comme un clavier chinois virtuel (Pinyin IME).

Un nouveau fichier de dictionnaire (fichier .zbin) est requis par l’application cliente avant la mise à jour vers la version 6.0. Vous pouvez obtenir le fichier .zbin requis à partir du profil Software and Docs (Softdocs).

Conditions préalables:

* Avant de procéder à la mise à niveau vers le client Insight 6.0 et vers Report Server 6.0, l’administrateur Insight doit d’abord effectuer la mise à niveau vers Insight Server 6.0.
* L’administrateur d’Insight devra choisir un fichier zbin en fonction de la langue (en-us.zbin, zh-cn.zbin), copier le fichier de langue, le renommer en insight.zbin et placer le fichier renommé dans le répertoire racine du serveur de rapports où se trouve le fichier exécutable. Redémarrez ensuite le serveur de rapports Insight.

Pour plus d’informations sur la mise à niveau côté serveur, voir Conditions requises [pour la mise à niveau du](../../../home/c-release-notes-insight/release-notes.md) serveur.

**Pour mettre à niveau le fichier zbin pour le client (de la version 5.x à la version 6.0)**

1. Pour vous assurer que le client n’est pas mis à jour depuis le serveur Insight pendant cette mise à niveau, définissez l’argument Insight.cfg sur false.

   ```
   Update Software = bool: false
   ```

1. Redémarrez le client Insight.
1. Accédez au profil Software and Docs (profil SoftDocs) et téléchargez le **[!UICONTROL Insight.zbin]** fichier requis : [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Copiez le fichier Insight.zbin dans le même dossier que le fichier Insight.exe.
1. Pour vous assurer que le client Insight est désormais mis à jour à partir du serveur Insight, définissez l’argument de fichier Insight.cfg sur true :

   ```
   Update Software = bool: true
   ```

1. Redémarrez le client.

   Votre client se synchronise avec le serveur et vous verrez un message indiquant que votre client est en train de télécharger. A la fin du téléchargement, vous recevrez un message vous demandant si vous souhaitez redémarrer votre client Insight.
1. Cliquez sur **OK** pour redémarrer le client.

   Le client démarrera et mettra à niveau vers la version 6.0.

1. Redémarrez le client pour que la synchronisation du client Insight.zbin prenne effet.

   Si vous obtenez le message suivant, cela signifie que le fichier zbin n’a pas été placé dans le dossier approprié à côté du fichier Insight.exe.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Pour corriger le problème, supprimez Insight.exe et renommez la dernière version de Insight.exe.old en Insight.exe, puis recommencez avec l’étape 1 ci-dessus.

## Configuration requise pour la mise à niveau du serveur {#section-d6edba8b36234957ba8d06b555667a5a}

Effectuez les tâches de mise à niveau suivantes pour les fonctionnalités du serveur Insight 6.0 :

**Mettez à jour tous les packages** Insight Server 6.0. Insight 6.0 inclut des packages de serveur qui doivent être mis à jour, y compris le nouveau profil Analyses prédictives.

>[!IMPORTANT]
>
>Il est recommandé aux utilisateurs de mettre à niveau leurs clusters de serveurs avec de nouvelles installations d’Insight Server 6.0 lors de la mise à jour.

Il est également recommandé aux clients de mettre à niveau leurs clusters de serveurs avec une nouvelle installation d’Insight Server 6.0.

## Mise à niveau de la grappe de serveurs

**Préparez le fichier de langue (fichier .zbin).** L’administrateur d’Insight sélectionne le `<language>.zbin` fichier pour la langue requise (par exemple : en-us.zbin , zh-cn.zbin) situé dans le `/localization/<language>.zbin` dossier. L’administrateur copie alors le fichier de langue et le renomme &quot;insight.zbin&quot;.

Après avoir préparé le fichier de langue (.zbin), le client Insight et le serveur de rapports doivent être mis à jour. Le client Insight est mis à jour pendant le processus [de mise à niveau du](../../../home/c-release-notes-insight/release-notes.md)client, mais dans la plupart des cas, l’administrateur Insight met à jour le serveur de rapports.

**Mettez à jour le serveur de rapports avec un fichier de langue (.zbin)**.

Pour toutes les langues, Report Server 6.0 requiert le fichier &quot;insight.zbin&quot; copié dans le dossier racine du serveur de rapports.

Mettez à jour les fichiers de langue du serveur de rapports :

1. Ajoutez le fichier &quot;insight.zbin&quot; renommé dans le répertoire racine du serveur de rapports.
1. Le fichier de configuration du serveur de rapports (reportserver.cfg) requiert des paramètres de police pour les langues codées sur deux octets. Par exemple, le chinois nécessite l’ajout de polices à l’aide de SimSun :

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

**Modification du fichier de configuration du profil pour les analyses** prédictives. L’administrateur d’Insight devra modifier le fichier profile.cfg personnalisé pour inclure le profil Analytics prédictif qui sera disponible dans Insight.

Exemple de l’entrée profile.cfg :

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

Le profil personnalisé doit hériter du fichier PAServer.cfg du profil Analyses prédictives (Server\Profiles\Predictive Analytics\Dataset). Configurez et enregistrez PAServer.cfg pour votre site d’implémentation.

>[!NOTE]
>
>Une fois que PAServer.cfg est configuré et enregistré dans un profil personnalisé, un redémarrage du serveur Insight est nécessaire sur l’ensemble du site.

**Mettre à niveau le serveur de rapports.** Vous devez mettre à jour les polices et les paramètres de démarrage du serveur de rapports.

Conditions préalables:

* Avant de mettre à niveau Report Server 6.0, l’administrateur Insight doit d’abord effectuer la mise à niveau vers Insight Server 6.0.
* Pour toutes les langues, Report Server 6.0 nécessite l’ajout d’Insight.zbin au dossier racine du serveur de rapports. Assurez-vous que le fichier `base/localization/<language>.zbin` est copié et renommé &quot;insight.zbin&quot;. Copiez-le à la racine du répertoire du serveur de rapports.

Mettez à jour les paramètres Polices et Démarrage :

1. Le serveur de rapports requiert un paramètre de police pour une sortie sur deux octets dans différentes langues,

   par exemple :

   Report Server.cfg - Ajouter des polices

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Le paramètre du serveur de rapports 6.0 doit être transmis dans la ligne de commande à des fins de localisation.

   Pour lancer le serveur de rapports en tant que service avec les paramètres régionaux :

   1. Arrêtez le service Report Server.
   1. Lancez une invite de commande en tant qu’administrateur.
   1. Accédez au dossier d’installation du serveur de rapports.
   1. Saisissez la commande suivante pour démarrer le service :

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Pour vérifier si le serveur de rapports est en cours d’exécution avec les paramètres corrects :

1. Ouvrir Windows Service Manager
1. Right-click [!DNL Adobe Insight Report Server - Properties].
1. Le chemin d&#39;accès au fichier exécutable contient les paramètres suivants :

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Mettez à niveau le flux de données SiteCatalyst pour Insight 6.0**. Le format du nom de fichier du flux de données SiteCatalyst pour Insight 6.0 a changé.

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
>Cette modification n’affecte pas les utilisateurs actuellement déployés avec la version *wbench/ecom* du flux de données SiteCatalyst.

Le changement de format de nom de fichier permet l’utilisation complète des déclarations d’heure de début et de fin d’Insight pendant le traitement du journal. Cela permet au processus d’évaluer si le contenu du fichier doit être lu, plutôt que de filtrer tous les fichiers source à l’aide d’une recherche ligne par ligne.

Dans la plupart des cas, un processus de changement de nom a été mis en oeuvre à la réception du fichier afin de permettre l’utilisation intégrale de cette fonctionnalité. Cette modification fournit par défaut la convention d’affectation de nom requise sans nécessiter ni surcharge d’un processus secondaire.

Pour utiliser le nouveau flux de données SiteCatalyst :

1. Déterminez comment le processus de réception gérera le nouveau format de nom de fichier.

   Les scripts standard de changement de nom/déplacement déployés au cours de l’implémentation déplacent les fichiers avec l’extension &quot;.gz&quot; et ne les renomment que si le nom de fichier correspond au format du nom de fichier avec le RSID précédent.

   Nouveau format de nom de fichier :

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Evaluez les chemins d’accès aux sources du journal définis pour vous assurer que tous les fichiers seront lus.

   Si un script de changement de nom est déjà implémenté, vous définissez déjà vos sources de journal pour lire ce nouveau format de nom de fichier.

## Correctifs {#section-203f917dd6224114a1f801309c4c2cee}

* Désormais, la combinaison de touches permettant de quitter un espace de travail sans enregistrer les modifications a été mise à jour sur **[!UICONTROL `<Ctrl>`+`<Backspace>`]**. Auparavant, vous aviez annulé les modifications et fermé un espace de travail en appuyant sur`<Ctrl>`+`<Delete>`.

## Data Workbench 6.0.4 Release Notes{#data-workbench-release-notes}

Nouvelles fonctionnalités introduites dans les Outils de données version 6.0.4, y compris les correctifs et les problèmes connus.

Pour consulter les fonctionnalités et correctifs antérieurs de chaque version précédente, consultez les archives [des notes de](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)mise à jour.

## Nouvelles fonctionnalités {#section-2-1225066ea8f44cf68e42e019d0bca816}

Les outils de données version 6.0.4 incluent ces nouvelles fonctionnalités et visualisations pour ajouter des fonctionnalités de création de rapports et des outils d’analyse prédictive.

**Visualisation** du score de propension. Les outils de données calculent les scores de chaque visiteur sous forme d’une probabilité estimée qu’un événement spécifique puisse se produire. La visualisation Scores des visiteurs vous permet de créer une dimension de score qui donne une probabilité d’événement spécifique pour chaque visiteur intéressé en fonction des variables d’entrée.

![](assets/visitor_scoring_visual.png)

Voir Score de [propension](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) pour plus d’informations sur cette fonctionnalité.

## Conditions requises pour la mise à niveau {#section-08bd6fe3da8740fcb19688e8cac6f223}

**L&#39;ID de source du journal doit être défini**. À partir de la version 6.04, si l&#39;ID de source du journal n&#39;est pas défini, vous obtenez l&#39;erreur suivante :

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

L’enregistrement des lignes par source de journal a été ajouté dans les Outils de données version 6.0 et peut être défini dans le fichier de profil personnalisé Log Processing.cfg en ajoutant un identifiant de source de journal nommé de manière unique. Si vous disposez d’un ID de source de journal vide, vous pouvez constater des problèmes de traitement du journal, tels que la lecture incomplète des données de source de journal et d’autres incohérences.

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

**Possibilité de déléguer des ressources FSU**

Dans [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg], vous pouvez désormais spécifier des unités FSU (File Server Units) distinctes pour les serveurs Normaliser et Liste source. Ces services ne sont plus liés au Maître de la FSU.

>[!NOTE]
>
>Si le serveur de liste n’est pas spécifié, le serveur de liste hérite des paramètres de configuration du serveur de normalisation.

Example in the [!DNL cluster.cfg] file.

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

* Dans les Outils de données version 6.0, la matrice de corrélation et le créateur de grappes ne prenaient pas en charge le calcul en arrière-plan. Ceci est maintenant corrigé dans la version 6.0.4.
* Auparavant, si vous aviez une sélection dans l’entonnoir et que vous aviez supprimé une étape, une violation d’accès pouvait se produire. Ce problème a été résolu.
* Correction d’une condition de verrouillage potentielle dans l’exportation de segment qui pouvait entraîner des problèmes dans des conditions de charge importante.
