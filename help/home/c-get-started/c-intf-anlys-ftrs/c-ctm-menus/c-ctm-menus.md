---
description: Vous pouvez personnaliser l’aspect des menus, y compris le menu de la fenêtre de l’espace de travail (accessible par un clic droit dans n’importe quel espace de travail) et les menus répertoriant les mesures, les dimensions et les calques de mappage.
title: Personnaliser un menu
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Personnaliser un menu{#customize-a-menu}

{{eol}}

Vous pouvez personnaliser l’aspect des menus, y compris le menu de la fenêtre de l’espace de travail (accessible par un clic droit dans n’importe quel espace de travail) et les menus répertoriant les mesures, les dimensions et les calques de mappage.

La hiérarchie de tout menu reflète la structure de son répertoire dans la variable [!DNL Profile Manager]. Par exemple, le menu de la fenêtre de l’espace de travail reflète la structure du répertoire des menus et le menu des mesures reflète la structure du répertoire des mesures. Pour tout menu, le répertoire correspondant peut contenir les éléments suivants :

* **Fichiers :** Ces fichiers représentent les visualisations, les légendes, les annotations, les interfaces administratives, les mesures, les dimensions ou les calques de mappage que vous pouvez ouvrir en cliquant sur l’option de menu correspondante.
* **Un [!DNL order.txt] fichier :** Ce fichier indique dans quel ordre le menu affiche ses éléments.
* **Sous-répertoires :** Chaque sous-répertoire représente un sous-menu. Chaque sous-répertoire peut contenir ses propres fichiers, sous-répertoires et [!DNL order.txt] fichier .

Par exemple, la variable [!DNL Add Legend] contient les éléments de menu Mesure, Couleur, Valeur et Degré de confiance, dans cet ordre. En comparaison, le répertoire Menu\Ajouter une légende dans la variable [!DNL Profile Manager] contient les fichiers ; [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw], et [!DNL Value.vw] dans l’ordre alphabétique, ainsi qu’un [!DNL order.txt] pour contrôler l’ordre des autres fichiers.
