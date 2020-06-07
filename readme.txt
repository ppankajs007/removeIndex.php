Remove index.php from url

1. htaccess file  out of application 
 'Your Folder'
 application
 system
 .htaccess

2. add htaccess
<IfModule mod_rewrite.c> 
RewriteEngine on
RewriteBase /your-project-directory-name/
RewriteCond $1 !^(index.php|resources|robots.txt)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L,QSA]
</IfModule>

3. Go to application/config/config.php
   You see that
   $config['index.php'] = 'index.php';
   Replace this code
   $config['index.php'] = '';   
