---
description: Le fichier JSON DeviceAtlas sera désormais distribué dans un fichier .bundle (un fichier .tar.gz renommé), ainsi que dans les fichiers DeviceAtlas.dll et DeviceAtlas64.dll.
solution: Analytics
title: Distribution DeviceAtlas
topic: Data workbench
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribution DeviceAtlas{#deviceatlas-distribution}

Le fichier JSON DeviceAtlas sera désormais distribué dans un fichier .bundle (un fichier .tar.gz renommé), ainsi que dans les fichiers DeviceAtlas.dll et DeviceAtlas64.dll.

Lorsque l’administrateur met à niveau Insight Server vers la version 6.0, le fichier DeviceAtlas.bundle est inclus dans le package de mise à niveau du profil Software and Docs (profil logiciel) situé à l’emplacement suivant :

[!DNL Server Packages > v6.00 > Server_6.00.zip]

Le fichier DeviceAtlas.bundle est extrait vers [!DNL Server\Lookups\DeviceAtlas].

Le fichier DeviceAtlas.bundle doit être placé dans un répertoire synchronisé avec les DPU, et le fichier DeviceAtlas.cfg correspondant au nouveau composant DeviceAtlasComponent doit être placé dans le répertoire &quot;Composants pour les serveurs de traitement&quot; sur le maître de synchronisation. Lorsque le fichier DeviceAtlas.bundle est modifié, l’appel de recherche DeviceAtlas suivant obtient des résultats en fonction de l’API et/ou du fichier JSON mis à jour.

## Modification du fichier Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

Les transformations DeviceAtlas n’auront plus besoin de spécifier le chemin d’accès au fichier JSON. Tout élément DeviceAtlasTransformation précédent défini dans le fichier transformation.cfg ne doit plus inclure le paramètre File qui pointe vers le fichier JSON obscurci.

Cet exemple de fichier Transformation.cfg montre l&#39;argument File qui doit être supprimé pour éviter toute confusion. (Le laisser là-bas ne causera pas de mal, mais seulement une confusion potentielle parce qu&#39;il sera ignoré.)

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## Modification du fichier DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Il s’agit d’un exemple de l’ [!DNL component] argument requis dans le fichier DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Ce fichier DeviceAtlas.bundle sera traité comme un fichier de configuration du point de vue de la fonctionnalité de synchronisation des profils. En outre, les données JSON et la DLL seront utilisées au niveau du composant plutôt qu’au niveau de la transformation individuelle.

Un nouveau composant DeviceAtlasComponent, au démarrage, trouve le conglomérat .bundle, désobscurcit le fichier JSON en mémoire, extrait les fichiers dans un répertoire temporaire et charge la DLL appropriée pour la plate-forme en cours d&#39;exécution. Ce composant surveille également les modifications apportées au fichier d’assemblage et recharge automatiquement les fichiers DLL et .cfg en cas de modification.

## Exécution de DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Une configuration appropriée fait une grande différence dans le temps nécessaire à la transformation. La transformation peut être configurée pour s&#39;exécuter une seule fois par visiteur et par session pour permettre à DeviceAtlas d&#39;accélérer le processus.

**S’il est déployé à l’aide du fichier Log Processing.cfg**:

Exécutez les transformations deux fois.

1. Recherchez uniquement le [!DNL mobile id] champ, puis
1. Créez des conditions pour ignorer le champ [!DNL mobile id] , puis recherchez le reste des champs.

**S’il est déployé à l’aide de Transformation.cfg**:

Déployez comme à l’étape 1 du traitement du journal ci-dessus ou utilisez des lignes croisées pour prendre en charge un paramètre conditionnel.

* Lignes croisées (Cross-Rows): saisit la clé de session précédente. Ensuite, déterminez si la clé de session en cours est différente de celle trouvée avec les lignes croisées. Si c&#39;est le cas, la transformation DeviceAtlas ne s&#39;exécutera que sur un enregistrement par session.

