# ReadMeSys1Exam

Let's install and configure VSFTPD here today

1- Get to SuperUser Mode first 
2- Once done, install VSFTPD by using (apt-get install vsftpd)
3- Configure then by using (nano /etc/vsftpd.conf)
4- Basically, in this part, you basically modify some line in the file vsftpd.conf;
    Here's All modification you have to do
        delete the "#" on the line 31,99,100,122.123.125 and 131
        then on the line 157, write (local_root=public_html) and on the ligne 158,write (seccomp_sandbox=NO)
5- Then use the command /usr/sbin/adduser ibra
    then the other command /etc/vsftpd.chroot_list
6- We just have to restart the server (systemctl restart vsftpd)
7- Then we have to modify our virtual's machine network to be in intern network
8- Then finally use (resolve /etc/resolv.conf) to configure ip addresses.

CONGRATULATIONS !!!