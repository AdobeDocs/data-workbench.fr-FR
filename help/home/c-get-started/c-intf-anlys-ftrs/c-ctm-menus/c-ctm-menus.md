---
description: Vous pouvez personnaliser l’aspect des menus, y compris le menu de la fenêtre de l’espace de travail (accessible en cliquant avec le bouton droit de la souris dans n’importe quel espace de travail) et les menus répertoriant les mesures, les dimensions et les calques de mappage.
solution: Analytics
title: Personnalisation d’un menu
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personnalisation d’un menu{#customize-a-menu}

Vous pouvez personnaliser l’aspect des menus, y compris le menu de la fenêtre de l’espace de travail (accessible en cliquant avec le bouton droit de la souris dans n’importe quel espace de travail) et les menus répertoriant les mesures, les dimensions et les calques de mappage.

La hiérarchie de tout menu reflète la structure de son répertoire dans le [!DNL Profile Manager]. Par exemple, le menu de la fenêtre de l’espace de travail reflète la structure du répertoire des menus et le menu des mesures reflète la structure du répertoire des mesures. Pour tout menu, le répertoire correspondant peut contenir les éléments suivants :

* **Fichiers :** Ces fichiers représentent les visualisations, les légendes, les annotations, les interfaces administratives, les mesures, les dimensions ou les calques de mappage que vous pouvez ouvrir en cliquant sur l’option de menu correspondante.
* **Un[!DNL order.txt]fichier :** Ce fichier indique dans quel ordre le menu affiche ses éléments.
* **Sous-répertoires :** Chaque sous-répertoire représente un sous-menu. Chaque sous-répertoire peut contenir ses propres fichiers, sous-répertoires et [!DNL order.txt] fichiers.

Par exemple, le [!DNL Add Legend] menu contient les options de menu Mesure, Couleur, Valeur et Degré de confiance, dans cet ordre. En comparaison, le répertoire Menu\Ajouter une légende dans le [!DNL Profile Manager] contient les fichiers [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]et [!DNL Value.vw] par ordre alphabétique, ainsi qu’un [!DNL order.txt] fichier pour contrôler l’ordre des autres fichiers.
