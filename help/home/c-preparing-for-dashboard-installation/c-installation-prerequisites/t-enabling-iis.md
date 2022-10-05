---
description: La première étape consiste à activer le rôle IIS sur votre serveur de tableau de bord.
title: Activation d’IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Activation d’IIS{#enabling-iis}

{{eol}}

La première étape consiste à activer le rôle IIS sur votre serveur de tableau de bord.

1. Sous **[!UICONTROL Administrative Tools]**, ouvrez le **[!UICONTROL Server Manager]**.
1. Cliquez avec le bouton droit de la souris sur l’option de menu Rôles dans la partie gauche du **[!UICONTROL Server Manager]** fenêtre.
1. Sélectionnez **[!UICONTROL Add Roles]**.
1. Sélectionner **[!UICONTROL Web Server (IIS)]** et continuez avec la fonction **[!UICONTROL Add Roles Wizard]**. Assurez-vous que les services de rôle suivants sont activés :

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
   | Filtres ISAPI |

   | Santé et diagnostics |
   |---|
   | Journalisation HTTP |
   | Outils de journalisation |
   | moniteur de requêtes |
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

1. Suivez l’assistant pour terminer l’installation.
