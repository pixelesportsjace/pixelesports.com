# Commands
php artisan auto-generate-brackets:cron

# To start Mysql server locally
mysql.server start

# To run the project locally
php artisan serve


# To seed db
You need to uncomment code in DatabaseSeeder
php artisan db:seed


# To reset storage
Remove public/storage folder then
php artisan storage:link

# To Crons
* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1

#notes

The source control is in bitbucket
https://teamwepro@bitbucket.org


# Deploy to AWS EC2
1. Create EC2 Key Pair and save the file locally
2. Go to aws cloudformation
3. Create stack and choose build.yaml
4. Once the stack is created, go to AWS EC2
5. Find the created EC2, and connect to the server
6. Make sure you have the source code in CodeCommit
7. Run: git clone https://repo
8. Enter username and password
9. To pull another version: backup current into another folder and then call
   git pull origin release/live
10. sudo apt update
11. sudo apt install nginx
12. systemctl status nginx
13. sudo systemctl restart nginx
14. sudo nginx -t
15. now we need to install php
16. sudo apt update
17. sudo apt install --no-install-recommends php8.1
18. sudo apt-get install php8.1-cli php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-bcmath php8.1-fpm
19. sudo systemctl restart nginx
20. sudo systemctl restart php8.1-fpm
21. sudo mkdir -p /var/www/html/
22. sudo chown -R ubuntu:ubuntu /var/www/html/
23. Now go to /var/www/html
24. Git pull the project
25. Cd into the project
26. chmod -R ugo+rw storage/logs
27. chmod -R ugo+rw storage/framework
28. Setting up the server -- make sure to write the right config
29. sudo nano /etc/nginx/nginx.conf
30. client_max_body_size 2M;
29. cd /etc/nginx/sites-available/
30. sudo nano default
31. Set the nginx server conf
32. install composer
33. go to root folder and run  php composer.phar update
34. chmod -R ugo+rw storage/logs
35. chmod -R ugo+rw storage/framework
36. create .env and move config data over
37. php artisan migrate
38. Run cron
39. * * * * * php artisan schedule:run >> /dev/null 2>&1
40. php artisan storage:link
41. chmod 775 public/storage

# To pull latest changes 
Either use ftp client to push the changes to the server
Or ssh into the server, and then 
git pull origin release-live
