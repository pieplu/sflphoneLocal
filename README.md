#Installation SFLPhone - Website en local


Allez dans le répertoire désiré (un de vos localhost)

>sudo drush archive-restore **nomDeLarchive** 

Cela créera un dossier 'drupal'





####OPTIONEL
Changez le propriétaire des fichiers

> sudo chown -R **user**:**user** drupal/  (ou **user** est votre username ou www-data)









##Bd
> mysql -u ***root*** -p -e "create database 'sflphone_website '"

(où **root** est votre user de bd)
 
    

Importer la bd (le fichier est dans l'archive, se placer au bon dossier)
>mysql -u root -p sflphone_website < sflphone_website.sql




Allez au fichier settings.php
>cd drupal/sites/default
**nano** settings.php (**nano** ou autre éditeur de texte)

à la ligne 92 (environ)
mettez à jour **$db_url** (avec votre user et pass local mysql)

>$db_url = 'mysqli://**user**:**pass**@localhost/sflphone_website';

>drush status

Normalement, il apparait ceçi:
 >Database:  Connected





Allez sur votre localhost, le site fonctionne!

Identifiants sflvault: s#1056 et s#1627 (twitter)


