---
description: Configurez les dimensions temporelles pour qu’elles s’affichent correctement pour les paramètres régionaux.
title: Localisation des dimensions temporelles
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
exl-id: 950fe70b-a687-4b9c-b29f-555139740809
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Localisation des dimensions temporelles{#localizing-time-dimensions}

{{eol}}

Configurez les dimensions temporelles pour qu’elles s’affichent correctement pour les paramètres régionaux.

Vous pouvez configurer le format d’affichage des dimensions temporelles en fonction des paramètres régionaux dans la variable **[!DNL Standard Time Dimensions.cfg]** fichier (situé par défaut à l’adresse **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimensions.cfg]**).

Par exemple, en Amérique du Nord, vous pouvez exprimer la date du 3 mai 2015 comme 5/3/15, ou **`%m/%d/%y`**. Cependant, dans d&#39;autres parties du monde, cela pourrait être interprété comme `%d/%m/%y`ou le 5 mars 2015 en raison d’une ambiguïté des valeurs. Pour éviter cette situation, un administrateur peut modifier le format affiché afin de répondre aux attentes des utilisateurs dans un paramètre régional.

## 1. Remplacement des Dimensions de temps par défaut dans le fichier Dimensions de temps standard.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Pour activer cette fonction, l’administrateur doit remplacer les valeurs par défaut en modifiant les dimensions temporelles existantes ou en créant de nouvelles dimensions temporelles avec des paramètres supplémentaires.

Vous trouverez ci-dessous un exemple de dimension temporelle modifiée.

Le **Format** Les valeurs Semaine, Heure, Jour, Mois et Heure du jour sont définies par défaut dans l’exemple.

>[!NOTE]
>
>Si ces lignes sont omises, le comportement du Data Workbench ne change pas et la dimension est compilée à l’aide des valeurs par défaut.

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. Configuration du fichier meta.cfg {#section-5e077d3298dd48fda7f7bb16af9ea00c}

De plus, il est nécessaire que l’administrateur de package ajoute ces paramètres et leurs valeurs par défaut dans la variable **[!DNL meta.cfg]** fichier . Cela permet de modifier à partir du poste de travail.

Voici un extrait d’un **[!DNL meta.cfg]** fichier .

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

Voici un exemple de **[!DNL meta.cfg]** dans le poste de travail :

![](assets/dwb_time_format.png)

L’administrateur peut alors accéder au **Gestionnaire de fichiers**, ouvrez le ou les fichiers dans lesquels les dimensions temporelles sont configurées (par exemple, **[!DNL Standard Time Dimensions.cfg]**) et modifiez-les à l’aide de dans le poste de travail.
