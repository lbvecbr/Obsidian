```
sudo apt-get update;\
sudo apt-get install -y vim mosh tmux htop git curl wget unzip zip gcc build-essential make
```
On remote machine enable www login, disable SSH login by password -just keys
```sudo vim /etc/ssh/sshd_config
      AllowUsers www root
      PermitRootLogin no
      PasswordAuthentication no
```
`sudo service ssh restart`
`sudo passwd www`
`www` здесь имя пользователя 
