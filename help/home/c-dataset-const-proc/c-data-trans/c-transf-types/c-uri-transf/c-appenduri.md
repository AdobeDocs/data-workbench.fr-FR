---
description: La transformation AppendURI permet d’ajouter des informations à la valeur par défaut provenant des entrées de journal utilisées pour créer le jeu de données.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

La transformation AppendURI permet d’ajouter des informations à la valeur par défaut provenant des entrées de journal utilisées pour créer le jeu de données.

La transformation place une paire nom-valeur à la fin du champ interne utilisé pour créer la dimension URI. La paire nom-valeur est créée à l’aide du paramètre clé de chaîne de Requête comme nom et la valeur du paramètre d’entrée identifié comme valeur de la paire. La commande [!DNL AppendURI] ajoute tout élément approprié ? et &amp; symboles nécessaires pour séparer les paires nom-valeur de la racine [!DNL URI] et de toute opération précédente [!DNL AppendURI] qui aurait pu être appliquée à l&#39;URI.

La transformation [!DNL AppendURI] ne fonctionne que lorsqu&#39;elle est définie dans le fichier [!DNL Transformation.cfg] ou dans un fichier [!DNL Transformation Dataset Include].

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Nom du champ dont la valeur est ajoutée à l’URI. |  |
| Clé de chaîne de requête | Nom à utiliser dans la création de la paire nom-valeur ajoutée. |  |

Prenons l&#39;exemple d&#39;un site Web qui a été construit selon une approche traditionnelle de contrôleur-Vue-modèle. Dans ces systèmes, il est courant de disposer d&#39;une seule page Web pour accéder au système. Pour un tel site, les visualisations des schémas de trafic dans le système seraient très inintéressantes et ne fourniraient aucune information sur l&#39;utilisation et le flux de trafic des visiteurs. Prenons l’exemple d’un site Web qui achemine toutes les requêtes Web via un URI du formulaire suivant :

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

La page ASP de vue de modèle reçoit tout le trafic et détermine ses actions en fonction de la valeur du champ id dans la requête. Par défaut, la dimension URI contient une seule entrée :

* [!DNL modelview.asp]

Cela résulterait en une correspondance plutôt inintéressante du trafic à travers le site, car tout le trafic est canalisé via un URI unique. Pour répondre à ce scénario particulier et fournir une vue plus détaillée sur l’architecture sous-jacente du site Web, [!DNL AppendURI] peut être utilisé pour déplacer certaines des paires nom-valeur uniques du champ cs-uri-requête vers la dimension URI utilisée pour les visualisations. La transformation présentée ci-dessous donne les détails d&#39;une telle transformation :

![](assets/cfg_TransformationType_AppendURI.png)

Dans cet exemple, le système utilise deux pages pour traiter toutes les requêtes : [!DNL modelview.asp] et [!DNL xmlmodelview.asp]. Une page est utilisée pour le trafic du navigateur et l’autre pour les communications XML système à système. Le processus du serveur d’applications utilise le nom d’ID de la requête cs-uri- pour déterminer l’action à entreprendre. Par conséquent, vous pouvez extraire la valeur du champ id et l’ajouter à l’URI. Le résultat est un ensemble d’URI avec une gamme de variations qui reflète le trafic visiteur sur le site Web. Ici, une condition [!DNL String Match] détermine les entrées de journal auxquelles la transformation est appliquée en recherchant dans le champ cs-uri-stem les deux pages Web présentant un intérêt et en ignorant toutes les autres. L’entrée (la valeur de notre paire nom-valeur) est le résultat de cs-uri-requête(id), qui est &quot;login&quot;. Comme spécifié par le paramètre Clé de chaîne de Requête, le nom ajouté est &quot;id&quot;. Ainsi, pour la valeur cs-uri entrante de notre exemple, l&#39;URI résultante utilisé par la dimension [!DNL URI] est [!DNL /modelview.asp&id=login].
