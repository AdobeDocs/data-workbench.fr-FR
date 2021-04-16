---
description: Les outils de données prennent désormais en charge l’éditeur de méthode d’entrée (IME) en tant que processus secondaire de saisie de texte pour les langues internationales.
title: Installation de l’éditeur de méthode d’entrée
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56,0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec,e4e1c016-0544-434a-b82e-fdd2a4af316c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Installation de l’éditeur de méthode d’entrée{#installing-the-input-method-editor}

Les outils de données prennent désormais en charge l’éditeur de méthode d’entrée (IME) en tant que processus secondaire de saisie de texte pour les langues internationales.

Les IME vous permettent de saisir des caractères internationaux en utilisant diverses méthodes adaptées à votre langue locale. L’outil de données fournit une boîte de dialogue de saisie qui vous permet d’ouvrir et d’utiliser l’IME de votre choix pour les champs de texte.

>[!NOTE]
>
>Pour la version 6.1 des outils de données, seul le clavier chinois simplifié virtuel sera pris en charge. La saisie d&#39;autres langues via l&#39;IME peut entraîner un comportement inattendu.

## Utilisation d’un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Pour utiliser la fonction flottante de saisie de texte IME :

1. Cliquez sur **[!UICONTROL Alt + Space]** pour n’importe quelle zone de saisie de texte.
1. Saisissez des valeurs à l’aide de l’IME de votre système.
1. Fermez la boîte de dialogue d&#39;entrée en sélectionnant la touche **[!UICONTROL Enter]** ou en cliquant sur le bouton **[!UICONTROL OK]**.

   La boîte de dialogue disparaîtra et les caractères apparaîtront dans le champ sélectionné.

**Mise à jour du fichier Insight.cfg**

Pour utiliser l&#39;IME, vous devez mettre à jour le fichier [!DNL Insight.cfg] avec ce paramètre :

```
Localized IME = bool: true
```

Si ce paramètre n&#39;existe pas dans le fichier de configuration, appuyez sur **[!UICONTROL Alt + Space]** pour désactiver la fonction IME.

**Démarrage d’Insight dans une autre langue :** pour mieux prendre en charge les ressources localisées comme un écran de démarrage et pour prendre en charge plusieurs langues à l’avenir, les outils de données doivent disposer d’arguments de ligne de commande identifiant la langue à charger. La langue par défaut est l’anglais.

Le démarrage des outils de données en chinois nécessite d’appeler [!DNL Insight.exe] avec l’argument &quot;-zh-cn&quot; :

```
Insight.exe -zh-cn
```

(Ces arguments de ligne de commande ne sont pas sensibles à la casse.)
