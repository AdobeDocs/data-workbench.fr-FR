---
description: Instructions pour ajouter le fichier Visual_sciences.dll au chemin d’accès de la bibliothèque Java Tomcat.
title: Modification du chemin d’accès à la bibliothèque Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du chemin d’accès à la bibliothèque Java{#modify-the-java-library-path}

Instructions pour ajouter le fichier Visual_sciences.dll au chemin d’accès de la bibliothèque Java Tomcat.

1. Sur votre serveur Windows, accédez au répertoire d’installation de Tomcat. (Tomcat > bin)
1. Sous le dossier bin, exécutez Tomcat9w.exe (gestionnaire de service de démon commun).

Dans l’onglet Java, sous Options Java, ajoutez une nouvelle ligne :

```
-Djava.library.path=C:\Sensor directory
```

Emplacement du fichier C:\Sensor directory is the directory containing the visual_sciences.dll.
