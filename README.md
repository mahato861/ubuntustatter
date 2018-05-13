# run this line into your machine console using root permission 

```
curl -sL https://raw.githubusercontent.com/prabhatpankaj/ubuntustarter/master/initial.sh | sh

```

# ubuntu installation essentials mannually
```
export LANG=en_US.UTF-8
export LANGUAGE=en_US.UTF-8
export LC_CTYPE="en_US.UTF-8"
export LC_NUMERIC="en_US.UTF-8"
export LC_TIME="en_US.UTF-8"
export LC_COLLATE="en_US.UTF-8"
export LC_MONETARY="en_US.UTF-8"
export LC_MESSAGES="en_US.UTF-8"
export LC_PAPER="en_US.UTF-8"
export LC_NAME="en_US.UTF-8"
export LC_ADDRESS="en_US.UTF-8"
export LC_TELEPHONE="en_US.UTF-8"
export LC_MEASUREMENT="en_US.UTF-8"
export LC_IDENTIFICATION="en_US.UTF-8"
export LC_ALL=en_US.UTF-8

sudo nano /etc/default/locale

LANG=en_US.UTF-8
LANGUAGE=en_US.UTF-8
LC_CTYPE="en_US.UTF-8"
LC_NUMERIC="en_US.UTF-8"
LC_TIME="en_US.UTF-8"
LC_COLLATE="en_US.UTF-8"
LC_MONETARY="en_US.UTF-8"
LC_MESSAGES="en_US.UTF-8"
LC_PAPER="en_US.UTF-8"
LC_NAME="en_US.UTF-8"
LC_ADDRESS="en_US.UTF-8"
LC_TELEPHONE="en_US.UTF-8"
LC_MEASUREMENT="en_US.UTF-8"
LC_IDENTIFICATION="en_US.UTF-8"
LC_ALL=en_US.UTF-8

sudo locale-gen en_US.UTF-8

sudo apt-get update


sudo apt-get install -y build-essential

sudo apt-get install openjdk-8-jre

sudo nano /etc/environment

JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/

source /etc/environment

sudo adduser demo

sudo gpasswd -a demo sudo

sudo apt-get install -y postgresql postgresql-contrib

sudo su - postgres

psql

CREATE DATABASE mydatabasedb;
CREATE USER mydatabaseuser WITH PASSWORD 'mydatabasepassword';
ALTER ROLE mydatabaseuser SET default_transaction_isolation TO 'read committed';
ALTER ROLE mydatabaseuser SET timezone TO 'Asia/Kolkata';
GRANT ALL PRIVILEGES ON DATABASE mydatabasedb TO mydatabaseuser;

\q

exit

sudo apt-get update

sudo apt-get install apache2

sudo nano /etc/apache2/apache2.conf
ServerName server_domain_or_IP

sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_balancer
sudo a2enmod lbmethod_byrequests
sudo systemctl restart apache2

```

```
sudo nano /etc/apache2/sites-available/proxy-host.conf

<VirtualHost *:80>
  ServerAdmin webmaster@localhost
  DocumentRoot /home/demo/
  ErrorLog ${APACHE_LOG_DIR}/error.log
  CustomLog ${APACHE_LOG_DIR}/access.log combined
  ProxyPreserveHost On
  # Servers to proxy the connection, or
  # List of application servers Usage
  ProxyPass / http://server-ip-address:8080/
  ProxyPassReverse / http://server-ip-address:8080/
  ServerName localhost
</VirtualHost>

 cd /etc/apache2/sites-available/
 
 sudo a2ensite proxy-host
 sudo a2dissite 000-default
 sudo service apache2 reload
 
 sudo nano /etc/apache2/ports.conf
 Listen 8080
 sudo /etc/init.d/apache2 restart
 


```
