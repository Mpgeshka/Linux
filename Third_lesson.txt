# 1. Управление пользователями:
## a)	создать нового пользователя;
```powershell
madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/user11 -m user11 
[sudo] password for madmin:
```
## b)	убедиться, что информация о нем появилась в соответствующих файлах в системе;
```powershell
madmin@madmin-VirtualBox:~$ tail /etc/passwd
colord:x:123:130:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:124:131::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:125:132:PulseAudio daemon,,,:/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:126:65534::/run/gnome-initial-setup/:/bin/false
hplip:x:127:7:HPLIP system user,,,:/run/hplip:/bin/false
gdm:x:128:134:Gnome Display Manager:/var/lib/gdm3:/bin/false
madmin:x:1000:1000:Maria,,,:/home/madmin:/bin/bash
sshd:x:129:65534::/run/sshd:/usr/sbin/nologin
user11:x:1001:1001::/home/user11:/bin/bash

madmin@madmin-VirtualBox:~$ tail /etc/group
colord:x:130:
geoclue:x:131:
pulse:x:132:
pulse-access:x:133:
gdm:x:134:
lxd:x:135:madmin
madmin:x:1000:
sambashare:x:136:madmin
user11:x:1001:

madmin@madmin-VirtualBox:~$ sudo tail /etc/shadow
colord:*:19411:0:99999:7:::
geoclue:*:19411:0:99999:7:::
pulse:*:19411:0:99999:7:::
gnome-initial-setup:*:19411:0:99999:7:::
hplip:*:19411:0:99999:7:::
gdm:*:19411:0:99999:7:::
madmin:$y$j9T$.fVD7xN.XdRS2nHYXkq2K/$ZrIwXiOKhYFlklgGVfXE7/YVgjxOz6o/KLUSd7nffk3:19480:0:99999:7:::
sshd:*:19480:0:99999:7:::
user11:!:19486:0:99999:7:::

madmin@madmin-VirtualBox:~$ sudo passwd user11
New password:
BAD PASSWORD: The password fails the dictionary check - it is too simplistic/systematic
Retype new password:
passwd: password updated successfully

madmin@madmin-VirtualBox:~$ sudo tail /etc/shadow
colord:*:19411:0:99999:7:::
geoclue:*:19411:0:99999:7:::
pulse:*:19411:0:99999:7:::
gnome-initial-setup:*:19411:0:99999:7:::
hplip:*:19411:0:99999:7:::
gdm:*:19411:0:99999:7:::
madmin:$y$j9T$.fVD7xN.XdRS2nHYXkq2K/$ZrIwXiOKhYFlklgGVfXE7/YVgjxOz6o/KLUSd7nffk3:19480:0:99999:7:::
sshd:*:19480:0:99999:7:::
user11:$y$j9T$61C7NHDs9k.3mBX4zNgmf0$eH1pB6BJzpjtm5OlnAnPACcadRCFCP7qfWMDYSLKZl3:19486:0:99999:7:::
```
## c)	удалить созданного пользователя;
```powershell
madmin@madmin-VirtualBox:~$ sudo userdel user11 -r
userdel: user11 mail spool (/var/mail/user11) not found

madmin@madmin-VirtualBox:~$ tail /etc/passwd
nm-openvpn:x:121:127:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
saned:x:122:129::/var/lib/saned:/usr/sbin/nologin
colord:x:123:130:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:124:131::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:125:132:PulseAudio daemon,,,:/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:126:65534::/run/gnome-initial-setup/:/bin/false
hplip:x:127:7:HPLIP system user,,,:/run/hplip:/bin/false
gdm:x:128:134:Gnome Display Manager:/var/lib/gdm3:/bin/false
madmin:x:1000:1000:Maria,,,:/home/madmin:/bin/bash
sshd:x:129:65534::/run/sshd:/usr/sbin/nologin

madmin@madmin-VirtualBox:~$ tail /etc/group
scanner:x:128:saned
saned:x:129:
colord:x:130:
geoclue:x:131:
pulse:x:132:
pulse-access:x:133:
gdm:x:134:
lxd:x:135:madmin
madmin:x:1000:
sambashare:x:136:madmin

madmin@madmin-VirtualBox:~$ sudo tail /etc/shadow
nm-openvpn:*:19411:0:99999:7:::
saned:*:19411:0:99999:7:::
colord:*:19411:0:99999:7:::
geoclue:*:19411:0:99999:7:::
pulse:*:19411:0:99999:7:::
gnome-initial-setup:*:19411:0:99999:7:::
hplip:*:19411:0:99999:7:::
gdm:*:19411:0:99999:7:::
madmin:$y$j9T$.fVD7xN.XdRS2nHYXkq2K/$ZrIwXiOKhYFlklgGVfXE7/YVgjxOz6o/KLUSd7nffk3:19480:0:99999:7:::
sshd:*:19480:0:99999:7:::
```
# 2. Управление группами:
## a) создать группу;
### Для начала создадим новых пользователей менеджеров, продвцов и кассиров.
```powershell
madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/manager1 -m manager1

madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/manager2 -m manager2

madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/seller1 -m seller1

madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/seller2 -m seller2

madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/cashier1 -m cashier1

madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/cashier2 -m cashier2
```
### Для каждого отдела создадим свою группу и добавим пользователей
```powershell
madmin@madmin-VirtualBox:~$ sudo groupadd managers

madmin@madmin-VirtualBox:~$ sudo groupadd sellers

madmin@madmin-VirtualBox:~$ sudo groupadd cashiers

madmin@madmin-VirtualBox:~$ tail /etc/group
sambashare:x:136:madmin
manager1:x:1001:
manager2:x:1002:
seller1:x:1003:
seller2:x:1004:
cashier1:x:1005:
cashier2:x:1006:
managers:x:1007:
sellers:x:1008:
cashiers:x:1009:

madmin@madmin-VirtualBox:~$ sudo usermod -a -G managers manager1

madmin@madmin-VirtualBox:~$ sudo usermod -a -G managers manager2

madmin@madmin-VirtualBox:~$ sudo usermod -a -G sellers seller1

madmin@madmin-VirtualBox:~$ sudo usermod -a -G sellers seller2

madmin@madmin-VirtualBox:~$ sudo usermod -a -G cashiers cashier1

madmin@madmin-VirtualBox:~$ sudo usermod -a -G cashiers cashier2

madmin@madmin-VirtualBox:~$ tail /etc/group
sambashare:x:136:madmin
manager1:x:1001:
manager2:x:1002:
seller1:x:1003:
seller2:x:1004:
cashier1:x:1005:
cashier2:x:1006:
managers:x:1007:manager1,manager2
sellers:x:1008:seller1,seller2
cashiers:x:1009:cashier1,cashier2
```
## b) попрактиковаться в смене групп у пользователей;
```powershell
madmin@madmin-VirtualBox:~$ sudo usermod -G "" cashier2

madmin@madmin-VirtualBox:~$ groups cashier2
cashier2 : cashier2

madmin@madmin-VirtualBox:~$ sudo usermod -a -G sellers cashier2

madmin@madmin-VirtualBox:~$ groups cashier2
cashier2 : cashier2 sellers
```
## c) добавить пользователя в группу, не меняя основной;
```powershell
madmin@madmin-VirtualBox:~$ sudo usermod -a -G sellers manager1

madmin@madmin-VirtualBox:~$ groups manager1
manager1 : manager1 managers sellers
```
# d) удалить пользователя из группы.	
```powershell
madmin@madmin-VirtualBox:~$ sudo deluser manager1 sellers
Removing user `manager1' from group `sellers' ...
Done.

madmin@madmin-VirtualBox:~$ groups manager1
manager1 : manager1 managers
```
# 3. Работа с группами.
## a) Создать пользователя с правами суперпользователя. Проверить результат.
```powershell
madmin@madmin-VirtualBox:~$ sudo useradd -s /bin/bash -d /home/sadmin -m sadmin

madmin@madmin-VirtualBox:~$ groups sadmin
sadmin : sadmin

madmin@madmin-VirtualBox:~$ sudo usermod -a -G sudo sadmin

madmin@madmin-VirtualBox:~$ groups sadmin
sadmin : sadmin sudo
```