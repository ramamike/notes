Create a directory named ‘simple-site‘ in ‘/var/www/html‘

	sudo mkdir -p /var/www/html/simple-site/

Create an ‘index.html‘ file in ‘/var/www/html/simple-site/‘

Give Read permission for all users in the system.

	sudo chmod 0666 /var/www/html/simple-site/index.html

Creating a local domain name.

	sudo vim /etc/hosts

Ubuntu uses this file to get IP mapping first, before it goes to look into an external network for any kind of matches.

# default
127.0.0.1       localhost    
# append this 
127.0.0.1       simplesite.local


	sudo vim /etc/nginx/sites-available/simple-site.conf

Simplest configuration to host a folder the way it is.

	server {
       		listen 80;
      		 server_name simplesite.local;
       		index index.html index.htm;
       		root /var/www/html/simple-site/;
	}


Link the file into sites-enabled the directory.

	sudo ln -s /etc/nginx/sites-available/simple-site.conf /etc/nginx/sites-enabled/simple-site.conf

Test nginx server configuration before restarting the server.

	sudo nginx -t

nginx: configuration file /etc/nginx/nginx.conf test is successful

Restart Server.

sudo service nginx restart
