---
description: La première étape consiste à activer le rôle IIS sur votre serveur de tableau de bord.
title: Activation d’IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Activation d’IIS{#enabling-iis}

La première étape consiste à activer le rôle IIS sur votre serveur de tableau de bord.

1. Sous **[!UICONTROL Administrative Tools]**, ouvrez **[!UICONTROL Server Manager]**.
1. Cliquez avec le bouton droit de la souris sur l&#39;option de menu Rôles dans la partie gauche de la fenêtre **[!UICONTROL Server Manager]**.
1. Sélectionnez **[!UICONTROL Add Roles]**.
1. Sélectionnez **[!UICONTROL Web Server (IIS)]** et continuez avec **[!UICONTROL Add Roles Wizard]**. Assurez-vous que les services de rôle suivants sont activés :

   | Fonctionnalités HTTP courantes |
   |---|
   | Contenu statique |
   | Document par défaut |
   | Navigation dans les répertoires |
   | Erreurs HTTP |
   | Redirection HTTP |

   | Développement d’applications |
   |---|
   | ASP.NET |
   | Extensibilité .NET |
   | Extensions ISAPI |
   | FILTRES ISAPI |

   | Santé et diagnostics |
   |---|
   | Journalisation HTTP |
   | Outils de journalisation |
   | Moniteur de requête |
   | Tracé |
   | Journalisation personnalisée |

   | Sécurité |
   |---|
   | Authentification de base |
   | Authentification Windows |
   | Authentification URL |
   | Filtrage des requêtes |
   | Restrictions d’IP et de domaine |

   | Outils de gestion |
   |---|
   | Console de gestion IIS |
   | Script et outils de gestion IIS |
   | Service de gestion |

1. Suivez l&#39;Assistant pour terminer l&#39;installation.
