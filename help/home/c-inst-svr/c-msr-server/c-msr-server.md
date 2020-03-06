---
description: Identifiez les exigences minimales et les recommandations relatives aux composants serveur Outils de données (anciennement [!DNL Insight]) avant de planifier et d’implémenter votre système.
title: Configuration requise pour le serveur
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration requise pour le serveur{#server-system-requirements}

Identifiez les exigences minimales et les recommandations relatives aux composants du serveur Outils de données avant de planifier et de mettre en oeuvre votre système.

## Configuration requise pour DPU{#dpu-requirements}

L’unité de traitement des données du serveur (DPU) est le principal composant de traitement des données des outils de données. Il écoute les connexions réseau à partir des outils de données, lit les données source brutes de l’unité de serveur de fichiers (FSU) et utilise des ressources de calcul et de stockage importantes.

### Capacité sous licence {#section-71850e13783443798b3df9eb22cc63dc}

Pour plus d’informations sur la capacité des licences, reportez-vous à la Description des services dans le contrat *de service[!DNL Data Workbench (Insight)]Adobe* Service Agreement.

>[!NOTE]
>
>Pour *MS System Center Endpoint Protection* sur les serveurs Windows 2012, ces exécutables doivent être ajoutés aux processus ***exclus :*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### Recommandations et configuration système DPU {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe fournit des recommandations concernant une conception des outils de données qui répond aux besoins de votre entreprise. Toutefois, les instructions suivantes sont utiles lors de la sélection du système d’exploitation (SE) et du matériel, car la nature optimisée du logiciel DPU place des exigences spécifiques sur la plate-forme du système d’exploitation/du matériel.

Si un jeu de données unique est limité par la capacité ou la vitesse d’un seul DPU, vous pouvez le regrouper. Supposons, par exemple, que vous disposiez de trois copies sous licence du logiciel DPU utilisées ensemble pour exécuter plus rapidement un jeu de données plus volumineux. Les données étant divisées uniformément entre les machines, la capacité du jeu de données sous licence est multipliée par trois. En outre, la vitesse de traitement par ligne devient trois fois plus rapide qu’un seul processeur de données.

Pour optimiser les performances de votre investissement DPU, Adobe recommande les composants hautes performances suivants décrits dans le tableau suivant :

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Obligatoire </th> 
   <th colname="col3" class="entry"> Recommandée </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Système d’exploitation </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x 64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UC </p> </td> 
   <td colname="col2"> <p>Voir Recommandations. </p> </td> 
   <td colname="col3"> Les processeurs 4 coeurs+ de dernière génération d'Intel ou d'AMD sont recommandés. Pour des performances optimales, 8 coeurs ; pour un compromis entre la vitesse et le coût, il est recommandé d'utiliser 4 coeurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 Go </p> </td> 
   <td colname="col3"> <p>12 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stockage des données de travail </p> </td> 
   <td colname="col2"> <p>Plus de 1 To de stockage temporaire logique total. </p> <p>Accès à faible latence au sous-système disque </p> </td> 
   <td colname="col3"> <p>Pour le stockage temporaire, Adobe recommande l’une des options suivantes : </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 à 8) * (750 Go ou plus) disques durs SATA (broche 3,5 pouces) </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 à 10) * (300 Go ou plus) disques durs SATA (broche de 2,5 pouces) </li> 
    </ul> <p>Elles doivent être configurées dans un tableau JBOD. Une autre solution consiste à utiliser une baie de volumes RAID1 à 2 disques lorsque la capacité brute du disque dépasse 2 To. Par exemple, configurez six disques en tant que paire 3*(2*750 Go RAID 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stockage des données système </p> </td> 
   <td colname="col2"> <p>En outre, Adobe nécessite un stockage à haute disponibilité de taille modeste (20 Go) pour le système d’exploitation, le logiciel DPU et d’autres logiciels système. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Matériel de mise en grappe </p> </td> 
   <td colname="col2"> <p>Voir Recommandations. </p> </td> 
   <td colname="col3"> <p>Utilisez un ensemble homogène de serveurs. Dans une grappe DPU, le serveur le plus lent réduit les performances de l’ensemble des jeux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Performances du réseau de mise en grappe </td> 
   <td colname="col2"> Une connexion Ethernet commutée-gigabit ou supérieure. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Sous-systèmes de disques alternatifs {#section-6f984eabe8074759aa9deaf17e3a68b7}

Lorsque vous envisagez d&#39;autres sous-systèmes de disque pour le stockage temporaire, tenez compte des facteurs et directives suivants :

* Le DPU est exceptionnellement exigeant pour un système de disque hautes performances, de sorte que la configuration d&#39;un sous-système de disque inadéquat peut provoquer des goulets d&#39;étranglement de performances.
* Le logiciel DPU effectue sa propre répartition des données orientée performances sur un ensemble de disques JBOD. N&#39;utilisez pas RAID pour augmenter la vitesse.
* Adobe recommande que le DPU dispose d’une bande passante soutenue de plus de 400 Mo/s sur les disques.
* Les tailles moyennes de lecture sont très élevées (2 Mo+). C&#39;est pourquoi les disques SAS 15 000 ou 10 000 tr/min fonctionnent souvent un peu mieux (ou pire) que les disques SATA à un coût et une capacité considérables.
* Evitez d&#39;utiliser une architecture SAN. L&#39;expérience montre que le coût de l&#39;exécution d&#39;un SAN aux niveaux requis est généralement extrême.
* Le sous-système de disque local est utilisé comme espace de travail : aucune donnée n’est définitivement perdue suite à une défaillance du disque dur ; évitez donc les systèmes coûteux, lents et à haute disponibilité.

### Considérations sur la vitesse {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe ne peut pas fournir de garantie ou de représentation concernant la vitesse à laquelle les données sont traitées par un outil de données configuré, car divers facteurs affectent la vitesse de traitement des données, notamment, mais sans s’y limiter, les éléments suivants :

* Nombre de lignes de données
* Nombre de dimensions (colonnes) des données
* Nombre et complexité des étapes de traitement personnalisées
* Utilisation de la mise en grappe
* Vitesse du matériel

## Configuration requise pour l’unité du serveur de fichiers{#file-server-unit-requirements}

L’unité de gestion des fichiers (FSU) du serveur est le principal composant de stockage et de gestion des données des outils de données. Le FSU agit comme un serveur de fichiers pour les données sources brutes au niveau du DPU et, le cas échéant, coordonne la mise en grappe des DPU. Chaque unité de traitement des données est autorisée à fournir des données source jusqu’à cinq (5) unités de traitement des données.

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
   <td colname="col1"> <p>Système d’exploitation, UC, RAM </p> </td> 
   <td colname="col2"> <p>Ces exigences sont les mêmes que celles du DPU. Toutefois, pour l’unité de gestion financière, Adobe recommande d’utiliser les conditions minimales requises plutôt que de suivre les recommandations. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Système de disque </p> <p>Le FSU nécessite un stockage redondant et hautement disponible pour de grands volumes de données. Adobe collaborera avec vous pour déterminer vos besoins exacts. </p> </td> 
   <td colname="col1"> <p>Adobe recommande : </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 ou plus) * (750 Go ou plus) disques durs SATA dans une configuration RAID 5/6. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Connexion SAN hautes performances prenant en charge une bande passante durable de 100 Mo/s+. </li> 
    </ul> <p>La FSU conservant les données brutes de la source, toute perte serait irrécupérable et Adobe suggère de sauvegarder ces données régulièrement. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Performances du réseau </p> </td> 
   <td colname="col2"> <p>Adobe requiert des connexions Ethernet commutées et gigabits entre les unités de sauvegarde (FSU) et les unités de production (DPU) qui fonctionnent ensemble. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Exigences du capteur{#sensor-requirements}

Data Workbench Sensor collecte les données d’événement des serveurs Web, d’applications et de collecte de données à transmettre à n’importe quel serveur. [!DNL Sensor’s] l’instrumentation permet de mesurer de manière cohérente et précise les événements qui se produisent sur votre canal Internet. [!DNL Sensor] prend en charge de nombreuses combinaisons de logiciels de serveur Web et de systèmes d&#39;exploitation.

### Recommandations système de capteurs {#section-0a981c3a47b644c1a1a56974ba033b9c}

Le tableau suivant décrit les recommandations système pour [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalités  </th> 
   <th colname="col2" class="entry"> Recommandée </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stockage sur disque </p> </td> 
   <td colname="col2"> <p>512 Mo minimum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 Mo de RAM doivent être disponibles pour <span class="wintitle"> Sensor </span> sur le serveur HTTP ou un autre ordinateur serveur qui est son hôte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Performances du réseau </p> </td> 
   <td colname="col2"> <p>1 Mbit/s ou plus de connexion réseau à un serveur de répéteur ou à un serveur <span class="keyword"> de outils de données </span>. <span class="wintitle"> Le capteur consomme </span> généralement beaucoup moins de bande passante qu’un (1) Mbit/s. Vos consultants Adobe vous aideront à estimer la quantité réelle de bande passante requise sur une base régulière. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ports réseau et pare-feu </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> se connecte au serveur de l’outil de <span class="keyword"> données à l’ </span> aide du protocole HTTPS (généralement le port 443, bien que configurable) ou HTTP (généralement le port 80, bien que configurable). </p> <p>Le port approprié sur tout pare-feu qui réside entre un <span class="wintitle"> Sensor </span> et le serveur de traitement de données cible <span class="keyword"> ou serveur de répéteur doit être ouvert uniquement entre l’ordinateur hôte de </span> Sensor et le serveur de traitement de données ou le serveur de répéteur de l’outil de <span class="wintitle"> </span> <span class="keyword"> données cible avant de commencer le processus d’installation de  Sensor . </span><span class="wintitle"></span> <span class="wintitle"> Sensor </span> effectue une connexion HTTPS ou HTTP unidirectionnelle à un serveur <span class="keyword"> de données ou à un serveur de répéteur </span> de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Systèmes de gestion de réseau </p> </td> 
   <td colname="col2"> <p>Les systèmes de gestion réseau existants doivent surveiller l'état du matériel informatique sous-jacent (par exemple, l'espace disque, le service réseau) et la connectivité réseau, ainsi que le journal des événements Windows ou le journal système UNIX. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Synchronisation du temps du serveur </p> </td> 
   <td colname="col2"> <p>Assurez-vous que l’heure du système informatique est synchronisée en permanence sur chaque ordinateur hébergeant un <span class="wintitle"> capteur </span>. Les applications de serveur Web et les ordinateurs surveillés par <span class="wintitle"> Sensor </span> doivent avoir synchronisé les heures système pour que les données d’événement collectées auprès d’eux soient exactes. Consultez la documentation de votre système d'exploitation pour connaître les étapes à suivre pour synchroniser les heures système de façon continue avec NTP ou d'autres installations de synchronisation de ce type. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisation du nom DNS </p> </td> 
   <td colname="col2"> <p>Adobe recommande aux <span class="wintitle"> capteurs </span> d’utiliser un nom DNS (au lieu d’une adresse IP) pour résoudre l’adresse réseau d’un serveur <span class="keyword"> de outils de données </span> ou d’un serveur de répéteur. Lorsqu’un <span class="wintitle"> capteur </span> utilise un nom DNS, le fichier DNS du serveur Web hôte ou le fichier d’hôtes locaux doit être configuré pour résoudre le nom du serveur <span class="keyword"> de outils de données ou du serveur de répéteurs </span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

### Logiciels du serveur de support {#section-d6071706539f49d9a861d87b98e6f382}

Le tableau suivant répertorie les combinaisons les plus courantes qui [!DNL Sensor] prennent en charge :

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logiciel Web Server </th> 
   <th colname="col2" class="entry"> Système d’exploitation </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td> 
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

Pour d’autres combinaisons serveur/système d’exploitation, veuillez consulter Adobe pour connaître la disponibilité. Toutes les fonctionnalités de ne [!DNL Sensor] sont pas disponibles avec toutes les combinaisons de serveur Web/d’application et de système d’exploitation. Pour plus d’informations sur certaines [!DNL Sensor] versions, contactez l’assistance technique d’Adobe.

## Configuration requise pour le serveur de rapports{#report-server-requirements}

Le serveur de rapports des outils de données est le composant qui permet la sortie des rapports planifiés. Les rapports qui sont générés peuvent prendre la forme d’images .PNG ou de feuilles de calcul .XLS placées dans un système de fichiers ou sous forme de courriers électroniques. La configuration matérielle requise est identique à celle du client [Outils de](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)données.

Les conditions suivantes sont requises pour [!DNL report server]:

* Accès au système de fichiers pour la sortie des données (partage réseau ou lecteur local).
* Accès au serveur SMTP configuré.
* Microsoft Excel 2003 ou version ultérieure installé sur [!DNL report] le serveur. Pour plus d’informations, voir [Considérations relatives à l’automatisation côté serveur d’Office](http://support.microsoft.com/kb/257757) .

## Gestion du réseau{#network-management}

Adobe recommande aux systèmes de gestion de réseau existants de surveiller le matériel et le réseau sur lesquels repose la plate-forme Outils de données.

En outre, Adobe recommande de surveiller les journaux des événements Windows des FSU et des DPU, qui sont écrits lorsqu’une erreur se produit.

>[!NOTE]
>
>Tout système de stockage en réseau hébergeant des fichiers journaux doit fournir au moins 10 Mo de bande passante durable par unité de traitement des données.

## Disponibilité des données{#data-availability}

Il est normal et nécessaire qu’un DPU serveur traite et retraite les données dans un jeu de données nouveau ou actualisé.

Cela peut être dû à des modifications de configuration, à des modifications de source de données, à des modifications matérielles, à une configuration inappropriée, à une défaillance matérielle, à une panne logicielle, à une panne d&#39;alimentation, etc. Lors de ce traitement ou de ce retraitement, toutes les données du jeu de données et du système doivent être immédiatement disponibles pour les composants DPU et FSU. Le non-respect de cette exigence peut entraîner un temps d&#39;arrêt important et inutile du système.

## Problèmes réseau DPU et FSU{#dpu-and-fsu-network-issues}

Points à prendre en compte lorsque vous travaillez avec des réseaux DPU et FSU.

* Pour la distribution de fichiers journaux en réseau, tout système de stockage en réseau hébergeant des fichiers journaux doit fournir au moins 10 Mo par unité de traitement de données (DPU) de bande passante durable.
* Le DPU, le FSU et les outils de données communiquent bidirectionnellement via HTTP ou HTTPS sur le port 80 ou 443 (par défaut) ; les ports peuvent être configurés).
* Les outils de données [!DNL Sensor(s)] doivent pouvoir se connecter (de manière unidirectionnelle) aux serveurs.
* Pour permettre au DPU d’envoyer des messages d’alerte via SMTP, il doit être en mesure de contacter le serveur SMTP configuré.
* Adobe recommande de donner aux FSU et aux DPU des noms de réseau tels que FSU01.CLIENT.COM afin d’éviter toute reconfiguration en cas de modification de l’adresse IP.