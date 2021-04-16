---
description: Vous pouvez personnaliser l’aspect des menus, y compris le menu de la fenêtre de l’espace de travail (accessible en cliquant avec le bouton droit de la souris dans n’importe quel espace de travail) et les menus répertoriant les mesures, les dimensions et les calques de mappage.
title: Personnaliser un menu
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Personnaliser un menu{#customize-a-menu}

Vous pouvez personnaliser l’aspect des menus, y compris le menu de la fenêtre de l’espace de travail (accessible en cliquant avec le bouton droit de la souris dans n’importe quel espace de travail) et les menus répertoriant les mesures, les dimensions et les calques de mappage.

La hiérarchie de tout menu reflète la structure de son répertoire dans le [!DNL Profile Manager]. Par exemple, le menu de la fenêtre de l&#39;espace de travail reflète la structure du répertoire de menus et le menu de mesures reflète la structure du répertoire de mesures. Pour tout menu, le répertoire correspondant peut contenir les éléments suivants :

* **Fichiers :** Ces fichiers représentent les visualisations, les légendes, les annotations, les interfaces administratives, les mesures, les dimensions ou les calques de mappage que vous pouvez ouvrir en cliquant sur l’option de menu correspondante.
* **Un  [!DNL order.txt] fichier :** ce fichier indique dans quel ordre le menu affiche ses éléments.
* **Sous-répertoires :** Chaque sous-répertoire représente un sous-menu. Chaque sous-répertoire peut contenir ses propres fichiers, sous-répertoires et fichier [!DNL order.txt].

Par exemple, le menu [!DNL Add Legend] contient les éléments de menu Mesure, Couleur, Valeur et Degré de confiance, dans cet ordre. En comparaison, le répertoire Menu\Ajouter la légende dans [!DNL Profile Manager] contient les fichiers [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw] et [!DNL Value.vw] par ordre alphabétique, ainsi qu&#39;un fichier [!DNL order.txt] pour contrôler l&#39;ordre des autres fichiers.
