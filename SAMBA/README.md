# ReadMeSys1Exam

Let's install and configure SAMBA here today

1- First Of all, lets connect into SuperUser mode (as a root) 
2- Install Samba; for that you'll need the command :(apt-get install samba )
3- Once installed, lets configure it 
4- We need to get to home first (cd /home/)
5- Then we create a file; here's an example : (mkdir BetaTest)
6- Now lets change the right of this file so it can be secured (chmod 777 BetaTest/)
7- Then create un new user like (useradd dea)
8- Then let's use the command (smbpasswd -a dea)
9- Once done, lets configure now (nano /etc/samba/smb.conf)
10- One there, "nano" helps us to right new things in smb.config. Let's add those :
    [BetaTest]
    path - /home/BetaTest
    valid users = dea
    browseable = yes
    writeable = yes
11- Once done, restart Samba by using (/etc/init.d/samba restart)

CONGRATULATIONS YOU'VE JUST INSTALLED AND CONFIGURED SAMBA!!!!!!!!!!