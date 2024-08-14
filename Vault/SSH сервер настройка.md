`pacman -S openssh`
`sudo systemctl start sshd`
Добавить в автозапуск
`sudo systemctl enable sshd`
Если нужно, открыть порт в фаерволе
`sudo ufw allow 22/tcp`
Узнать IP адрес сервера
`ip addr show`
Заходим на сервер
`ssh dimon@192.168.0.180`
