# 191011
[ nginx ]

0. Lesson Leanred: When the nginx cannot connect the Django server, check the configuration file @etc/nginx/conf.d

1. Problem: Nginx shows 404 for every API

2. Solution implemented:
  - check /etc/nginx/sites-avaiable and set up the domain name
  - relink the /etc/nginx/sites-enabled (symbolic link) to the appropriate domain in sites-available

3. Tips
  - sites-avaible shows the options that we can set as domain to which the nginx connects
  - sites-enabled shows the actual target domains connected to nginx
  
