---
description: La transformation AppendURI permet d’ajouter des informations à la valeur par défaut qui provient des entrées de journal utilisées pour créer le jeu de données.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

{{eol}}

La transformation AppendURI permet d’ajouter des informations à la valeur par défaut qui provient des entrées de journal utilisées pour créer le jeu de données.

La transformation place une paire nom-valeur à la fin du champ interne utilisé pour créer la dimension URI. La paire nom-valeur est créée à l’aide du paramètre de clé de chaîne de requête comme nom et de la valeur du paramètre d’entrée identifié comme valeur de la paire. Le [!DNL AppendURI] ajoute une commande appropriée ? et les symboles &amp; nécessaires pour séparer les paires nom-valeur de [!DNL URI] origine et issue de n’importe quel précédent [!DNL AppendURI] opérations qui peuvent avoir été appliquées à l’URI.

Le [!DNL AppendURI] La transformation ne fonctionne que lorsqu’elle est définie dans la variable [!DNL Transformation.cfg] ou un [!DNL Transformation Dataset Include] fichier .

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrée | Nom du champ dont la valeur est ajoutée à l’URI. |  |
| Clé de chaîne de requête | Nom à utiliser dans la création de la paire nom-valeur ajoutée. |  |

Prenons l’exemple d’un site web qui a été créé selon une approche traditionnelle de Model-View-Controller. Dans ces systèmes, il est courant qu’une seule page Web soit le point d’accès au système. Pour un tel site, les visualisations des schémas de trafic dans le système seraient très inintéressantes et ne fourniraient aucune information sur l’utilisation des visiteurs et le flux de trafic. Prenons l’exemple d’un site web qui achemine toutes les demandes web via un URI du formulaire suivant :

* [!DNL https://www.examplesite.com/modelview.asp?id=login&name=bob]

La page ASP de la vue de modélisation reçoit tout le trafic et détermine ses actions en fonction de la valeur du champ id dans la requête. Par défaut, la dimension URI contient une seule entrée :

* [!DNL modelview.asp]

Cela entraînerait un mappage plutôt inintéressant du trafic à travers le site, car tout le trafic est canalisé via un seul URI. Pour répondre à ce scénario particulier et fournir une vue plus détaillée de l’architecture sous-jacente du site web, [!DNL AppendURI] peut être utilisé pour déplacer certaines des paires nom-valeur uniques du champ cs-uri-query vers la dimension URI utilisée pour les visualisations. La transformation illustrée ci-dessous donne les détails d&#39;une telle transformation :

![](assets/cfg_TransformationType_AppendURI.png)

Dans cet exemple, le système utilise deux pages pour gérer toutes les requêtes : [!DNL modelview.asp] et [!DNL xmlmodelview.asp]. Une page est utilisée pour le trafic du navigateur, l’autre pour les communications XML système à système. Le processus du serveur d’applications utilise le nom d’ID de la requête cs-uri-query pour déterminer l’action à entreprendre. Par conséquent, vous pouvez extraire la valeur du champ id et l’ajouter à l’URI. Il en résulte un ensemble d’URI avec une plage de variations qui reflète le trafic des visiteurs sur le site web. Ici, une [!DNL String Match] condition détermine les entrées de journal auxquelles la transformation est appliquée en recherchant le champ cs-uri-stem pour les deux pages web présentant un intérêt et en ignorant toutes les autres. L’entrée (la valeur de notre paire nom-valeur) est le résultat de cs-uri-query(id), qui est &quot;login&quot;. Comme spécifié par le paramètre de clé de chaîne de requête, le nom ajouté est &quot;id&quot;. Ainsi, pour la valeur cs-uri entrante de notre exemple, l’URI obtenu utilisé par la variable [!DNL URI] la dimension est [!DNL /modelview.asp&id=login].
