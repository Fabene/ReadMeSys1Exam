# ReadMeSys1Exam

Ok, So Now, we're gonna learn how to install and configure NGINX together:

1- Once in your Linux, Get to your SuperUser Mode :the command :(su) 
2- Then Install It :
     the command : 
         (apt-get install nginx -y)  (the small "-y" means that u directly said yes to all terms of use of NGINX)
3- Verify if NGINX is installed (nginx -v)
4- Then Let's create a file in "www" which is gonna help us to keep all our files for our site : 
    the command :
         mkdir /var/www/"NameOfYourWebSite's_Domain"
5- Let's determine now who is the possessor of the NGINX user's file:
    The command:
        chown -R www-data:www-data /var/www/"NameOfTheWebSite"
6- Now, we apply all the right (chmod 755 /var/"NameOfTheWebSite")
7- Now we create the .html file for the root (nano /var/www/"NameOfTheWebSite/index.html)
8- Creation of the configuring file (the file config)
    the command:
        nano /etc/nginx/sites-available/Site'sName
Here's an example for you:
    server{
        listen 80;
        listen [;;]:80;

        root/var/www/NameOfTheWebSite;

        index index.html;
        server_name WebSite'sName www WebSite'sName;

        location / {
            try_files $uri/ =404;
        }
    }
9- Configure it to make it permanant (ls -s /etc/nginx/site-available/"WebSite'sName" /etc/nginx/sites-enables/"WebSite'sName")
10- We can verify our configuration by using the command (nginx -t)
11- Then we restart NGINX (systemctl restart nginx)

GOOD JOB YOU'VE INSTALLED NGINX!!!!