# 1. Создать каталоги students и mentors в домашней директории, а в них — текстовые файлы students_list.txt и mentors_list.txt соответственно.
```powershell
madmin@madmin-VirtualBox:~$ mkdir students

madmin@madmin-VirtualBox:~$ mkdir mentors
```
# 2. Открыть созданные в п.1 файлы в любом текстовом редакторе и заполнить их (в соответствии с названием) списком Ваших одногруппников и наставников на данном потоке.
```powershell
madmin@madmin-VirtualBox:~$ cd students/

madmin@madmin-VirtualBox:~/students$ nano students_list.txt

madmin@madmin-VirtualBox:~/students$ cd

madmin@madmin-VirtualBox:~$ cd mentors/

madmin@madmin-VirtualBox:~/mentors$ nano mentors_list.txt

madmin@madmin-VirtualBox:~/mentors$ cd
```
# 3. Переместите файл mentors_list.txt в папку students.
```powershell
madmin@madmin-VirtualBox:~$ mv mentors/mentors_list.txt students/
```
# 4. Удалите папку mentors.
```powershell
madmin@madmin-VirtualBox:~$ rmdir mentors/
```
# 5. Переименуйте папку students в students_and_mentors.
```powershell
madmin@madmin-VirtualBox:~$ mv students students_and_mentors
```
# 6. Удалите папку students_and_mentors вместе с содержимым.
```powershell
madmin@madmin-VirtualBox:~$ rm -r students_and_mentors/
```
# 7 *. Создать файл file1 и наполнить его произвольным содержимым. Скопировать его в file2. Создать символическую ссылку file3 на file1. Создать жёсткую ссылку file4 на file1. Посмотреть, какие inode у файлов. Удалить file1. Что стало с остальными созданными файлами? Попробовать вывести их на экран.
## а. Создаем файл file1 и наполняем его произвольным содержимым.
```powershell
madmin@madmin-VirtualBox:~$ echo 'Hello world!' > file1
```
## b. Копируем его в file2. 
```powershell
madmin@madmin-VirtualBox:~$ cp file1 file2
```
## c. Создаем символическую ссылку file3 на file1. 
```powershell
madmin@madmin-VirtualBox:~$ ln -s file1 file3
```
## d. Создаем жёсткую ссылку file4 на file1. 
```powershell
madmin@madmin-VirtualBox:~$ ln file1 file4
```
## e. Посмотреть, какие inode у файлов. 
```powershell
madmin@madmin-VirtualBox:~$ ls -li
total 56
524375 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Desktop
524379 drwxr-xr-x 2 madmin madmin 4096 мая  8 22:37 Documents
524376 drwxr-xr-x 2 madmin madmin 4096 мая  8 23:05 Downloads
529179 -rw-rw-r-- 2 madmin madmin   13 мая  9 16:44 file1
529187 -rw-rw-r-- 1 madmin madmin   13 мая  9 16:44 file2
524335 lrwxrwxrwx 1 madmin madmin    5 мая  9 16:46 file3 -> file1
529179 -rw-rw-r-- 2 madmin madmin   13 мая  9 16:44 file4
529976 drwxrwxr-x 2 madmin madmin 4096 мая  9 16:26 Lesson
524380 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Music
524381 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Pictures
524378 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Public
524455 drwx------ 7 madmin madmin 4096 мая  4 19:59 snap
524377 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Templates
524382 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Videos
```
## f. Удаляем file1. Что стало с остальными созданными файлами? 
```powershell
madmin@madmin-VirtualBox:~$ rm file1

madmin@madmin-VirtualBox:~$ ls -li
total 52
524375 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Desktop
524379 drwxr-xr-x 2 madmin madmin 4096 мая  8 22:37 Documents
524376 drwxr-xr-x 2 madmin madmin 4096 мая  8 23:05 Downloads
529187 -rw-rw-r-- 1 madmin madmin   13 мая  9 16:44 file2
524335 lrwxrwxrwx 1 madmin madmin    5 мая  9 16:46 file3 -> file1
529179 -rw-rw-r-- 1 madmin madmin   13 мая  9 16:44 file4
529976 drwxrwxr-x 2 madmin madmin 4096 мая  9 16:26 Lesson
524380 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Music
524381 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Pictures
524378 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Public
524455 drwx------ 7 madmin madmin 4096 мая  4 19:59 snap
524377 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Templates
524382 drwxr-xr-x 2 madmin madmin 4096 мая  3 20:10 Videos
```
## g. Выводим их на экран.
```powershell
madmin@madmin-VirtualBox:~$ cat file2
Hello world!

madmin@madmin-VirtualBox:~$ cat file3
cat: file3: No such file or directory

madmin@madmin-VirtualBox:~$ cat file4
Hello world!
```
# 8 *. Дать созданным файлам другие, произвольные имена. Создать новую символическую ссылку. Переместить ссылки в другую директорию.
```powershell
madmin@madmin-VirtualBox:~$ echo 'Viva LasVegas' > file1

madmin@madmin-VirtualBox:~$ mv file1 FileUno

madmin@madmin-VirtualBox:~$ mv file2 FileDos

madmin@madmin-VirtualBox:~$ ln -s FileUno FileUno_Link

madmin@madmin-VirtualBox:~$ ln -s FileDos FileDos_Link

madmin@madmin-VirtualBox:~$ mkdir Links

madmin@madmin-VirtualBox:~$ mv *_Link Links/

```