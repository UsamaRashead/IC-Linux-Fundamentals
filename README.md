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
