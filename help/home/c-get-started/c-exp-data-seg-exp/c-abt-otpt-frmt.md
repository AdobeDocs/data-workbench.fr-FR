---
description: Instructions relatives à la spécification du format de sortie.
title: Format de sortie
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Format de sortie{#output-format}

Instructions relatives à la spécification du format de sortie.

* Chaque nom de mesure ou de dimension doit être début et se terminer par un signe de pourcentage (%).

   * %XYZ% spécifie l&#39;élément de la dimension XYZ correspondant à l&#39;élément de Niveau. Une erreur est générée si la dimension XYZ n’est pas un-à-un ou un-à-plusieurs avec Niveau.
   * %=XYZ% spécifie la valeur de la formule de mesure ou de mesure XYZ pour l’élément donné de Niveau.

* Les noms de Dimension de deux mots ou plus ne nécessitent pas de traits de soulignement.
* Les noms de mesure qui contiennent deux mots ou plus nécessitent des traits de soulignement.

>[!NOTE]
>
>Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le champ [!DNL Output Format], un [!DNL Insert menu] apparaît. Ce menu contient une liste de caractères spéciaux (par exemple, Tabulation) qui sont souvent utilisés comme délimiteurs.

Si vous souhaitez exporter des données de durée de session pour votre segment, vous devez créer une nouvelle mesure basée sur la mesure Durée de la session. La nouvelle mesure, qui n&#39;est utilisée qu&#39;avec le champ [!DNL Output Format] de l&#39;exportation de segments, permet à Microsoft Excel d&#39;interpréter correctement les sessions qui durent moins d&#39;une heure. Pour créer une mesure de durée de session, ouvrez le fichier [!DNL Session Duration.metric] (à partir de [!DNL Profile Manager]) et insérez un signe dièse (#) dans la chaîne de date : [!DNL ftime = string: %#H:%M:%S]

Le signe dièse indique qu’un &quot;0&quot; de début est ajouté aux durées de session inférieures à 1 heure. Par conséquent, Excel interprète 0:53:21 comme 53 minutes et 21 secondes. Enregistrez la nouvelle mesure sous un autre nom et téléchargez-la dans le profil approprié pour que d’autres l’utilisent en cliquant avec le bouton droit sur la coche du fichier dans la colonne [!DNL User] et en cliquant sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.
