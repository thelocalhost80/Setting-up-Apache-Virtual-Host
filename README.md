# Setting-up-Apache-Virtual-Host

Refer demoproject.conf for adding in the cofiguration file.

### Basic command line to follow:

`$ cd /etc/apache2` <br>
`$ cd /sites-available`<br>
`$ touch denoproject.conf` <br>
`$ gedit dempproject.conf` <br/>

Add following code in demoproject.conf file <br />
<p>
   
   
    <VirtualHost *:80>
    ServerName demoproject.com
    ServerAlias www.demoproject.com
    ServerAdmin webmaster@demoproject.com
    DocumentRoot /var/www/html/new_project/public
    
    <Directory /var/www/html/new_project/public>
        Options -Indexes +FollowSymLinks
        AllowOverride All
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/demoproject.com-error.log
    CustomLog ${APACHE_LOG_DIR}/demoproject.com-access.log combined
    </VirtualHost>

Save the file and copy the same file in sites-enabled folder

`$ sudo a2ensite demoproject.conf`

Restart apache server

`$ systemctl restart apache2`

Then add the server name in hosts file

`$ cd /etc` <br>
`$ gedit hosts`

Add the following line in the hosts file with the server name of your choice

`127.0.0.1 demoproject.com`
