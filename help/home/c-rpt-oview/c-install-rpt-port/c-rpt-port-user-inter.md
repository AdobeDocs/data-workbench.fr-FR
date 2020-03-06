---
description: Les jeux de rapports doivent être configurés d’une manière spécifique pour produire des rapports qui s’affichent correctement via le portail des rapports.
solution: Analytics
title: Personnalisation de l’interface utilisateur du portail des rapports
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personnalisation de l’interface utilisateur du portail des rapports{#customize-the-report-portal-user-interface}

Les jeux de rapports doivent être configurés d’une manière spécifique pour produire des rapports qui s’affichent correctement via le portail des rapports.

L’interface utilisateur de [!DNL Report Portal] est conçue pour afficher un onglet pour chaque dossier de jeu de rapports qui apparaît dans le répertoire de sortie et est répertorié dans le [!DNL profiles.xml] fichier, ainsi que l’ [!DNL Admin] onglet intégré, qui doit être ajouté au [!DNL TopNavigation.xml] fichier à afficher. Pour plus d’informations sur l’affichage de l’ [!DNL Admin] onglet intégré, voir [Liaison d’un dossier de sortie à un onglet dans l’utilisateur...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Liaison d’un dossier Output à un onglet dans l’utilisateur...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports {#section-2b141e5d198a4bbea455699126c24706}

Un jeu de rapports définit une tâche planifiée pour [!DNL Report]. Il se compose de deux éléments :

* Dossier qui définit la collection d’espaces de travail que vous souhaitez générer [!DNL Report] en tant que rapports.
* Un fichier de configuration ( [!DNL Report.cfg]).

Entre autres choses, le [!DNL Report.cfg] fichier indique [!DNL Report] quand générer les rapports et où enregistrer les fichiers de sortie. Les jeux de rapports résident dans le dossier Rapports du serveur de l’outil de données. Un profil peut afficher n’importe quel nombre de jeux de rapports.

Pour garantir la compatibilité avec [!DNL Report Portal], vos jeux de rapports doivent répondre aux exigences suivantes :

* Le répertoire de sortie de vos jeux de rapports doit contenir un [!DNL profiles.xml] fichier configuré.
* Chaque jeu de rapports doit inclure un rapport de niveau supérieur nommé &quot;*ReportSetName* Summary&quot;, où *ReportSetName* correspond au nom du jeu de rapports. Par exemple, le rapport suivant [!DNL Profile Manager] montre deux jeux de rapports : &quot;Accueil&quot; et &quot;Trafic&quot;. Notez que chaque jeu de rapports définit un rapport récapitulatif ( [!DNL Home Summary.vw] et [!DNL Traffic Summary.vw], respectivement).

![](assets/rptPort_scrn_RptSets.png)

Dans [!DNL Report Portal]la, le rapport de synthèse s’affiche sur l’onglet du jeu de rapports. Le rapport de synthèse peut contenir n’importe quel espace de travail, fenêtre ou visualisation que vous choisissez.

* Le rapport de synthèse doit être le seul rapport du dossier de niveau supérieur pour un jeu de rapports. Tous les autres rapports doivent être placés dans des sous-dossiers. Si vous placez d’autres rapports dans le dossier de niveau supérieur, vous ne pouvez pas les afficher via le portail.

## Liaison d’un dossier Output à un onglet dans l’interface utilisateur {#section-3f6bc47d37ed448e871f4f685f46acee}

Pour spécifier les onglets [!DNL Report Portal] à afficher, vous devez configurer un [!DNL TopNavigation.xml] fichier pour chaque profil. Ce fichier détermine quels jeux de rapports apparaissent sous forme d’onglets dans l’interface utilisateur pour un profil particulier, ainsi que l’ordre de ces onglets. Le [!DNL TopNavigation.xml] fichier réside dans le dossier \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Pour modifier le fichier TopNavigation.xml**

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL TopNavigation.xml] fichier dans un éditeur de texte tel que le Bloc-notes.
1. Modifiez la liste des `<TopNav>` éléments afin qu’elle définisse les noms et l’ordre des jeux de rapports dont vous souhaitez [!DNL Report Portal] afficher la sortie, comme dans l’exemple suivant :

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
   >L’ [!DNL Admin] onglet est un onglet intégré qui fournit des fonctionnalités supplémentaires. Si vous ne l’incluez pas dans le [!DNL TopNavigation.xml] fichier, cet onglet ne s’affiche pas et ses fonctionnalités ne sont pas disponibles.

1. Dans \*PortalName*\PortalFiles\Core\TopNav\ folder, créez un dossier pour votre profil suivant.
1. Copiez le [!DNL TopNavigation.xml] fichier du premier dossier de profil et collez-le dans le nouveau dossier.
1. Modifiez le fichier [!DNL TopNavigation.xml] suivant vos besoins, puis enregistrez-le.
1. Répétez les étapes 3 à 5 pour tous les autres profils disponibles dans votre portail.

