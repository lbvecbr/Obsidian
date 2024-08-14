`useradd dimon`
`passwd dimon`
`mkdir /home/dimon`
`useradd dimon -m -d /home/dimon -k /home/exsample -s /bin/bash`

`adduser dimon`
более автоматизированное создание пользователя  `/etc/skel`
`usermod` измен параметров пользователя 
`userdel -r dimon` удалить пользователя

`/etc/passwd` файл пользователи и группы
`/etc/nsswitch.conf` список источников данных о пользователях и группах 

