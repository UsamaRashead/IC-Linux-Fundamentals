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

### File Modification
#### Create a file named example.txt in your home directory.
```
usamarashead@ur-ubuntu:~$ touch example.txt
```
#### Change the owner of example.txt to a user named student
```
usamarashead@ur-ubuntu:~$ sudo chown student:student example.txt
```
#### Change the group of example.txt to a group named students.
```
usamarashead@ur-ubuntu:~$ sudo chown student:student example.txt
```
#### Verify the changes using appropriate commands.
```
usamarashead@ur-ubuntu:~$ ls -l
total 60
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Desktop
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Documents
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov  4 12:57 Downloads
-rw-rw-r--  1 student      student         0 Nov 29 21:09 example.txt
drwxrwxrwx  3 usamarashead usamarashead 4096 Nov 28 20:15 ic-bash
drwxrwxr-x  5 usamarashead usamarashead 4096 Nov 26 13:49 ic-linux-os
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 25 19:47 Interactive_Cares
drwxr-xr-x  3 usamarashead usamarashead 4096 Nov 13 21:43 Music
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Pictures
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Public
drwx------  6 usamarashead usamarashead 4096 Nov  2 13:56 snap
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Templates
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Videos
```

### Ownership
#### Create a directory named project in your home directory.
```
usamarashead@ur-ubuntu:~$ mkdir project
```
#### Create a file named report.txt inside the project directory.
```
usamarashead@ur-ubuntu:~$ touch ~/project/report.txt
usamarashead@ur-ubuntu:~$ ls ~/project/
report.txt
```
#### Set the permissions of report.txt to read and write for the owner, and read-only for the group and others.
```
usamarashead@ur-ubuntu:~/project$ chmod 644 report.txt
```
#### Set the permissions of the project directory to read, write, and execute for the owner, and read and execute for the group and others
```
usamarashead@ur-ubuntu:~/project$ chmod 755 ~/project/
```
#### Verify the changes using appropriate commands.
```
usamarashead@ur-ubuntu:~$ ls -l | grep project
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov 29 21:18 project
usamarashead@ur-ubuntu:~$ ls -l ~/project/ | grep report.txt
-rw-r--r-- 1 usamarashead usamarashead 0 Nov 29 21:18 report.txt
```

### User add/modify
#### Create a new user named developer.
```
usamarashead@ur-ubuntu:~$ sudo useradd developer
```
#### Set the home directory of the user developer to /home/developer_home.
```
usamarashead@ur-ubuntu:~$ sudo usermod -d /home/developer_home developer
```
#### Assign the shell /bin/sh to the user developer.
```
usamarashead@ur-ubuntu:~$ sudo chsh -s /bin/sh developer
```
#### Verify the new user's information.
```
usamarashead@ur-ubuntu:~$ cat /etc/passwd | grep developer
developer:x:1003:1003::/home/developer_home:/bin/sh
```
#### Change the username of the user developer to devuser.
```
usamarashead@ur-ubuntu:~$ sudo usermod -l devuser developer
```
#### Add devuser to a group named devgroup.
```
usamarashead@ur-ubuntu:~$ sudo groupadd devgroup
usamarashead@ur-ubuntu:~$ sudo usermod -a -G devgroup devuser
```
#### Set the password of devuser to devpass. ( hint: use passwd command. Run passwd --help to see available options)
```
usamarashead@ur-ubuntu:~$ sudo passwd devuser
New password:
BAD PASSWORD: The password is shorter than 8 characters
Retype new password:
passwd: password updated successfully
usamarashead@ur-ubuntu:~$
```
#### Verify the changes made to the user.
```

```

