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

### Hard/Soft Link
#### Create a file named original.txt in your home directory.
```
usamarashead@ur-ubuntu:~$ touch original.txt
```
#### Create a symbolic link named softlink.txt pointing to original.txt.
```
usamarashead@ur-ubuntu:~$ ln -s original.txt softlink.txt
```
#### Verify the symbolic link and ensure it points to the correct file.
```
usamarashead@ur-ubuntu:~$ ls -l
total 64
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 23 00:23 candy-bucket
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Desktop
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Documents
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov  4 12:57 Downloads
-rw-rw-r--  1 student      student         0 Nov 29 21:09 example.txt
drwxrwxr-x 10 usamarashead usamarashead 4096 Nov  9 20:34 Git_Learn_Anis
drwxrwxrwx  3 usamarashead usamarashead 4096 Nov 28 20:15 ic-bash
drwxrwxr-x  5 usamarashead usamarashead 4096 Nov 26 13:49 ic-linux-os
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 25 19:47 Interactive_Cares
drwxrwxr-x  4 usamarashead usamarashead 4096 Nov 29 20:59 linux_fundamentals
drwxr-xr-x  3 usamarashead usamarashead 4096 Nov 13 21:43 Music
-rw-rw-r--  1 usamarashead usamarashead    0 Nov 30 12:48 original.txt
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Pictures
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov 29 21:18 project
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Public
drwx------  6 usamarashead usamarashead 4096 Nov  2 13:56 snap
lrwxrwxrwx  1 usamarashead usamarashead   12 Nov 30 12:48 softlink.txt -> original.txt
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Templates
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Videos
```

<img width="700" alt="01  softlink" src="screenshots/01. softlink.png">

#### Delete the original file original.txt and observe the status of the symbolic link.
```
usamarashead@ur-ubuntu:~$ rm original.txt
usamarashead@ur-ubuntu:~$ ls -l
total 64
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 23 00:23 candy-bucket
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Desktop
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Documents
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov  4 12:57 Downloads
-rw-rw-r--  1 student      student         0 Nov 29 21:09 example.txt
drwxrwxr-x 10 usamarashead usamarashead 4096 Nov  9 20:34 Git_Learn_Anis
drwxrwxrwx  3 usamarashead usamarashead 4096 Nov 28 20:15 ic-bash
drwxrwxr-x  5 usamarashead usamarashead 4096 Nov 26 13:49 ic-linux-os
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 25 19:47 Interactive_Cares
drwxrwxr-x  4 usamarashead usamarashead 4096 Nov 29 20:59 linux_fundamentals
drwxr-xr-x  3 usamarashead usamarashead 4096 Nov 13 21:43 Music
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Pictures
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov 29 21:18 project
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Public
drwx------  6 usamarashead usamarashead 4096 Nov  2 13:56 snap
lrwxrwxrwx  1 usamarashead usamarashead   12 Nov 30 12:48 softlink.txt -> original.txt
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Templates
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Videos
```
<img width="700" alt="01  softlink" src="screenshots/02. soft link check.png">

#### Create a file named datafile.txt in your home directory.
```
usamarashead@ur-ubuntu:~$ touch datafile.txt
```
#### Create a hard link named hardlink.txt pointing to datafile.txt.
```
usamarashead@ur-ubuntu:~$ ln datafile.txt  hardlink.txt
```
#### Verify the hard link and ensure it correctly points to the file.
```
usamarashead@ur-ubuntu:~$ ls -i datafile.txt
1972829 datafile.txt
usamarashead@ur-ubuntu:~$ ls -i hardlink.txt
1972829 hardlink.txt
```
#### Check the inode of both datafile.txt and hardlink.txt
```
usamarashead@ur-ubuntu:~$ ls -i datafile.txt
1972829 datafile.txt
usamarashead@ur-ubuntu:~$ ls -i hardlink.txt
1972829 hardlink.txt
```
#### Delete the original file datafile.txt and observe the status of the hard link.
```
usamarashead@ur-ubuntu:~$ rm datafile.txt
usamarashead@ur-ubuntu:~$ ls -l
total 64
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 23 00:23 candy-bucket
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Desktop
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Documents
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov  4 12:57 Downloads
-rw-rw-r--  1 student      student         0 Nov 29 21:09 example.txt
drwxrwxr-x 10 usamarashead usamarashead 4096 Nov  9 20:34 Git_Learn_Anis
-rw-rw-r--  1 usamarashead usamarashead    0 Nov 30 13:26 hardlink.txt
drwxrwxrwx  3 usamarashead usamarashead 4096 Nov 28 20:15 ic-bash
drwxrwxr-x  5 usamarashead usamarashead 4096 Nov 26 13:49 ic-linux-os
drwxrwxr-x  3 usamarashead usamarashead 4096 Oct 25 19:47 Interactive_Cares
drwxrwxr-x  4 usamarashead usamarashead 4096 Nov 29 20:59 linux_fundamentals
drwxr-xr-x  3 usamarashead usamarashead 4096 Nov 13 21:43 Music
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Pictures
drwxr-xr-x  2 usamarashead usamarashead 4096 Nov 29 21:18 project
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Public
drwx------  6 usamarashead usamarashead 4096 Nov  2 13:56 snap
lrwxrwxrwx  1 usamarashead usamarashead   12 Nov 30 12:48 softlink.txt -> original.txt
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Templates
drwxr-xr-x  2 usamarashead usamarashead 4096 Oct 21 18:37 Videos
```
#### Find all .txt files in your home directory. ( use find command. Run find --help for usage)
```
usamarashead@ur-ubuntu:~$ find  -type f -name '*.txt'
```

### Package installation
#### Update repo cache using apt/apt-get
```
usamarashead@ur-ubuntu:~$ sudo apt update
Hit:1 http://archive.ubuntu.com/ubuntu noble InRelease
Get:2 http://archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [673 kB]
Get:5 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main i386 Packages [337 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Components [131 kB]
Get:8 http://security.ubuntu.com/ubuntu noble-security/main amd64 Components [7,180 B]
Get:9 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Components [212 B]
Get:10 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [719 kB]
Get:11 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Components [212 B]
Get:12 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Components [51.9 kB]
Get:13 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Components [212 B]
Get:14 http://archive.ubuntu.com/ubuntu noble-updates/universe i386 Packages [442 kB]
Get:15 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Components [310 kB]
Get:16 http://archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Components [940 B]
Get:17 http://archive.ubuntu.com/ubuntu noble-backports/main amd64 Components [208 B]
Get:18 http://archive.ubuntu.com/ubuntu noble-backports/restricted amd64 Components [216 B]
Get:19 http://archive.ubuntu.com/ubuntu noble-backports/universe amd64 Components [11.7 kB]
Get:20 http://archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 Components [212 B]
Fetched 3,063 kB in 15s (206 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
51 packages can be upgraded. Run 'apt list --upgradable' to see them.
```
<img width="700" alt="01  softlink" src="screenshots/03. package update.png">

#### Install a package named tree
```
usamarashead@ur-ubuntu:~$ sudo apt-get install tree
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  mysql-client-8.0 mysql-client-core-8.0 mysql-common
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  tree
0 upgraded, 1 newly installed, 0 to remove and 51 not upgraded.
Need to get 47.1 kB of archives.
After this operation, 111 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble/universe amd64 tree amd64 2.1.1-2ubuntu3 [47.1 kB]
Fetched 47.1 kB in 2s (29.9 kB/s)
Selecting previously unselected package tree.
(Reading database ... 213110 files and directories currently installed.)
Preparing to unpack .../tree_2.1.1-2ubuntu3_amd64.deb ...
Unpacking tree (2.1.1-2ubuntu3) ...
Setting up tree (2.1.1-2ubuntu3) ...
Processing triggers for man-db (2.12.0-4build2) ...
```
<img width="700" alt="01  softlink" src="screenshots/04. package install.png">

#### Install gcloud CLI tool using apt ( Follow instructions from here: https://cloud.google.com/sdk/docs/install#deb )
```
usamarashead@ur-ubuntu:~$ sudo apt-get update && sudo apt-get install google-cloud-cli
```
<img width="700" alt="01  softlink" src="screenshots/05. install Gcloud.png">
