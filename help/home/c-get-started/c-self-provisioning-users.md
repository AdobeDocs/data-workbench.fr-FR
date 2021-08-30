---
description: Utilisez Workstation pour gérer les utilisateurs de vos Data Workbench.
title: Approvisionnement automatique des utilisateurs
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Approvisionnement automatique des utilisateurs{#self-provisioning-of-users}

Utilisez Workstation pour gérer les utilisateurs de vos Data Workbench.

Vous pouvez utiliser Workstation pour vous connecter au serveur Data Workbench en configurant le certificat requis à partir d’Adobe. Ce certificat facilite la communication et l’autorisation SSL pour utiliser les ressources et fonctionnalités sous licence. Dans l’authentification par certificat, vous devez acquérir et configurer plusieurs certificats pour utiliser Workstation sur plusieurs machines. En outre, la configuration et les droits des utilisateurs sont gérés par Adobe et vous devez contacter Adobe pour obtenir de nouveaux certificats ou la révocation des certificats.

À compter de DWB 6.7, Workstation prend en charge l’authentification des utilisateurs par nom d’utilisateur et mot de passe.

Bien que l’authentification/autorisation basée sur un certificat fonctionne toujours pour votre configuration, il est vivement recommandé de migrer vers la nouvelle authentification basée sur les informations d’identification. Avec la nouvelle approche, les utilisateurs de votre station de travail s’authentifient eux-mêmes via Adobe Identity Management System (IMS). Avant de pouvoir utiliser la station de travail, l&#39;administrateur de l&#39;organisation doit leur donner accès aux fonctionnalités par l&#39;intermédiaire du [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

Le nouveau modèle d’authentification et de configuration utilisateur permet ce qui suit :

* Approvisionnement automatique des utilisateurs et des groupes par le biais de Admin Console. Vous n’avez pas à contacter Adobe pour ajouter, supprimer ou modifier des droits de licence pour les utilisateurs.
* Accès à Workstation à partir de plusieurs machines sans perdre l’état de configuration en vous connectant à l’aide des informations d’identification. Le cache local est supprimé lors de la déconnexion, le profil actuel est fermé et le profil de configuration devient principal.

## Prise en main

Avant de commencer, contactez l’Adobe pour ajouter votre organisation dans le Admin Console. Selon les services que vous avez achetés, Adobe vous confiera l’organisation. Par exemple, les entreprises peuvent avoir accès aux versions bêta ou du service d’attribution, ou aux deux. Une fois qu’une organisation est configurée, l’administrateur de l’organisation peut ajouter des utilisateurs et des groupes. Voir [Gestion des utilisateurs et des produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) dans Experience Cloud pour plus d’informations. L’administrateur de l’organisation peut également configurer des restrictions d’utilisation pour différents utilisateurs en fonction de leur rôle. Par exemple, les utilisateurs qui ne disposent pas d’une version préliminaire n’ont pas besoin d’accéder aux versions bêta.

Chaque utilisateur ayant reçu les privilèges d’accès ajoutés à cette organisation par le biais du Admin Console aura accès à l’utilisation du Data Workbench. Les sous-services ne peuvent être activés ou désactivés que pour chaque utilisateur, en fonction de son accès aux produits. Lorsqu’un utilisateur est mis à niveau du certificat vers IMS, toutes les données locales sont copiées dans le nouveau répertoire utilisateur IMS.

>[!NOTE]
>
>Une session dure 6 heures sur le serveur et 23 heures sur le client, sauf si le jeton d’accès est actualisé. Lorsque le jeton est actualisé, vous pouvez utiliser Client sans vous reconnecter.

Au moins une configuration de niveau produit doit être créée en Admin Console par l’administrateur avant de donner accès à n’importe quel utilisateur.

L’indicateur booléen **Utiliser IMS** peut être ajouté à [!DNL Insight.cfg] pour basculer en mode certificat. Pour plus d’informations sur la configuration du contrôle d’accès pour les utilisateurs IMS, voir [Mise à jour du fichier de contrôle d’accès](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Résolution des conflits

Lorsqu’un utilisateur est connecté à plusieurs machines avec le même compte IMS sur le même profil et qu’il est en mode hors ligne sur l’une des machines, un `.conflict` peut se former et une fenêtre contextuelle vous en informe. Cela se produit lorsqu’il existe une différence de contenu avec des fichiers (espaces de travail, dimensions, filtres, etc.) synchronisé sur les deux machines dans [!DNL User\Profile\] sur le serveur et le client . Une sauvegarde sera créée dans le fichier `.conflict` et aucune donnée ne sera perdue. Un indicateur booléen dans [!DNL Insight.cfg] vous permet de désactiver cette fenêtre contextuelle de conflit.

Indicateur : Notifications de conflit

Cela s’applique aux espaces de travail, aux mesures, aux dimensions, etc. dans le dossier User.
