---
description: Le paramètre Fuseau horaire du fichier Transformation.cfg contrôle les dimensions temporelles, les conversions temporelles (par exemple, la définition du champ x-local-timestring) et la mise en forme de toutes les heures locales dans le profil du jeu de données.
solution: Analytics
title: Fuseaux horaires
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Fuseaux horaires{#time-zones}

Le paramètre Fuseau horaire du fichier Transformation.cfg contrôle les dimensions temporelles, les conversions temporelles (par exemple, la définition du champ x-local-timestring) et la mise en forme de toutes les heures locales dans le profil du jeu de données.

>[!NOTE]
>
>Le paramètre Fuseau horaire n’affecte pas les fonctionnalités au niveau du système, telles que les horodatages dans les journaux d’état et d’événements, qui sont exprimés en heure locale du système.

Le paramètre Fuseau horaire prend en charge un format de fuseau horaire indépendant du système (&quot;Heure universelle coordonnée&quot;) au format suivant :

Fuseau horaire = chaîne : UTC +hhmm dstrules

Le signe (+) peut être un signe plus (+) ou un signe moins (-), et *hhmm* est le décalage par rapport à UTC en heures et minutes. La variable facultative *décrit* un ensemble de règles pour mettre en oeuvre l’heure d’été ou une stratégie similaire de changement d’horloge.

Si vous spécifiez *des règles*, un fichier délimité par des tabulations nommé [!DNL dstrules .dst] doit figurer dans le sous-répertoire DataSet\TimeZone du profil du jeu de données. Le fichier spécifie un jeu de règles indépendant du fuseau horaire pour l’heure d’été. Vous pouvez avoir différents ensembles de règles pour différentes années. Le [!DNL DST.dst] fichier fourni par Adobe dans le profil de base spécifie les règles américaines standard établies par la loi de 2005 sur la politique énergétique (en vigueur depuis 2007) et les règles américaines pour les années précédentes.

Les exemples d’entrées de fuseau horaire sont répertoriés ci-dessous :

* Heure avancée de l&#39;Est des États-Unis : Fuseau horaire = chaîne : UTC -0500 DST
* Heure UTC sans décalage et sans distorsion : Fuseau horaire = chaîne : UTC -0000

Lorsque ce format est utilisé, le fuseau horaire système du serveur de l’outil de données, de l’outil de données et des [!DNL Report] ordinateurs ne doit pas nécessairement être identique au fuseau horaire spécifié. En outre, tous les profils de jeux de données actifs sur un ordinateur serveur de l’outil de données ne doivent pas avoir le même paramètre de fuseau horaire.

Adobe ne conseille pas d’exécuter plusieurs profils de jeux de données sur un seul ordinateur serveur de l’outil de données ou une grappe de serveurs de l’outil de données.

Les utilisateurs des outils de données verront les données dans le fuseau horaire du profil du jeu de données au lieu de leur fuseau horaire système. Adobe recommande que le fuseau horaire système d’un serveur de outils de données soit identique à celui utilisé dans ses jeux de données.

>[!NOTE]
>
>Vous pouvez spécifier un paramètre de fuseau horaire dans le [!DNL Log Processing.cfg] fichier, où il est utilisé pour les conversions de temps pendant le traitement du journal. Pour plus d’informations sur le paramètre Fuseau horaire dans le [!DNL Log Processing.cfg] fichier, voir Fichier [de configuration de traitement des](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)journaux.

