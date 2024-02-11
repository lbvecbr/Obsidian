###### Virtualenv входит в Python с версии 3.4
###### Установка virtualenvwrapper
Windows
```
pip install virtualenvwrapper
```
MacOS / Linux
```
pip install --user virtualenvwrapper
```
 Затем дайте Bash загрузить virtualenvwrapper автоматически
```
echo "source virtualenvwrapper.sh" >> ~/.bashrc
```
```
source ~/.bashrc
```
###### Создать новую среду
MacOS/Linux:
```
mkvirtualenv --python=python3.6 superlists
```
Windows:
```
mkvirtualenv --python=`py -3.6 -c"import sys; print(sys.executable)"` 
superlists
```
(небольшой трюк, чтобы убедиться, что у нас virtualenv в версии python 3.6)

###### Активация среды
```
workon superlists
```
###### Деактивация
```
deactivate
```

