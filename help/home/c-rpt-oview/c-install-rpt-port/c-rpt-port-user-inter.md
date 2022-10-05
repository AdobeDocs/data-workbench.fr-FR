---
description: Les jeux de rapports doivent être configurés d’une manière spécifique afin de produire des rapports qui s’affichent correctement via le portail de rapports.
title: Personnaliser l’interface utilisateur du portail de rapports
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Personnaliser l’interface utilisateur du portail de rapports{#customize-the-report-portal-user-interface}

{{eol}}

Les jeux de rapports doivent être configurés d’une manière spécifique afin de produire des rapports qui s’affichent correctement via le portail de rapports.

L’interface utilisateur de [!DNL Report Portal] est conçu pour afficher un onglet pour chaque dossier de jeux de rapports qui apparaît dans le répertoire de sortie et est répertorié dans la variable [!DNL profiles.xml] , ainsi que le fichier intégré [!DNL Admin] , qui doit être ajouté à la variable [!DNL TopNavigation.xml] à afficher. Pour plus d’informations sur l’affichage de la version intégrée [!DNL Admin] , voir [Liaison d’un dossier de sortie à un onglet dans l’utilisateur...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Liaison d’un dossier de sortie à un onglet dans l’utilisateur...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Vérification de la compatibilité de vos jeux de rapports avec le portail de rapports {#section-2b141e5d198a4bbea455699126c24706}

Un jeu de rapports définit une tâche planifiée pour [!DNL Report]. Il se compose de deux éléments :

* Un dossier qui définit la collection des espaces de travail que vous souhaitez [!DNL Report] pour générer en tant que rapports.
* Un fichier de configuration ( [!DNL Report.cfg]).

Entre autres, la variable [!DNL Report.cfg] fichier:xter [!DNL Report] date de génération des rapports et emplacement d’enregistrement des fichiers de sortie. Les jeux de rapports résident dans le dossier Rapports sur le serveur Data Workbench. Un profil peut afficher n’importe quel nombre de jeux de rapports.

Pour garantir la compatibilité avec [!DNL Report Portal], vos jeux de rapports doivent répondre aux exigences suivantes :

* Le répertoire de sortie de vos jeux de rapports doit contenir un [!DNL profiles.xml] fichier .
* Chaque jeu de rapports doit inclure un rapport de niveau supérieur nommé &quot;&quot;*ReportSetName* &quot;Summary&quot;, où *ReportSetName* correspond au nom du jeu de rapports. Par exemple, les éléments suivants [!DNL Profile Manager] affiche deux jeux de rapports, &quot;Accueil&quot; et &quot;Trafic&quot;. Notez que chaque jeu de rapports définit un rapport récapitulatif ( [!DNL Home Summary.vw] et [!DNL Traffic Summary.vw], respectivement).

![](assets/rptPort_scrn_RptSets.png)

Dans [!DNL Report Portal], le rapport de synthèse s’affiche dans l’onglet du jeu de rapports. Le rapport de synthèse peut contenir n’importe quel espace de travail, fenêtre ou visualisation de votre choix.

* Le rapport de synthèse doit être le seul rapport du dossier de niveau supérieur pour un jeu de rapports. Tous les autres rapports doivent être placés dans des sous-dossiers. Si vous placez d’autres rapports dans le dossier de niveau supérieur, vous ne pouvez pas les afficher via le portail.

## Liaison d’un dossier de sortie à un onglet dans l’interface utilisateur {#section-3f6bc47d37ed448e871f4f685f46acee}

Pour spécifier les onglets de votre choix [!DNL Report Portal] pour s’afficher, vous devez configurer une [!DNL TopNavigation.xml] pour chaque profil. Ce fichier détermine les jeux de rapports qui s’affichent sous forme d’onglets dans l’interface utilisateur pour un profil particulier, ainsi que l’ordre de ces onglets. Le [!DNL TopNavigation.xml] se trouve dans le dossier \*PortalName*\PortalFiles\Core\TopNav\*profileName* .

**Pour modifier le fichier TopNavigation.xml**

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL TopNavigation.xml] dans un éditeur de texte tel que le Bloc-notes.
1. Modifier la liste de `<TopNav>` pour définir les noms et l’ordre des jeux de rapports dont vous souhaitez obtenir la sortie. [!DNL Report Portal] pour afficher, comme dans l’exemple suivant :

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
   >Le [!DNL Admin] est un onglet intégré qui fournit des fonctionnalités supplémentaires. Si vous ne l’incluez pas dans la variable [!DNL TopNavigation.xml] , cet onglet ne s’affiche pas et ses fonctionnalités ne sont pas disponibles.

1. Dans \*NomPortail*\PortalFiles\Core\TopNav\ folder, créez un dossier pour votre profil suivant.
1. Copiez le [!DNL TopNavigation.xml] à partir du premier dossier de profil et collez-le dans le nouveau dossier.
1. Modifiez la variable [!DNL TopNavigation.xml] si nécessaire, enregistrez le fichier.
1. Répétez les étapes 3 à 5 pour tous les autres profils disponibles sur votre portail.
