## Небольшой мануал по командам на чистом bash
---
Включение GPIO-порта:
```
echo <номер порта> > /sys/class/gpio/export
```
---
Отключение GPIO-порта:
```
echo <номер порта> > /sys/class/gpio/unexport
```
---
Получение направления GPIO-порта (in/out):
```
cat /sys/class/gpio/gpio<номер порта>/direction
```
---
Смена направления GPIO-порта (in - вход, out - выход):
```
echo in > /sys/class/gpio/gpio<номер порта>/direction
echo out > /sys/class/gpio/gpio<номер порта>/direction
```
---
Получение значения GPIO-порта low(0)/high(1):
```
cat /sys/class/gpio/gpio<номер порта>/value
```
---
Смена значений GPIO-порта (low/high):
Для смены значения порта нужно поменять его direction на out
```
echo 0 > /sys/class/gpio/gpio<номер порта>/value
echo 1 > /sys/class/gpio/gpio<номер порта>/value
```
---

В моем случае, скрипт не активировал GPIO-порт, поэтому была использована wiringOP
