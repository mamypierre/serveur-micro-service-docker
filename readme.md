create folder src/project1 ,src/project2 add httpd-vhosts.conf ex : DocumentRoot /usr/local/apache2/htdocs/project1 and restart apache container 

Next, navigate in your terminal to the directory you cloned this, and spin up the containers for the web server by running docker-compose up -d --build site_apache

docker exec service_php74  php -v
