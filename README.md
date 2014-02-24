#Installation SFLPhone - Website en local


Allez dans le répertoire désiré (un de vos localhost)

>sudo drush archive-restore **nomDeLarchive** 

Cela créera un dossier 'drupal'





####OPTIONEL
Changez le propriétaire des fichiers

> sudo chown -R **user**:**user** drupal/  (ou **user** est votre username ou www-data)









##Bd
> mysql -u ***root*** -p -e "create database sflphone_website;"

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



##Remplacer le bloc twitter
https://twitter.com/settings/widgets/new/search
Connectez-vous à n'importe quel compte.
Entrer l'usertag:
>@sflphone

Cochez:
>N'afficher que les Top Tweets

Coller la couleur de liens sflphone:
    
> "#ffa306"

Générez le code


dans votre navigateur, ajouter 'user' à votre url
Connectez vous avec les logins fourni par sflvault (1056)

Dans site building / blocks / add block

Entrer la description (exemple: news-feed twitter de sfl), le titre (exemple: twitter)

Dans block body:
clic sur "**disable rich text**", puis Input Format / **Full HTML**

Collez le code twitter

Choisir :
>Show on only the listed pages.

Collez dans **Pages** (pour la page news et tout ses sous-noeuds:
>news/all
news/*

Clic "save block"


Chercher votre bloc en bas de la page, 
glissez-déposer le plus haut dans first sidebar
**OU** utiliser le dropdown
 
Supprimer l'ancien (placez-le à "none"), allez tout en bas, et faites "save blocks".

Le nouveau twitter feed est en place