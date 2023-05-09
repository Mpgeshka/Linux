# Вывод информации о версии ОС
```powershell
madmin@madmin-VirtualBox:~$ uname
Linux
madmin@madmin-VirtualBox:~$ hostnamectl
 Static hostname: madmin-VirtualBox
       Icon name: computer-vm
         Chassis: vm
      Machine ID: ae545c1ebd3a404a836711d51816221a
         Boot ID: 14544cb229c240ffa58801065f9605d7
  Virtualization: oracle
Operating System: Ubuntu 22.04.2 LTS
          Kernel: Linux 5.19.0-41-generic
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
madmin@madmin-VirtualBox:~$ lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 22.04.2 LTS
Release:        22.04
Codename:       jammy
madmin@madmin-VirtualBox:~$ cat /etc/os-release
PRETTY_NAME="Ubuntu 22.04.2 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.2 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
```
# Установка Midnight Commander
```powershell
madmin@madmin-VirtualBox:~$ sudo apt install mc
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Suggested packages:
  arj catdvi | texlive-binaries dbview djvulibre-bin epub-utils gv imagemagick
  libaspell-dev links | w3m | lynx odt2txt python python-boto python-tz unar
  wimtools
The following NEW packages will be installed:
  mc
0 upgraded, 1 newly installed, 0 to remove and 1 not upgraded.
Need to get 547 kB of archives.
After this operation, 1 574 kB of additional disk space will be used.
Get:1 http://ru.archive.ubuntu.com/ubuntu jammy/universe amd64 mc amd64 3:4.8.27-1 [547 kB]
Fetched 547 kB in 0s (1 777 kB/s)
Selecting previously unselected package mc.
(Reading database ... 203984 files and directories currently installed.)
Preparing to unpack .../mc_3%3a4.8.27-1_amd64.deb ...
Unpacking mc (3:4.8.27-1) ...
Setting up mc (3:4.8.27-1) ...
update-alternatives: using /usr/bin/mcview to provide /usr/bin/view (view) in auto mode
Processing triggers for mailcap (3.70+nmu1ubuntu1) ...
Processing triggers for desktop-file-utils (0.26-1ubuntu3) ...
Processing triggers for gnome-menus (3.36.0-1ubuntu3) ...
madmin@madmin-VirtualBox:~$ mc
```