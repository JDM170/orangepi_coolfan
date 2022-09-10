## Небольшой мануал по командам wiringOP
---
## Требования чтобы скрипт работал:
wiringOP: <https://github.com/orangepi-xunlong/wiringOP>
---
Включение GPIO-порта:
```
gpio export <номер порта> <in/out>
```
---
Отключение GPIO-порта:
```
gpio unexport <номер порта>
```
---
Смена направления GPIO-порта (in - вход, out - выход):
```
gpio mode <номер порта> <in/out>
```
---
Получение значения GPIO-порта low(0)/high(1):
```
gpio read <номер порта>
```
---
Смена значений GPIO-порта (low/high):
Для смены значения порта нужно поменять его direction на out
```
gpio write <номер порта> <0/1>
```
