---
description: La première étape consiste à activer le rôle IIS sur votre serveur de tableau de bord.
solution: Analytics
title: Activation d'IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Activation d&#39;IIS{#enabling-iis}

La première étape consiste à activer le rôle IIS sur votre serveur de tableau de bord.

1. Sous **[!UICONTROL Administrative Tools]**, ouvrez le **[!UICONTROL Server Manager]**.
1. Cliquez avec le bouton droit de la souris sur l’option de menu Rôles dans la partie gauche de la **[!UICONTROL Server Manager]** fenêtre.
1. Select **[!UICONTROL Add Roles]**.
1. Sélectionnez **[!UICONTROL Web Server (IIS)]** et poursuivez avec le **[!UICONTROL Add Roles Wizard]**. Assurez-vous que les services de rôle suivants sont activés :

   | Fonctions HTTP courantes |
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
