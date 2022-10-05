---
description: Instructions pour spécifier le format de sortie.
title: Format de sortie
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Format de sortie{#output-format}

{{eol}}

Instructions pour spécifier le format de sortie.

* Chaque nom de mesure ou de dimension doit commencer et se terminer par un signe de pourcentage (%).

   * %XYZ% spécifie l’élément de la dimension XYZ correspondant à l’élément du niveau. Une erreur est générée si la dimension XYZ n’est pas un-à-un ou un-à-plusieurs avec le niveau.
   * %=XYZ % spécifie la valeur de la formule de mesure ou de mesure XYZ pour l’élément donné du niveau.

* Les noms de Dimension de deux mots ou plus ne nécessitent pas de traits de soulignement.
* Les noms de mesure qui comportent deux mots ou plus nécessitent des traits de soulignement.

>[!NOTE]
>
>Si vous maintenez la touche Ctrl enfoncée, cliquez avec le bouton droit de la souris dans le [!DNL Output Format] , un [!DNL Insert menu] apparaît. Ce menu contient une liste de caractères spéciaux (par exemple, tabulation) qui sont souvent utilisés comme délimiteurs.

Si vous souhaitez exporter les données de durée de session pour votre segment, vous devez créer une mesure basée sur la mesure Durée de session . La nouvelle mesure, qui ne doit être utilisée qu’avec la variable [!DNL Output Format] d’exportation de segments, permet à Microsoft Excel d’interpréter correctement les sessions d’une durée inférieure à une heure. Pour créer une mesure de durée de session, ouvrez le [!DNL Session Duration.metric] (depuis le fichier [!DNL Profile Manager]) et insérez un signe dièse (#) dans la chaîne de saisie : [!DNL ftime = string: %#H:%M:%S]

Le signe dièse signifie qu’un &quot;0&quot; de début est ajouté aux durées de session de moins d’une heure. Par conséquent, Excel interprète 0:53:21 comme 53 minutes et 21 secondes. Enregistrez la nouvelle mesure sous un autre nom et téléchargez-la dans le profil approprié afin que d’autres utilisateurs puissent l’utiliser en cliquant avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL User] colonne et clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
