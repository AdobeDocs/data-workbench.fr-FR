---
description: Instructions relatives à la spécification du format de sortie.
solution: Analytics
title: Format de sortie
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Format de sortie{#output-format}

Instructions relatives à la spécification du format de sortie.

* Chaque nom de mesure ou de dimension doit commencer et se terminer par un signe de pourcentage (%).

   * %XYZ% spécifie l&#39;élément de dimension XYZ correspondant à l&#39;élément de Niveau. Une erreur est générée si la dimension XYZ n’est pas un à un ou un à plusieurs avec Niveau.
   * %=XYZ % indique la valeur de la formule de mesure ou XYZ pour l’élément donné de Niveau.

* Les noms de dimension de deux mots ou plus ne nécessitent pas de traits de soulignement.
* Les noms de mesure qui sont composés de deux mots ou plus nécessitent des traits de soulignement.

>[!NOTE]
>
>Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le [!DNL Output Format] champ, un [!DNL Insert menu] apparaît. Ce menu contient une liste de caractères spéciaux (par exemple, Tabulation) qui sont souvent utilisés comme délimiteurs.

Si vous souhaitez exporter des données de durée de session pour votre segment, vous devez créer une nouvelle mesure basée sur la mesure Durée de la session. La nouvelle mesure, qui est utilisée uniquement avec le [!DNL Output Format] champ d’exportation de segments, permet à Microsoft Excel d’interpréter correctement les sessions qui durent moins d’une heure. Pour créer une mesure de durée de session, ouvrez le [!DNL Session Duration.metric] fichier (à partir du [!DNL Profile Manager]) et insérez un signe dièse (#) dans la chaîne de la période : [!DNL ftime = string: %#H:%M:%S]

Le signe dièse indique qu’un &quot;0&quot; de début est ajouté aux durées de session de moins d’une heure. Par conséquent, Excel interprète 0:53:21 comme 53 minutes et 21 secondes. Enregistrez la nouvelle mesure sous un autre nom et téléchargez-la dans le profil approprié pour que d’autres l’utilisent en cliquant avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
