---
description: Guide rapide des différentes méthodes de transfert de fichiers dans DWB.
title: Gouvernance du transfert de fichiers
uuid: a3e19f8a-1cc4-437c-9661-408f675109c0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gouvernance du transfert de fichiers{#file-transfer-governance}

Guide rapide des différentes méthodes de transfert de fichiers dans DWB.

La gouvernance du transfert de fichiers est un processus standard permettant de transférer des fichiers d’un répertoire interne vers tout autre serveur ou mouvement interne de fichiers.

## Différentes méthodes de transfert de fichiers {#section-972bb39ba1954c6ebd35f6d042593efe}

1. AWS (Amazon Web Services)

   1. Levez un ticket pour installer l’interface de ligne de commande AWS sur le serveur si ce n’est pas déjà fait (voir [http://docs.aws.amazon.com/cli/latest/userguide/installing.html](http://docs.aws.amazon.com/cli/latest/userguide/installing.html)).
   1. Comment vérifier ? Essayez de configurer AWS à l’aide de l’invite de commande (voir [http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)).

1. Transférez les fichiers du serveur FTP vers le répertoire NAS.

   1. Flux FTP hors ligne du serveur ftp vers le répertoire NAS. Les détails ci-dessous sont requis pour le protocole FTP.

      ftp_username

      ftp_password

      ftp_port

      ftp_address

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      (Les détails FTP seront disponibles dans la liste de contrôle du projet. Utiliser un utilisateur ftp externe pour transférer les fichiers)

   1. Utilisez le script ftp_winscp_get.pl joint ci-dessous et planifiez selon les besoins.

      ftp_winscp_get.pl

      Ce script doit être placé à l’adresse E:\scripts\Scripository\Library\Perl

      >[!NOTE]
      >
      >Si le dossier Scripository n’est pas disponible, reportez-vous à la section [Processus](../../../home/dwb-implement-overview/dwb-implement-configure/dwb-implement-reprocess-scripting.md#concept-60529e12d6d94386a02c1c6fdedf0295) hebdomadaire de téléchargement du dossier.

   1. Planifiez le script en fonction de la disponibilité des fichiers à ftp_address.
   1. La convention de dénomination du fichier doit être AAAAMMJJ-&lt;nom_flux_hors ligne>-00.*

1. Transférez les fichiers du répertoire NAS vers le serveur FTP.

   1. Utilisez le script et la planification ftp_winscp_put.pl en fonction des besoins.

      Ce script doit être placé à l’adresse E:\scripts\Scripository\Library\Perl

      Les détails ci-dessous sont requis pour exécuter le script.

      ftp_username

      ftp_password

      ftp_port

      ftp_address

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      ```
      ####################################################################################################################### 
      # PLUGIN NAME HERE 
      my $pluginname = "FTP WinSCP"; 
      # 20140421 Script tp put files on the FTP 
      ####################################################################################################################### 
      # INCLUDE SCRIPOSITORY CORE 
      use FindBin;                 # locate this script 
      BEGIN {push @INC, $FindBin::Bin} 
      require 'core.pl'; 
      
         # check for the required parameters 
       GetOptions('local_directory:s'     => \$local_directory, 
                     'source_file_pattern:s' => \$source_file_pattern, 
                     'ftp_file_extension:s' => \$ftp_file_extension, 
                     'ftp_address=s'  => \$ftp_address, 
                     'ftp_username=s'  => \$ftp_username, 
                     'ftp_password:s'  => \$ftp_password, 
                     'ftp_port:s'   => \$ftp_port, 
                     'ftp_directory:s'     => \$ftp_directory, 
           'log_directory:s'  => \$log_directory, 
                     'error_directory:s'  => \$error_directory, 
                     'mail_from:s'  => \$mail_from, 
                     'mail_to:s'   => \$mail_to, 
                     'host:s'   => \$host, 
                     'trigger_directory:s' => \$trigger_directory, 
                     'trigger_file_extension:s' => \$trigger_file_extension, 
                     'delete_ftp_files:s'  => \$delete_ftp_files,); 
      
       # FOR LEFT OVER PARAMS, WE CAN CHECK GLOBAL PARAMS 
       check_parameters(@argv); 
      
       my $ftp_winscp_script = "winscpscript.txt"; 
       if (index($trigger_file_extension, '.') != -1) { 
        my @trigger_file_extension1=split(/\./,$trigger_file_extension,2); 
        $trigger_file_extension =  $trigger_file_extension1[1]; 
       } 
       if (index($ftp_file_extension, '.') != -1) { 
        my @ftp_file_extension1=split(/\./,$ftp_file_extension,2); 
        $ftp_file_extension =  $ftp_file_extension1[1]; 
       } 
       if ($trigger_file_extension ne "_empty_" && $trigger_directory ne "_empty_") { 
         print $trigger_file_extension; 
        my $ftp_winscp_trigger_script = "winscpscript_trigger.txt"; 
        create_winscp_script($ftp_winscp_trigger_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$trigger_directory,$ftp_directory,$delete_ftp_files,"*",$trigger_file_extension); 
        sleep(10); 
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_trigger_script /log=$logfile"); 
        $files = getFiles($trigger_directory,$trigger_file_extension,$days_ago,$months_ago); 
        my $ftp_file_pattern=""; 
        my $numberoffiles = @$files; 
        my $i=0; 
        foreach my $trigger_file(@$files) { 
         $i++; 
         my $file_string=substr($trigger_file,length($trigger_directory), length($trigger_file)-length($trigger_directory)); 
         my @file_string1=split(/\./, $file_string, 2); 
         if ($i == $numberoffiles) { 
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension; 
         } 
         else { 
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension.", "; 
         }
      
        } 
      
        #unlink($ftp_winscp_trigger_script); 
        print $local_directory; 
        print $trigger_directory; 
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$ftp_file_pattern, ""); 
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available"); 
        sleep(10); 
        runLogger("$pluginname: FTP started"); 
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile"); 
        runLogger("$pluginname: FTP ended"); 
      
       } 
       else { 
        if ($source_file_pattern eq "_empty_") { 
         $source_file_pattern="*"; 
        } 
        else { 
         if (index($source_file_pattern, '.') != -1) { 
          my @source_file=split(/\./,$source_file_pattern,2); 
          $source_file_pattern =  $source_file[0]; 
         } 
        } 
        $ftp_file_extension=".".$ftp_file_extension; 
      print $local_directory; 
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$source_file_pattern,$ftp_file_extension); 
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available"); 
        sleep(10); 
        runLogger("$pluginname: FTP started"); 
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile"); 
        runLogger("$pluginname: FTP ended"); 
       } 
       unlink($ftp_winscp_script);
      
      sub create_winscp_script() { 
       my ($ftp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$file_pattern, $file_extension) = @_; 
       open (FTP, "> $ftp_script") or die "Can't open log: $!"; 
       print FTP "\# Automatically answer all prompts negatively not to stall\n"; 
       print FTP "option batch on\n\n"; 
       print FTP "\# Disable overwrite confirmations that conflict with the previous\n"; 
       print FTP "option confirm off\n\n"; 
       print FTP "\# Connect using a password\n"; 
       if ($ftp_port eq "22") { 
        print FTP "open sftp://$ftp_username:$ftp_password\@$ftp_address\n\n"; 
       } 
       else { 
        print FTP "open ftp://$ftp_username:$ftp_password\@$ftp_address\n\n"; 
       } 
       print FTP "\# Change local directory\n"; 
       print FTP "lcd \"$local_directory\"\n\n"; 
       print FTP "\# Change remote directory\n"; 
       if ($ftp_directory eq "_empty_") { 
       } 
       else { 
        print FTP "cd \"$ftp_directory\"\n\n"; 
       } 
       print FTP "\# Force binary mode transfer\n"; 
       print FTP "option transfer binary\n\n"; 
       print FTP "\# Download the file to specified directory\n"; 
       my @get_files=split(/,/,$file_pattern); 
       foreach my $file (@get_files){ 
        if ($delete_ftp_files eq "Y" || $delete_ftp_files eq "Yes") { 
         print FTP "put -nopreservetime -nopermissions -delete $file$file_extension\n"; 
      
        } 
        else { 
         print FTP "put -nopreservetime -nopermissions $file$file_extension\n"; 
      
        } 
      
       } 
      
       print FTP "\n\n"; 
       print FTP "\# Disconnect\n"; 
       print FTP "close\n\n"; 
       print FTP "\# Exit WinSCP\n"; 
       print FTP "exit\n\n"; 
       close(FTP); 
       runLogger("$pluginname: creating temporary winscp file"); 
      
      }
      ```

   1. Planifiez le script en fonction de la disponibilité des fichiers à ftp_address.
   1. La convention de dénomination du fichier doit être AAAAMMJJ-&lt;nom_flux_hors ligne>-00.*

1. Transférez des fichiers d&#39;un répertoire NAS vers un autre répertoire NAS.

   1. Copiez et collez le fichier se connectant directement à un répertoire NAS à partir d&#39;un autre. Procédez comme suit :)

      connexion au serveur -> aller à Exécuter -> \\server_name\E$ [le nouveau dossier s&#39;ouvre et copie ou déplace directement les fichiers]

   1. Utilisez le script &quot;copy_files.pl&quot; pour copier des fichiers d’un serveur vers un autre ou &quot;move_files.pl&quot; pour déplacer des fichiers d’un serveur vers un autre. (Ces fichiers sont disponibles dans E:\scripts\Scripository)

