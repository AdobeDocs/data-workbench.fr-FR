---
description: Les outils de données prennent désormais en charge l’éditeur de méthode d’entrée (IME) en tant que processus secondaire de saisie de texte pour les langues internationales.
solution: Analytics
title: Installation de l’éditeur de méthodes d’entrée
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installation de l’éditeur de méthodes d’entrée{#installing-the-input-method-editor}

Les outils de données prennent désormais en charge l’éditeur de méthode d’entrée (IME) en tant que processus secondaire de saisie de texte pour les langues internationales.

Les IME vous permettent de saisir des caractères internationaux à l’aide de différentes méthodes adaptées à votre langue locale. L’outil de données fournit une boîte de dialogue de saisie qui vous permet d’ouvrir et d’utiliser l’IME de votre choix pour les champs de texte.

>[!NOTE]
>
>Pour la version 6.1 des outils de données, seul le clavier virtuel en chinois simplifié sera pris en charge. L’entrée d’autres langues via l’IME peut entraîner un comportement inattendu.

## Utilisation d’un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Pour utiliser la fonction flottante de saisie de texte IME :

1. Cliquez sur **[!UICONTROL Alt + Space]** pour n’importe quelle zone de saisie de texte.
1. Entrez des valeurs à l’aide de l’IME de votre système.
1. Fermez la boîte de dialogue d’entrée en sélectionnant la **[!UICONTROL Enter]** touche ou en cliquant sur le **[!UICONTROL OK]** bouton.

   La boîte de dialogue disparaîtra et les caractères apparaîtront alors dans le champ sélectionné.

**Mise à jour du fichier Insight.cfg**

Pour utiliser l’IME, vous devez mettre à jour le [!DNL Insight.cfg] fichier avec ce paramètre :

```
Localized IME = bool: true
```

Si ce paramètre n’existe pas dans le fichier de configuration, appuyer sur **[!UICONTROL Alt + Space]** n’active pas la fonction IME.

**Démarrage d’Insight dans une autre langue :** Pour mieux prendre en charge les ressources localisées comme un écran de démarrage et pour prendre en charge plusieurs langues à l’avenir, les outils de données doivent disposer d’arguments de ligne de commande identifiant la langue à charger. La langue par défaut est l’anglais.

Pour démarrer les outils de données en chinois, vous devez appeler [!DNL Insight.exe] avec l’argument &quot;-zh-cn&quot; :

```
Insight.exe -zh-cn
```

(Ces arguments de ligne de commande ne sont pas sensibles à la casse.)
