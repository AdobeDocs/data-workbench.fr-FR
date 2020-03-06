---
description: Pour configurer le portail de rapports, vous devez mapper ses fichiers d’application aux répertoires virtuels.
solution: Analytics
title: Association des pages du portail de rapports aux répertoires virtuels
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Association des pages du portail de rapports aux répertoires virtuels{#map-the-report-portal-pages-to-virtual-directories}

Pour configurer le portail de rapports, vous devez mapper ses fichiers d’application aux répertoires virtuels.

Un répertoire virtuel définit l’adresse utilisée par les clients du navigateur pour localiser une ressource physique sur le serveur d’applications IIS. Pour y accéder [!DNL Report Portal], les clients pointent leurs navigateurs vers le répertoire virtuel que vous affectez au portail.

Le nom du répertoire virtuel auquel vous affectez [!DNL Report Portal] doit correspondre au nom utilisé pour le dossier VSVirtualPortalName à l’étape 3 de la section précédente. Par exemple, si vous souhaitez utiliser &quot;Portal&quot; comme nom de votre [!DNL Report Portal]entreprise, vous devez mapper les fichiers du portail vers un répertoire virtuel nommé &quot;Portal&quot;. L’exemple suivant illustre l’URI que les clients utiliseraient pour accéder à un [!DNL Report Portal] affecté au répertoire virtuel [!DNL VisualReportPortal] sur un serveur appelé myWebServer :

[!DNL http://myWebServer/VisualReportPortal]

Les procédures suivantes décrivent comment mapper [!DNL Report Portal] à un répertoire virtuel sur IIS 5.0, 6.0 et 7.0 ou version ultérieure.

Suivez l’ensemble des procédures pour la version d’IIS que vous utilisez :

* [Mappage du portail de rapports à un répertoire virtuel (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Mappage du portail de rapports à un répertoire virtuel (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Modifier le fichier de configuration de session](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

