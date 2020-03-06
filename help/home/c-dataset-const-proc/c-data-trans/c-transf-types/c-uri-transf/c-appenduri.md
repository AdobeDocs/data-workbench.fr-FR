---
description: La transformation AppendURI permet d’ajouter des informations à la valeur par défaut provenant des entrées de journal utilisées pour créer le jeu de données.
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

La transformation AppendURI permet d’ajouter des informations à la valeur par défaut provenant des entrées de journal utilisées pour créer le jeu de données.

La transformation place une paire nom-valeur à la fin du champ interne utilisé pour créer la dimension URI. La paire nom-valeur est créée à l’aide du paramètre de clé de chaîne de requête comme nom et de la valeur du paramètre d’entrée identifié comme valeur de la paire. La [!DNL AppendURI] commande ajoute le code approprié ? et &amp; symboles nécessaires pour séparer les paires nom-valeur de la [!DNL URI] [!DNL AppendURI] racine et de toute opération précédente qui aurait pu être appliquée à l’URI.

La [!DNL AppendURI] transformation ne fonctionne que lorsqu’elle est définie dans le [!DNL Transformation.cfg] fichier ou dans un [!DNL Transformation Dataset Include] fichier.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Nom du champ dont la valeur est ajoutée à l’URI. |  |
| Clé de chaîne de requête | Nom à utiliser dans la création de la paire nom-valeur ajoutée. |  |

Prenons l&#39;exemple d&#39;un site Web qui a été construit selon une approche traditionnelle de contrôleur de vue modèle. Dans ces systèmes, il est courant de disposer d&#39;une page Web unique comme point d&#39;accès au système. Pour un tel site, les visualisations des schémas de trafic dans le système seraient très peu intéressantes et ne fourniraient aucune information sur l’utilisation des visiteurs et le flux de trafic. Prenons l’exemple d’un site Web qui achemine toutes les requêtes Web via un URI du formulaire suivant :

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

La page ASP de la vue de modèle reçoit tout le trafic et détermine ses actions en fonction de la valeur du champ d&#39;ID dans la requête. Par défaut, la dimension URI contient une seule entrée :

* [!DNL modelview.asp]

Cela résulterait en une correspondance plutôt inintéressante du trafic à travers le site, car tout le trafic est canalisé via un URI unique. Pour répondre à ce scénario particulier et fournir une vue plus détaillée de l’architecture sous-jacente du site Web, [!DNL AppendURI] vous pouvez déplacer certaines des paires nom-valeur uniques du champ cs-uri-query vers la dimension URI utilisée pour les visualisations. La transformation illustrée ci-dessous donne les détails d&#39;une telle transformation :

![](assets/cfg_TransformationType_AppendURI.png)

Dans cet exemple, le système utilise deux pages pour traiter toutes les requêtes : [!DNL modelview.asp] et [!DNL xmlmodelview.asp]. Une page est utilisée pour le trafic du navigateur et l’autre pour les communications XML système à système. Le processus du serveur d’applications utilise le nom d’ID de la requête cs-uri-query pour déterminer l’action à entreprendre. Par conséquent, vous pouvez extraire la valeur du champ id et l’ajouter à l’URI. Le résultat est une collection d’URI avec une gamme de variations qui reflète le trafic des visiteurs sur le site Web. Ici, une [!DNL String Match] condition détermine les entrées de journal auxquelles la transformation est appliquée en recherchant dans le champ cs-uri-tige les deux pages Web présentant un intérêt et en ignorant toutes les autres. L’entrée (la valeur de notre paire nom-valeur) est le résultat de cs-uri-query(id), qui est &quot;login&quot;. Comme spécifié par le paramètre de clé de chaîne de requête, le nom ajouté est &quot;id&quot;. Ainsi, pour la valeur cs-uri entrante de notre exemple, l’URI résultant utilisé par la [!DNL URI] dimension est [!DNL /modelview.asp&id=login].
