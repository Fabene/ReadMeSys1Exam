# ReadMeSys1Exam

So here, you'll find how to install apache2 and configure it from scratch 

1- First of all, get to your terminal first and connect yourself
2- Then connect as the SuperUser by using the command su 
3- After that, use the command (apt-update) to update ur terminal
4- Then the command : (apt-get install apache2)
5- After that, in theory, apache2 should be installed and it should be in a file that auto created in "var" and which is named "www"
6- Now to get there, use (cd /var/etc/html/)
7- the command ls help us see what in html file 
8-Normally u should find a file name index.html
9- lets create a backup in case something wrong happen by using (cp index.html index.html.bak)
10- By configuring the file index.html, we can modify what will be shown in our apache2 server
11- Now use the command rm index.html
12- Then open it by using nano index.html
13- Then freely configure it

Congratulations!! You've installed apache2
