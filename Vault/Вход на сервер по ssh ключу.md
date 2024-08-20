На клиенте
`ssh-keygen`
`ssh-copy-id dimon@192.168.0.180`

На сервере для безопасности отключаем вход по паролю
`sudo vim /etc/ssh/sshd_config`
`Passwordauthetification yes/no`

`Permitrootlogin no`


`sudo service ssh restart`
``