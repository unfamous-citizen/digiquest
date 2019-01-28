# DigiQuest
DigiQuest is a survey suite using a Web interface.

Installation :

It uses MySQL, you will need to import digi_survey.sql

You will need to setup a Virtual-Host with the proper config for CGI scripts.
here is a sample virtual-host config called digiquest.com.conf :


<VirtualHost digiquest.com:80>
   ServerAdmin webmaster@localhost

    #DocumentRoot /var/www
    DocumentRoot /home/digiquest/public_html

    <Directory />
            Options FollowSymLinks
            AllowOverride None
    </Directory>

    ScriptAlias /cgi-bin/ /home/digiquest/public_html/cgi-bin/
    <Directory /home/digiquest/public_html/cgi-bin/>
            AllowOverride None
            Options +ExecCGI -MultiViews +SymLinksIfOwnerMatch
            Order allow,deny
            Allow from all
    </Directory>

    ErrorLog /var/log/apache2/error.log

    LogLevel debug

    CustomLog /var/log/apache2/access.log combined

</VirtualHost>


Ensure that the public_html has R/W access to Apache's user www-data.

Configure the /cgi-bin/config/config_main.pm variables to match your environnement.

Finally, the following linux (Ubuntu) packages are required :

libdbd-mysql-perl
libxml-libxslt-perl
libspreadsheet-writeexcel-perl
libexcel-template-perl
libgd-perl
libgd-graph-perl

Log into the Management interface using the following credentials :

user : admin
password : test

Notes and disclaimer :

This is an old project iv'e developped and it's code is sloppy. However the main functions are implemented.
If you dont mind adapting it to your current needs it should do the job efficiently.



