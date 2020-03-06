---
description: Utilisez Workstation pour gérer vos utilisateurs des outils de données.
title: Auto-approvisionnement des utilisateurs
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Auto-approvisionnement des utilisateurs{#self-provisioning-of-users}

Utilisez Workstation pour gérer vos utilisateurs des outils de données.

Vous pouvez utiliser Workstation pour vous connecter au serveur Data Workbench en configurant le certificat requis auprès d’Adobe. Ce certificat facilite la communication SSL et l’autorisation d’utiliser les ressources et fonctionnalités sous licence. Dans l’authentification par certificat, vous devez acquérir et configurer plusieurs certificats pour utiliser Workstation sur plusieurs ordinateurs. En outre, l’approvisionnement des utilisateurs et les droits sont gérés par Adobe et vous devez contacter Adobe pour obtenir de nouveaux certificats ou la révocation de certificats.

Depuis DWB 6.7, Workstation prend en charge l’authentification des utilisateurs par nom d’utilisateur et mot de passe.

Bien que l’authentification/autorisation basée sur certificat fonctionne toujours pour votre configuration, il est vivement recommandé de migrer vers la nouvelle authentification basée sur les informations d’identification. Dans la nouvelle approche, les utilisateurs de votre station de travail s’authentifient via le système Adobe Identity Management System (IMS). Avant de pouvoir utiliser le poste de travail, l&#39;administrateur de l&#39;organisation doit leur donner accès aux fonctionnalités par le biais de la Console [d&#39;administration](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) .

Le nouveau modèle d’authentification et de mise en service des utilisateurs permet d’effectuer les opérations suivantes :

* Mise en service automatique des utilisateurs et des groupes via la console d’administration. Vous n’avez pas besoin de contacter Adobe pour ajouter, supprimer ou modifier des droits de licence pour les utilisateurs.
* Accès à Workstation à partir de plusieurs ordinateurs sans perdre l’état de configuration en vous connectant à l’aide des informations d’identification. Le cache local est supprimé lors de la déconnexion, le profil actuel est fermé et le profil de configuration devient actif.

## Prise en main

Avant de commencer, contactez Adobe pour ajouter votre organisation dans la console d’administration. En fonction des services que vous avez achetés, Adobe fournit des services à l’entreprise. Par exemple, les entreprises peuvent avoir accès au service d’attribution ou aux versions bêta, ou aux deux. Une fois qu’une organisation est configurée, l’administrateur peut ajouter des utilisateurs et des groupes. Pour plus d’informations, voir [Gestion des utilisateurs et des produits](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud dans Experience Cloud. L’administrateur de l’organisation peut également configurer des restrictions d’utilisation pour différents utilisateurs en fonction de leurs rôles. Par exemple, les utilisateurs qui ne sont pas des utilisateurs de version préliminaire n’ont pas besoin d’accéder aux versions bêta.

Chaque utilisateur configuré ajouté à cette organisation par le biais de la Console d’administration aura accès à l’outil de données. Les sous-services ne peuvent être activés ou désactivés que pour chaque utilisateur, en fonction de l’accès aux produits. Lorsqu’un utilisateur est mis à niveau du certificat vers IMS, toutes les données locales sont copiées dans le nouveau répertoire utilisateur IMS.

>[!NOTE]
>
>Une session dure 6 heures sur le serveur et 23 heures sur le client, sauf si le jeton d’accès est actualisé. Lorsque le jeton est actualisé, vous pouvez utiliser Client sans vous reconnecter.

L’administrateur doit créer au moins une configuration au niveau du produit dans la console d’administration avant de donner accès à un utilisateur.

L’indicateur booléen **Utiliser IMS** peut être ajouté à [!DNL Insight.cfg] la reprise en mode de certificat. Pour plus d’informations sur la configuration du contrôle d’accès pour les utilisateurs IMS, voir [Mise à jour du fichier](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)de contrôle d’accès.

## Résolution des conflits

Lorsqu’un utilisateur est connecté à plusieurs ordinateurs avec le même compte IMS sur le même profil et qu’il est en mode hors ligne sur l’un des ordinateurs, un formulaire `.conflict` peut s’afficher et une fenêtre contextuelle vous en informe. Cela se produit lorsqu’il existe une différence de contenu avec les fichiers (espaces de travail, dimensions, filtres, etc.) synchronisé sur les deux machines dans [!DNL User\Profile\] sur le serveur et le client. Une sauvegarde sera créée dans le `.conflict` fichier et aucune donnée ne sera perdue. Un indicateur booléen dans [!DNL Insight.cfg] permet de désactiver cette fenêtre contextuelle de conflit.

Indicateur : Notifications de conflit

Cela s’applique aux espaces de travail, aux mesures, aux dimensions, etc. dans le dossier utilisateur.
