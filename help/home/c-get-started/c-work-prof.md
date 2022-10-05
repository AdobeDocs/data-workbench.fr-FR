---
description: Data Workbench télécharge les profils sur votre ordinateur.
title: Profils
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Profils{#profiles}

{{eol}}

Data Workbench télécharge les profils sur votre ordinateur.

Si vous chargez un profil pour la première fois, vous devez disposer d’une connexion réseau au [!DNL Data Workbench server] et travailler en ligne pour que le Data Workbench puisse télécharger les fichiers nécessaires à partir de la [!DNL Data Workbench server].

Le téléchargement du profil peut prendre plusieurs minutes. Vous ne devez pas commencer à utiliser le profil tant que le cache de données n’a pas commencé à se remplir, mais vous n’avez pas à attendre qu’il soit complet. Vous pouvez suivre la progression du cache de données, la progression de la synchronisation des profils, ainsi que la date et l’heure des données les plus récemment traitées, en regardant les barres d’état au chargement du profil.

>[!NOTE]
>
>Les données que vous ajoutez ne s’affichent pas dans les visualisations tant que le cache de données n’a pas commencé à être rempli.

La prochaine fois que vous chargez le profil, les mises à jour du profil et de ses données ne sont téléchargées que si vous êtes connecté au [!DNL Data Workbench server] et travaillent en ligne. Si vous travaillez hors ligne, le profil et ses données sont chargés à partir du cache de votre ordinateur. Dans ce cas, vous affichez la version du profil et des données téléchargées la dernière fois que vous avez travaillé en ligne avec le profil. Pour plus d’informations sur l’utilisation en ligne ou hors ligne, voir [Travail hors ligne](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Lorsque vous devez modifier votre profil (à l’aide de la variable [!DNL Profile Manager] ou le [!DNL Server Files Manager]), vous devez travailler en ligne pour vous assurer que vous disposez de la version la plus récente du profil. Pour plus d’informations sur la variable [!DNL Profile Manager] et le [!DNL Server Files Manager], voir [Interfaces administratives](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Si vous ne parvenez pas à accéder à un profil ou à le charger, vous devrez peut-être confirmer ce qui suit :

* Vous disposez d’une connexion réseau au [!DNL Data Workbench server] machine sur laquelle réside le profil.
* Vous disposez des autorisations appropriées pour accéder au profil.

Pour obtenir de l’aide, contactez votre administrateur système.

## Chargement ou changement de profil {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Lancez Data Workbench.
1. Dans la barre latérale, cliquez sur le nom du profil, puis sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>* où *nom du profil* est le profil avec lequel vous souhaitez travailler.

   ![](assets/sidebar_profile.png)

Si c’est la première fois que vous chargez le profil sélectionné, le téléchargement d’un nombre suffisant de données peut prendre plusieurs minutes pour remplir une visualisation.

## Accès à un profil sur une grappe {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Utilisateurs Data Workbench qui accèdent à un profil s’exécutant sur un

la grappe de serveurs Data Workbench identifie uniquement le serveur Data Workbench maître dans le fichier de configuration du Data Workbench ( [!DNL Insight.cfg]). Du point de vue de l’utilisateur Data Workbench, le profil est accessible sur un seul serveur Data Workbench (le serveur Data Workbench principal). Toutefois, les requêtes des analystes peuvent être dirigées vers n’importe quel serveur de Data Workbench de la grappe.

Pour plus d’informations sur les profils exécutés sur une grappe de serveurs Data Workbench, voir *Guide d’installation et d’administration des produits serveur*.
