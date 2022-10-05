---
description: Data Workbench prend désormais en charge l’éditeur de méthode d’entrée (IME) en tant que processus de saisie de texte secondaire pour les langues internationales.
title: Installation de l’éditeur de méthode d’entrée
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Installation de l’éditeur de méthode d’entrée{#installing-the-input-method-editor}

{{eol}}

Data Workbench prend désormais en charge l’éditeur de méthode d’entrée (IME) en tant que processus de saisie de texte secondaire pour les langues internationales.

Les IME vous permettent de saisir des caractères internationaux à l’aide de diverses méthodes adaptées à votre langue locale. Data Workbench fournit une boîte de dialogue de saisie qui vous permet d’ouvrir et d’utiliser l’IME souhaité pour les champs de texte.

>[!NOTE]
>
>Pour la version 6.1 des outils de données, seul le clavier chinois simplifié virtuel est pris en charge. La saisie d’autres langues via l’IME peut entraîner un comportement inattendu.

## Utilisation d’un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Pour utiliser la fonction d’entrée de texte IME flottante :

1. Cliquez sur **[!UICONTROL Alt + Space]** pour toute zone de saisie de texte.
1. Saisissez des valeurs à l’aide de l’IME de votre système.
1. Fermez la boîte de dialogue de saisie en sélectionnant **[!UICONTROL Enter]** ou en cliquant sur la touche **[!UICONTROL OK]** bouton .

   La boîte de dialogue disparaît et les caractères apparaissent ensuite dans le champ sélectionné.

**Mise à jour du fichier Insight.cfg**

Pour utiliser l’IME, vous devez mettre à jour la variable [!DNL Insight.cfg] avec ce paramètre :

```
Localized IME = bool: true
```

Si ce paramètre n’existe pas dans le fichier de configuration, appuyez sur **[!UICONTROL Alt + Space]** n’activera pas la fonction IME.

**Démarrage d’Insight dans une autre langue :** Pour mieux prendre en charge les ressources localisées telles qu’un écran de démarrage et pour prendre en charge plusieurs langues à l’avenir, Data Workbench nécessite des arguments de ligne de commande identifiant la langue à charger. La langue par défaut est l’anglais.

Pour démarrer Data Workbench en chinois, vous devez appeler [!DNL Insight.exe] avec l’argument &quot;-zh-cn&quot; :

```
Insight.exe -zh-cn
```

(Ces arguments de ligne de commande ne sont pas sensibles à la casse.)
