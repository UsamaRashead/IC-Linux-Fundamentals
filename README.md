# IC-Linux-Fundamentals
Linux Fundamentals - Assignment 1 by Interactive Care

### File System Navigation
#### List the contents of the home directory.
```
usamarashead@ur-ubuntu:~$ ls
candy-bucket  Documents  Git_Learn_Anis  ic-linux-os        Music     Public  Templates
Desktop       Downloads  ic-bash         Interactive_Cares  Pictures  snap    Videos
```

#### Change the current directory to /var/log and list its contents.
```
usamarashead@ur-ubuntu:~$ cd /var/log
usamarashead@ur-ubuntu:/var/log$ ls
alternatives.log    boot.log.3             dist-upgrade    gpu-manager.log  README
alternatives.log.1  boot.log.4             dmesg           hp               speech-dispatcher
apport.log          boot.log.5             dmesg.0         installer        sssd
apt                 boot.log.6             dmesg.1.gz      journal          syslog
auth.log            boot.log.7             dmesg.2.gz      kern.log         syslog.1
auth.log.1          bootstrap.log          dmesg.3.gz      kern.log.1       syslog.2.gz
auth.log.2.gz       btmp                   dmesg.4.gz      kern.log.2.gz    syslog.3.gz
auth.log.3.gz       btmp.1                 dpkg.log        kern.log.3.gz    syslog.4.gz
auth.log.4.gz       cloud-init.log         dpkg.log.1      kern.log.4.gz    sysstat
boot.log            cloud-init-output.log  faillog         lastlog          unattended-upgrades
boot.log.1          cups                   fontconfig.log  openvpn          wtmp
boot.log.2          cups-browsed           gdm3            private
```

#### Find and display the path to the bash executable using the which command.
```
usamarashead@ur-ubuntu:/var/log$ which $SHELL
/bin/bash
```
#### Find current shell
```
usamarashead@ur-ubuntu:/var/log$ echo $0
-bash
```

### File and Directory Operations
#### Create a directory named linux_fundamentals in your home directory.
```
usamarashead@ur-ubuntu:~$ mkdir linux_fundamentals
```

#### Inside linux_fundamentals, create a subdirectory named scripts.
```
usamarashead@ur-ubuntu:~/linux_fundamentals$ mkdir scripts
```
#### Create an empty file named example.txt inside the linux_fundamentals directory.
```
usamarashead@ur-ubuntu:~/linux_fundamentals$ touch example.txt
```
#### Copy example.txt to the scripts directory.
```
usamarashead@ur-ubuntu:~/linux_fundamentals$ cp example.txt ~/linux_fundamentals/scripts/
```
#### Move example.txt from linux_fundamentals to linux_fundamentals/backup.
```
usamarashead@ur-ubuntu:~/linux_fundamentals$ mkdir backup
usamarashead@ur-ubuntu:~/linux_fundamentals$ mv ~/linux_fundamentals/example.txt ~/linux_fundamentals/backup/
usamarashead@ur-ubuntu:~/linux_fundamentals$ ls ~/linux_fundamentals/backup/
example.txt
```

### Permissions

#### Change the permissions of example.txt to read and write for the owner, and read-only for the group and others.
```
usamarashead@ur-ubuntu:~/linux_fundamentals/backup$ chmod 644 example.txt
```
#### Verify the permission changes using ls -l
```
usamarashead@ur-ubuntu:~/linux_fundamentals/backup$ ls -l
total 0
-rw-r--r-- 1 usamarashead usamarashead 0 Nov 29 20:58 example.txt
```
