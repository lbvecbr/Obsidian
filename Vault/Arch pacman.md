`pacman -Q` список установленных пакетов 
`pacman -Qe` только пользовательские 
`pacman -Ss` поиск пакета для установки 
`pacman -S`  установка пакета
`pacman -Sy` обновление репозиториев 
`pacman -Sy` `python` обновление-установка 

`pacman -Fy` построение индексов для 
режима файлы `-F` , делается один раз

`pacman -Fl python` посмотреть какие файлы были установлены в систему 

`pacman -Qo python` узнать к какому пакету принадлежит этот файл 
`/usr/bin/python is owned by python3.11.8-1`

`pacman -Su` обновление пакета 
`pacman  -Syu python` обновить репозитории-пакет
`pacman -Syu` обновить систему 
`pacman -R python` удалить пакет 
`pacman -Qdtq` неиспользуемые зависимости 
`pacman -R $(pacman -Qdtq)` удалить неиспользуемые зависимости 
`pacman -Ss` доступные в репозитории пакеты 
`pacman -Ssq` вывод без описания 

https://youtu.be/qSdu6Mqgur4?si=JE_vl0iA18-oIVpc