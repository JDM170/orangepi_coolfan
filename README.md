# Скрипт управления вентилятором охлаждения для OrangePi
Протестировано на OrangePi PC с Armbian Buster
---
## Требования:
wiringOP: <https://github.com/orangepi-xunlong/wiringOP>
---
## Установка:
- Клонировать репозиторий:
```git clone https://github.com/JDM170/orangepi_coolfan.git```
- Перейти в директорию репозитория:
```cd orangepi_coolfan```
- Скопировать скрипты:
```cp coolfan-control /usr/bin```
```cp coolfan-stop /usr/bin```
```cp coolfan.service /etc/systemd/system```
- Активировать и запустить службу:
```systemctl enable coolfan.service```
```systemctl start coolfan```
---
## Управление:
Управление службой производится следующими командами:
- Узнать состояние: ```systemctl status coolfan```
- Запустить службу: ```systemctl start coolfan```
- Перезапустить службу: ```systemctl restart coolfan```
- Остановить службу: ```systemctl stop coolfan```
---
## Если служба завершается с кодом 203:
- Убеждаемся что у ```coolfan-control``` и ```coolfan-stop``` стоят права ```-rwxrwxrwx```
- Узнать можно их следующим способом:
```ls -la /usr/bin | grep coolfan```
- Если права не совпадают, то нужно обновить их следующей командой:
```chmod 777 /usr/bin/coolfan-control```
```chmod 777 /usr/bin/coolfan-stop```
