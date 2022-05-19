# ReadMeSys1Exam

Okay, Before installing NFS, We need to configure our ip address and ping between our two servers;

1- Give their those names :
    Clt_NFS and Srv_NFS
2- Configure Ip Address:
    Clt_Srv : 192.168.10.10/24
    Srv_NFS : 192.168.10.250/24

Now let's install our Nfs Server 
1- We use the command (apt-get install nfs-common nfs-kernel server portmap)
2- Then we need to prepare the file we're going to share /home/user/data_ro/ and /home/user/data_rw/
3- we share the two files with the client Clt_NFS by adding the two lines in the file
4- Add the sharing file in the file /etc/exports/ :
        /home/user/data_ro 192.168.10.10 (ro)
        /home/user/data_rw 192.168.10.10 (rw)
5- Then we restart the service NFS : use the commande (/etc/init.d/nfs-kernel-server restart)

Now lets install the client Clt_NFS
1- Once again, use the command (apt-get install nfs-common)
2- Then create 2 files to mount those distant files
        get to user by using cd /home/user
        then use the command mkdir /home/user/nfs_data_ro
                             mkdir /home/user/nfs_data_rw
Then mount the two shared files on the server in the local file
the command : 
    mount -t nfs 192.168.10.250 : /home/user/data_ro /home/user/nfs_data_ro
    mount -t nfs 192.168.10.250 : /home/user/data_rw /home/user/nfs_data_rw
Then test your access to the shared files by using the client

Now lets create a sharing permanant mount of NFS
1- Restart again the client and try again to access to the shared file
2- If yes, then mount the two file permanantly in the files /etc/fstab
    192.168.10.250: /home/user/data_ro /home/user/nfs_data_ro nfs _netdev,nodev,noexec 0 0
    192.168.10.250 : /home/user/data_rw /home/ser/nfs_data_rw nfs _netdev,nodev,noexec 0 0
3- Finally, restart one last time the client and try again to get access to the shared file;

CONGRATULATIONS YOU'VE INSTALLED NFS CORRECTLY