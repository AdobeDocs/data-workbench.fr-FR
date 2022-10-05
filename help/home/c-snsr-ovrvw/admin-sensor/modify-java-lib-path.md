---
description: Instructions pour l’ajout du fichier Visual_sciences.dll au chemin d’accès de la bibliothèque Java Tomcat.
title: Modification du chemin d’accès à la bibliothèque Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# Modification du chemin d’accès à la bibliothèque Java{#modify-the-java-library-path}

{{eol}}

Instructions pour l’ajout du fichier Visual_sciences.dll au chemin d’accès de la bibliothèque Java Tomcat.

1. Sur votre serveur Windows, accédez au répertoire d’installation de Tomcat. (Tomcat > bin)
1. Sous le dossier bin, exécutez Tomcat9w.exe (gestionnaire de service de démon commun).

Dans l’onglet Java , sous Options Java, ajoutez une nouvelle ligne :

```
-Djava.library.path=C:\Sensor directory
```

Où le fichier C:\Sensor directory is the directory containing the visual_sciences.dll.
