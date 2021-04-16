---
description: Informations sur les paramètres requis de Sensor txlogd.conf.
title: Paramètres obligatoires
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Paramètres obligatoires{#required-parameters}

Informations sur les paramètres requis de Sensor txlogd.conf.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dans ce paramètre... </th> 
   <th colname="col2" class="entry"> Spécifiez les... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Chaîne de caractères qui identifie de manière unique ce <span class="wintitle"> capteur</span>. </p> <p> <span class="wintitle"> </span> Sensorattache l’identifiant SensorID à chaque enregistrement de événement qu’il envoie au serveur <span class="keyword">  de l’outil de </span>données. Le SensorID permet de distinguer les données de événement provenant de ce serveur Web des données de événement capturées par d'autres capteurs <span class="wintitle"> </span>. </p> <p>Bien qu’un SensorID puisse être constitué de n’importe quelle chaîne de caractères, par convention, le nom du serveur Web dont le événement <span class="wintitle"> Sensor</span> est capturé est utilisé. L’utilisation du nom de serveur comme SensorID permet de déterminer facilement la source d’un événement au cours de l’analyse. Il garantit également que l’identifiant SensorID est unique dans l’implémentation. </p> <p>Exemple : <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Adresse du serveur de l'outil de données <span class="keyword"> </span> auquel <span class="wintitle"> Sensor</span> envoie des données de événement. </p> <p>Remarque :  <p>Lorsque vous travaillez dans un environnement organisé en grappes, <span class="wintitle"> Sensor</span> doit être configuré pour accéder au serveur maître <span class="keyword"> des outils de données</span> afin d’éviter des problèmes de synchronisation. Dans le Data Workbench, vous pouvez vue des informations sur le traitement des <span class="keyword"> serveurs de l'outil de données</span> dans votre grappe à l'aide de l'option de menu Serveurs associés dans le <span class="wintitle"> Gestionnaire de serveurs</span>. Pour plus d'informations sur le <span class="wintitle"> Gestionnaire de serveurs</span>, consultez le <i> Data Workbench<span class="keyword"></span><span class="wintitle"> Guide du capteur</span></i>. </p> <p>Si votre serveur Web peut résoudre les noms de serveur par le biais du DNS, vous pouvez spécifier l’adresse du serveur par nom. Dans le cas contraire, vous devez indiquer l’adresse IP numérique du serveur. </p> <p>Exemple : <span class="filepath"> ServerAddress 10.1.0.7</span> ou </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Si <span class="wintitle"> Sensor</span> communique avec <span class="keyword"> le serveur de l'outil de données </span> en utilisant HTTP ou HTTPS. Définissez sur "on" pour HTTPS ou "off" pour HTTP. </p> <p>Exemple : <span class="filepath"> SSL sur </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>port sur lequel le serveur de l'outil de données <span class="keyword"> </span> écoute les données de événement. </p> <p>Exemple : <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Obligatoire uniquement si le paramètre SSL est défini sur "on". </p> <p>Nom commun du serveur d'outils de données <span class="keyword"> </span> auquel <span class="wintitle"> Sensor</span> envoie des données de événement. </p> <p>La valeur que vous spécifiez doit correspondre exactement au nom commun qui apparaît sur le certificat de licence <span class="keyword"> du serveur de l’outil de données</span>. </p> <p>Exemple : <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Obligatoire uniquement si le paramètre SSL est défini sur "on". </p> <p>Répertoire dans lequel se trouve le fichier d’autorité de certification (<span class="filepath"> trust_ca_cert.pem</span>). </p> <p>Exemples : </p> <p> <span class="filepath"> CertPath /usr/local/visualcapteur</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Non requis pour les installations de <span class="wintitle"> capteur</span> sur les ordinateurs Microsoft Windows 2000 ou 2003 Server exécutant Internet Service d'information (IIS) versions 5.x ou 6.x. </p> <p>Nom complet du fichier de file d'attente de disque. </p> <p>Bien que vous puissiez attribuer n’importe quel nom à ce fichier, par convention, le fichier de file d’attente est nommé <span class="filepath"> VisualSensor.dat</span>. </p> <p>Pour les installations <span class="wintitle"> Sensor</span> sur Unix, vous pouvez placer ce fichier n'importe où. Sous Windows exécutant un serveur Web Java, vous devez placer ce fichier dans le même répertoire que l’émetteur. Pour tous les autres serveurs Web, ce fichier doit résider dans le répertoire /var/queue. </p> <p>Exemple : <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Remarque :  Assurez-vous que le périphérique auquel vous affectez ce fichier dispose de suffisamment d’espace libre pour accueillir une file d’attente de la taille dont vous avez besoin. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Entier représentant la taille du fichier de file d'attente de disque en Mo. </p> <p>Pour les installations <span class="wintitle"> Sensor</span> sous Microsoft Windows, le fichier de file d’attente lui-même est créé dans le même répertoire que l’émetteur et est nommé <span class="filepath"> Diskq2000.log</span>. </p> <p>L’exemple suivant définit la taille de la file d’attente sur 200 Mo : </p> <p>QueueSize 200 </p> <p>L’exemple suivant définit la taille de la file d’attente sur 2 Go : </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
