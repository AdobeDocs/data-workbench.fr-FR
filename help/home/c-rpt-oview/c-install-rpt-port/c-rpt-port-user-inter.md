---
description: Les jeux de rapports doivent être configurés d’une manière spécifique pour produire des rapports qui s’affichent correctement via le portail de rapports.
title: Personnaliser l’interface utilisateur du portail de rapports
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Personnaliser l’interface utilisateur du portail de rapports{#customize-the-report-portal-user-interface}

Les jeux de rapports doivent être configurés d’une manière spécifique pour produire des rapports qui s’affichent correctement via le portail de rapports.

L&#39;interface utilisateur de [!DNL Report Portal] est conçue pour afficher un onglet pour chaque dossier de jeu de rapports qui apparaît dans le répertoire de sortie et est répertorié dans le fichier [!DNL profiles.xml], ainsi que l&#39;onglet intégré [!DNL Admin], qui doit être ajouté au fichier [!DNL TopNavigation.xml] à afficher. Pour plus d&#39;informations sur l&#39;affichage de l&#39;onglet [!DNL Admin] intégré, voir [Liaison d&#39;un dossier Output à un onglet dans l&#39;utilisateur...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Liaison d’un dossier de sortie à un onglet dans l’utilisateur...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports {#section-2b141e5d198a4bbea455699126c24706}

Un jeu de rapports définit une tâche planifiée pour [!DNL Report]. Il se compose de deux éléments :

* Dossier qui définit la collection d&#39;espaces de travail que [!DNL Report] doit générer en tant que rapports.
* Un fichier de configuration ( [!DNL Report.cfg]).

Entre autres, le fichier [!DNL Report.cfg] indique à [!DNL Report] quand générer les rapports et où enregistrer les fichiers de sortie. Les jeux de rapports résident dans le dossier Rapports du serveur de l’outil de données. Un profil peut afficher n’importe quel nombre de jeux de rapports.

Pour garantir la compatibilité avec [!DNL Report Portal], vos jeux de rapports doivent répondre aux exigences suivantes :

* Le répertoire de sortie de vos jeux de rapports doit contenir un fichier [!DNL profiles.xml] configuré.
* Chaque jeu de rapports doit inclure un rapport de niveau supérieur nommé &quot;*ReportSetName* Summary&quot;, où *ReportSetName* correspond au nom du jeu de rapports. Par exemple, le [!DNL Profile Manager] suivant affiche deux jeux de rapports, &quot;Accueil&quot; et &quot;Trafic&quot;. Notez que chaque jeu de rapports définit un rapport récapitulatif ( [!DNL Home Summary.vw] et [!DNL Traffic Summary.vw], respectivement).

![](assets/rptPort_scrn_RptSets.png)

Dans [!DNL Report Portal], le rapport récapitulatif s&#39;affiche sur l&#39;onglet du jeu de rapports. Le rapport de synthèse peut contenir n’importe quel espace de travail, fenêtre ou visualisation choisi.

* Le rapport de synthèse doit être le seul rapport du dossier de niveau supérieur pour un jeu de rapports. Tous les autres rapports doivent être placés dans des sous-dossiers. Si vous placez d’autres rapports dans le dossier de niveau supérieur, vous ne pouvez pas les vue via le portail.

## Liaison d’un dossier Output à un onglet dans l’interface utilisateur {#section-3f6bc47d37ed448e871f4f685f46acee}

Pour spécifier les onglets à afficher sous [!DNL Report Portal], vous devez configurer un fichier [!DNL TopNavigation.xml] pour chaque profil. Ce fichier détermine quels jeux de rapports s’affichent sous forme d’onglets dans l’interface utilisateur pour un profil particulier, ainsi que l’ordre de ces onglets. Le fichier [!DNL TopNavigation.xml] réside dans le dossier \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Pour modifier le fichier TopNavigation.xml**

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le fichier [!DNL TopNavigation.xml] dans un éditeur de texte tel que le Bloc-notes.
1. Modifiez la liste des éléments `<TopNav>` afin qu&#39;elle définisse les noms et l&#39;ordre des jeux de rapports dont vous souhaitez afficher la sortie [!DNL Report Portal], comme dans l&#39;exemple suivant :

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >L&#39;onglet [!DNL Admin] est un onglet intégré qui fournit des fonctionnalités supplémentaires. Si vous ne l&#39;incluez pas dans le fichier [!DNL TopNavigation.xml], cet onglet ne s&#39;affiche pas et ses fonctionnalités ne sont pas disponibles.

1. Dans \*PortalName*\PortalFiles\Core\TopNav\ folder, créez un dossier pour votre profil suivant.
1. Copiez le fichier [!DNL TopNavigation.xml] du premier dossier de profil et collez-le dans le nouveau dossier.
1. Modifiez [!DNL TopNavigation.xml] si nécessaire, puis enregistrez le fichier.
1. Répétez les étapes 3 à 5 pour tous les autres profils disponibles dans votre portail.
