получаем список сетевых интерфейсов
`ls /sys/class/net`
для настройки wi-fi нужен пакет
`sudo apt install wpasupplicant`
в папке `/etc/netplan` создаём `yaml`  файл
`sudo vi /etc/netplan/02-networkd.yaml`
проводное соединение с динамическим IP 
```
network:  
  version: 2  
  renderer: networkd  
  ethernets:  
    enp3s0:  
      dhcp4: yes
```
проверяем конфигурацию
`sudo netplan --debug generate`
если ошибок нет применяем конфигурацию 
`sudo netplan --debug apply`
wi-fi с динамическим IP 
```
network:
  version: 2
  renderer: networkd
  wifis:
    wlp3s0b1:
      dhcp4: yes
      dhcp6: no
      nameservers:
        addresses: [ 8.8.8.8, 8.8.4.4 ]
      access-points:
        "AccessPoint":
           password: "12345678"
```
сеть со статическим IP, пробелы возле квадратных скобок обязательны
```
network:  
  version: 2  
  renderer: networkd  
  ethernets:  
    enp3s0:  
      dhcp4: no  
      addresses: [ 192.168.1.10/24 ]  
      gateway4: 192.168.1.1  
      nameservers:  
        addresses: [ 8.8.8.8, 8.8.4.4 ]
```
