### Simple Help for configuring apache2 from scratch

1. sudo apt-get install apache2 apache2-utils
2. mkdir ~/sites
3. sudo nano /etc/apache2/sites-available/site.example.conf
#### Write down apache configs about the site like below:
```bash
<VirtualHost *:80>
     ServerAdmin YOUR_EMAIL_ADDRESS
     ServerName {your virtual site}
     DocumentRoot /home/user/web
     <Directory /home/user/web>
             Options Indexes FollowSymLinks MultiViews
             DirectoryIndex index.html index.php
             AllowOverride All
             Order Allow,Deny
             Allow from all
             Require all granted
     </Directory>
</VirtualHost>
```
4.sudo a2ensite /etc/apache2/sites-available/site.example.conf
5. sudo systemctl apache2 reload
6. sudo nano /etc/hosts
# 127.0.0.1. localhost change to your servername;
7. Create a .html file in ~/sites
8. load servername into firefox or any browser 
9-10. Done.
