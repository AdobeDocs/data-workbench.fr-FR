---
description: Identifiez les exigences et recommandations minimales relatives aux composants de serveur Data Workbench (anciennement [!DNL Insight]) avant de planifier et d’implémenter votre système.
title: Configuration requise du serveur
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Configuration requise du serveur{#server-system-requirements}

Identifiez les exigences et recommandations minimales relatives aux composants de serveur de Data Workbench avant de planifier et d’implémenter votre système.

## Exigences DPU{#dpu-requirements}

L’unité de traitement des données du serveur est le composant principal de traitement des données de Data Workbench. Il écoute les connexions réseau de Data Workbench, lit les données source brutes de l’unité de serveur de fichiers (FSU) et utilise d’importantes ressources de calcul et de stockage.

### Capacité sous licence {#section-71850e13783443798b3df9eb22cc63dc}

Pour plus d’informations sur la capacité de licence, reportez-vous à la Description des services dans le *Adobe [!DNL Data Workbench (Insight)] Contrat de service*.

>[!NOTE]
>
>Pour *MS System Center Endpoint Protection* dans les serveurs Windows 2012, ces exécutables doivent être ajoutés aux ***processus exclus:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### Configuration requise et Recommendations du système DPU {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe fournit des recommandations concernant une conception de Data Workbench qui répond aux besoins de votre entreprise. Toutefois, les instructions suivantes s’avèrent utiles lors de la sélection du système d’exploitation et du matériel, car la nature optimisée du logiciel DPU place des exigences spécifiques sur la plateforme du système d’exploitation/du matériel.

Si un seul jeu de données est limité par la capacité ou la vitesse d’un seul DPU, vous pouvez le grouper. Supposons, par exemple, que vous disposiez de trois copies sous licence du logiciel DPU utilisées conjointement pour exécuter plus rapidement un jeu de données plus volumineux. Comme les données sont divisées uniformément entre les machines, la capacité sous licence du jeu de données est multipliée par trois. En outre, la vitesse de traitement par ligne devient trois fois plus rapide qu’un seul DPU.

Pour optimiser les performances de votre investissement DPU, Adobe recommande les composants haute performance suivants décrits dans le tableau suivant :

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Obligatoire </th> 
   <th colname="col3" class="entry"> Recommandé </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Système d’exploitation </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>Voir Recommandations. </p> </td> 
   <td colname="col3"> Les processeurs 4 coeurs de dernière génération d’Intel ou AMD sont recommandés. Pour des performances optimales, 8 coeurs ; pour un compromis entre vitesse et coût, il est recommandé d’utiliser 4 coeurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 Go </p> </td> 
   <td colname="col3"> <p>12 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stockage des données de travail </p> </td> 
   <td colname="col2"> <p>1 To+ de stockage temporaire logique total. </p> <p>Accès à faible latence au sous-système de disque </p> </td> 
   <td colname="col3"> <p>Pour un Adobe de stockage temporaire, recommande l’une des options suivantes : </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 à 8) * (750 Go ou plus) disques durs SATA (fuseau de 3,5 pouces). </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 à 10) * (300 Go ou plus) disques durs SATA (fuseau de 2,5 pouces). </li> 
    </ul> <p>Ils doivent être configurés dans un tableau JBOD. Une autre solution consiste à utiliser une matrice de volumes RAID1 à 2 disques lorsque la capacité du disque brut dépasse 2 To. Par exemple, configurez six disques en tant que paire RAID 1 3*(2*750 Go). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stockage des données système </p> </td> 
   <td colname="col2"> <p>En outre, Adobe nécessite un stockage haute disponibilité d’une taille modeste (20 Go) pour le système d’exploitation, le logiciel DPU et d’autres logiciels système. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Matériel de mise en grappe </p> </td> 
   <td colname="col2"> <p>Voir Recommandations. </p> </td> 
   <td colname="col3"> <p>Utilisez un ensemble homogène de serveurs. Dans une grappe DPU, le serveur le plus lent réduit les performances de l’ensemble du jeu de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Performances du réseau en grappe </td> 
   <td colname="col2"> Une connexion Ethernet de gigabit changée ou supérieure. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Sous-systèmes de disque alternatifs {#section-6f984eabe8074759aa9deaf17e3a68b7}

Lorsque vous envisagez d’autres sous-systèmes de disque pour le stockage temporaire, tenez compte des facteurs et des directives suivants :

* Le DPU est exceptionnellement exigeant d’un système de disque haute performance, la configuration d’un sous-système de disque inadéquat peut donc entraîner des goulets d’étranglement au niveau des performances.
* Le logiciel DPU effectue sa propre répartition de données orientée performances sur un ensemble de disques JBOD. N’utilisez pas le RAID pour augmenter la vitesse.
* Adobe recommande que le DPU dispose d’une bande passante globale de plus de 400 Mo/s sur les disques.
* Les tailles moyennes de lecture sont très élevées (2 Mo+). Pour cette raison, les disques SAS 15 000 ou 10 000 tr/min fonctionnent souvent un peu mieux (ou pire) que les disques SATA, à un coût et une capacité significatifs.
* Évitez d’utiliser une architecture SAN. L&#39;expérience montre que le coût d&#39;obtention d&#39;un SAN aux niveaux requis est généralement extrême.
* Le sous-système de disque local est utilisé comme espace de travail : aucune donnée n’est définitivement perdue à cause d’une défaillance du disque dur. Pensez donc à éviter les systèmes coûteux, plus lents et à haute disponibilité.

### Observations relatives à la vitesse {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe ne peut pas fournir de garantie ou de représentation concernant la vitesse à laquelle les données sont traitées par un Data Workbench configuré, car divers facteurs affectent la vitesse de traitement des données, notamment, mais sans s’y limiter, les éléments suivants :

* Nombre de lignes de données
* Nombre de dimensions (colonnes) des données
* Nombre et complexité des étapes de traitement personnalisées
* Utilisation de la mise en cluster
* Vitesse du matériel

## Exigences d’unité de serveur de fichiers{#file-server-unit-requirements}

Le FSU (File Serving Unit) du serveur est le composant principal de gestion et de stockage des données de Data Workbench. Le FSU agit comme un serveur de fichiers pour les données sources brutes au DPU et, le cas échéant, coordonne la mise en grappe des DPU. Chaque FSU est autorisé à fournir des données sources jusqu’à cinq (5) DPU.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composants FSU </th> 
   <th colname="col2" class="entry"> Recommandations </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Système d’exploitation, processeur, RAM </p> </td> 
   <td colname="col2"> <p>Ces exigences sont identiques à celles du DPU. Toutefois, pour l’unité de gestion des stocks, Adobe recommande d’utiliser les exigences minimales plutôt que de suivre les recommandations. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Système de disque </p> <p>Le FSU nécessite un stockage redondant et hautement disponible pour de grands volumes de données. Adobe vous aidera à déterminer vos exigences exactes. </p> </td> 
   <td colname="col1"> <p>Adobe recommande : </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 ou plus) * (750 Go ou plus) HDD SATA dans une configuration RAID 5/6. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Connexion SAN haute performance prenant en charge une bande passante soutenue de 100 Mo/s ou plus. </li> 
    </ul> <p>Comme le FSU détient les données sources brutes, toute perte serait irrécupérable et Adobe suggère de sauvegarder ces données régulièrement. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Performances du réseau </p> </td> 
   <td colname="col2"> <p>Adobe nécessite des connexions Ethernet gigabit échangées entre les FSU et les DPU travaillant ensemble. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Exigences du capteur{#sensor-requirements}

Data Workbench Sensor collecte les données d’événement des serveurs web, d’applications et de collecte de données à transmettre à n’importe quel serveur. [!DNL Sensor’s] L’instrumentation garantit une mesure cohérente et précise des événements qui se produisent dans votre canal Internet. [!DNL Sensor] prend en charge de nombreuses combinaisons de logiciels de serveur Web et de système d’exploitation.

### Recommendations du système de détection {#section-0a981c3a47b644c1a1a56974ba033b9c}

Le tableau suivant décrit les recommandations système pour [!DNL Sensor] :

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalités </th> 
   <th colname="col2" class="entry"> Recommandé </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stockage de disque </p> </td> 
   <td colname="col2"> <p>512 Mo minimum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 Mo de RAM doivent être disponibles pour <span class="wintitle"> Capteur </span> sur l’ordinateur HTTP ou un autre serveur qui est son hôte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Performances du réseau </p> </td> 
   <td colname="col2"> <p>1 Mbit/s ou plus de connexion réseau à un serveur de répéteur ou <span class="keyword"> serveur Data Workbench </span>. <span class="wintitle"> Le capteur consomme  </span> généralement beaucoup moins de bande passante qu’une (1) Mbit/s. Vos consultants Adobe vous aideront à estimer la quantité réelle de bande passante requise de manière régulière. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ports réseau et pare-feu </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensor se  </span> connecte au serveur  <span class="keyword"> Data Workbench à l’ </span> aide du protocole HTTPS (généralement le port 443, bien que configurable) ou HTTP (généralement le port 80, bien que configurable). </p> <p>Le port approprié sur un pare-feu situé entre un <span class="wintitle"> Capteur </span> et le <span class="keyword"> serveur Data Workbench </span> cible doit être ouvert uniquement entre le <span class="wintitle"> Capteur </span> ordinateur hôte et le <span class="keyword"> serveur Data Workbench </span> ou serveur répéteur avant de commencer le <span class="wintitle"> Capteur </span> 9/&gt; processus d’installation. <span class="wintitle"> Sensor  </span> établit une connexion HTTP ou HTTPS unidirectionnelle à un serveur  <span class="keyword"> Data Workbench  </span> ou à un serveur de répéteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Systèmes de gestion réseau </p> </td> 
   <td colname="col2"> <p>Les systèmes de gestion de réseau existants doivent surveiller l’intégrité du matériel informatique sous-jacent (par exemple, l’espace disque, le service réseau) et la connectivité réseau, ainsi que le journal des événements Windows ou le journal système UNIX. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Synchronisation de l’heure du serveur </p> </td> 
   <td colname="col2"> <p>Assurez-vous que l’heure du système informatique est synchronisée en permanence sur chaque ordinateur qui héberge un <span class="wintitle"> Capteur </span>. Les applications de serveur Web et les ordinateurs surveillés par <span class="wintitle"> Capteur </span> doivent avoir des heures système synchronisées pour que les données d’événement collectées à partir d’eux soient exactes. Reportez-vous à la documentation de votre système d’exploitation pour connaître les étapes de synchronisation continue des heures système avec NTP ou d’autres installations de synchronisation du temps. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisation du nom DNS </p> </td> 
   <td colname="col2"> <p>Adobe recommande que <span class="wintitle"> Capteurs </span> utilisent un nom DNS (au lieu d’une adresse IP) pour résoudre l’adresse réseau d’un serveur Data Workbench </span> ou d’un serveur de répéteur. <span class="keyword"> Lorsqu’un <span class="wintitle"> Capteur </span> utilise un nom DNS, le fichier d’hôtes local ou DNS du serveur web hôte doit être configuré pour résoudre le nom du serveur Data Workbench </span> ou du serveur de répéteur.<span class="keyword"> </span></span></p> </td> 
  </tr> 
 </tbody> 
</table>

### Logiciels du serveur d’assistance {#section-d6071706539f49d9a861d87b98e6f382}

Le tableau suivant répertorie les combinaisons les plus courantes prises en charge par [!DNL Sensor] :

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logiciels du serveur web </th> 
   <th colname="col2" class="entry"> Système d’exploitation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serveur Apache / Serveur IBM HTTP 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 ou version ultérieure ; RedHat Enterprise Linux 6.x ou version ultérieure ; Sun Solaris 8.x ou version ultérieure ; IBM AIX 5.1x ou version ultérieure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x ou version ultérieure </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 ou version ultérieure </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs d’applications Java (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 ou version ultérieure ; RedHat Enterprise Linux 6.x ou version ultérieure ; Sun Solaris 8.x ou version ultérieure ; IBM AIX 5.1x ou version ultérieure. </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour connaître les autres combinaisons serveur/système d&#39;exploitation, veuillez consulter l&#39;Adobe de disponibilité. Toutes les fonctionnalités de [!DNL Sensor] ne sont pas disponibles avec toutes les combinaisons de serveur web/d’application et de système d’exploitation. Pour plus d’informations sur les versions [!DNL Sensor] spécifiques, veuillez contacter l’assistance Adobe.

## Configuration requise du serveur de rapports{#report-server-requirements}

Le serveur de rapports Data Workbench est le composant qui permet la sortie des rapports planifiés. Les rapports qui sont générés peuvent prendre la forme d’images .PNG ou de feuilles de calcul .XLS placées dans un système de fichiers ou sous la forme d’emails. Ses exigences matérielles sont identiques à celles du [client Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=fr).

Les exigences suivantes s’appliquent à [!DNL report server] :

* Accès au système de fichiers pour la sortie des données (partage réseau ou lecteur local).
* Accès au serveur SMTP configuré.
* Microsoft Excel 2003 ou version ultérieure installé sur le serveur [!DNL report]. Voir [Considérations pour l’automatisation côté serveur d’Office](http://support.microsoft.com/kb/257757) pour plus d’informations.

## Gestion des réseaux{#network-management}

Adobe recommande que les systèmes de gestion de réseau existants surveillent le matériel et le réseau sur lesquels repose la plateforme Data Workbench.

En outre, Adobe recommande de surveiller les journaux d’événements Windows des FSU et des DPU, qui sont écrits lorsqu’une erreur se produit.

>[!NOTE]
>
>Tout système de stockage en réseau hébergeant des fichiers journaux doit fournir au moins 10 Mo par unité de traitement des données (DPU) de bande passante continue.

## Disponibilité des données{#data-availability}

Il est normal et nécessaire qu’un DPU de serveur traite et retraite les données dans un jeu de données nouveau ou actualisé.

Cela peut être dû à des modifications de configuration, à des modifications de source de données, à des modifications matérielles, à une configuration inappropriée, à une défaillance matérielle, à une panne logicielle, à une panne d’alimentation, etc. Lorsque ce type de traitement ou de retraitement se produit, tous les jeux de données et toutes les données système doivent être immédiatement disponibles pour les composants DPU et FSU. Si vous ne respectez pas cette exigence, le système risque d’être mis hors service.

## Problèmes de réseau DPU et FSU{#dpu-and-fsu-network-issues}

Remarques à garder à l’esprit lorsque vous utilisez des réseaux DPU et FSU.

* Pour la distribution des fichiers journaux en réseau, tout système de stockage en réseau hébergeant des fichiers journaux doit fournir au moins 10 Mo par unité de traitement des données (DPU) de bande passante continue.
* Le DPU, le FSU et le Data Workbench communiquent de manière bidirectionnelle via HTTP ou HTTPS sur le port 80 ou 443 (par défaut ; les ports peuvent également être configurés).
* Data Workbench [!DNL Sensor(s)] doit pouvoir se connecter (à sens unique) aux serveurs.
* Pour permettre au DPU d&#39;envoyer des messages d&#39;alerte via SMTP, il doit pouvoir contacter le serveur SMTP configuré.
* Adobe recommande de donner aux FSU et aux DPU des noms de réseau tels que FSU01.CLIENT.COM afin d&#39;éviter toute reconfiguration en cas de changement d&#39;adresse IP.
