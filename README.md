
# !!!!! Для изменения value у пина нужно поменять direction на out !!!!!

---

## Включение GPIO-пина:
```
echo 13 > /sys/class/gpio/export
```

---

## Отключение GPIO-пина:
```
echo 13 > /sys/class/gpio/unexport
```

---

## Получение направления GPIO-пина (in/out):
```
cat /sys/class/gpio/gpio(номер пина)/direction
```

---

## Смена направления GPIO-пина (in - вход, out - выход):
```
echo in > /sys/class/gpio/gpio(номер пина)/direction
echo out > /sys/class/gpio/gpio(номер пина)/direction
```

---

## Получение значения GPIO-пина low(0)/high(1):
```
cat /sys/class/gpio/gpio(номер пина)/value
```

---

## Смена значений GPIO-пина (low/high):
```
echo 0 > /sys/class/gpio/gpio(номер пина)/value
echo 1 > /sys/class/gpio/gpio(номер пина)/value
```

---

## Расположение скриптов:
```
coolfan-* ---- /usr/bin
coolfan.service ---- /etc/systemd/system/
```

---

## Управление:
```
systemctl enable coolfan.service - включение
systemctl disable coolfan.service - отключение
systemctl status coolfan - статус
systemctl start coolfan - запуск
systemctl restart coolfan - перезапуск
systemctl stop coolfan - остановка
```

---

## Если служба падает с 203 кодом ошибки:
```
Нужно убедиться что у скриптов coolfan-* стоят права -rwxrwxrwx
Их можно задать следующей командой: chmod 777 /usr/bin/coolfan-*
```
