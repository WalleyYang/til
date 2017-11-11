#### Restrict access to ip address 
1. Go to the /etc/apache2/conf-available/phpmyadmin.conf file.
2. Add the below within <Directory /usr/share/phpmyadmin></Directory><br/>
    Order Deny,Allow<br/>
    Deny from all<br/>
    Allow from 127.0.0.1<br/>
    Allow from myip
3. Restart Apache
    
