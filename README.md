
# Для изменения value у пина нужно поменять direction на out !!!!!

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

## Получение назначения пина in/out:
```
cat /sys/class/gpio/gpio(номер пина)/direction
```

---

## Смена назначения пина (in - вход, out - выход):
```
echo in > /sys/class/gpio/gpio(номер пина)/direction
echo out > /sys/class/gpio/gpio(номер пина)/direction
```

---

## Получение значения пина low(0)/high(1):
```
cat /sys/class/gpio/gpio(номер пина)/value
```

---

## Смена значений пина (low/high):
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
systemctl start coolfan.service - запуск
systemctl status coolfan.service - статус
systemctl stop coolfan.service - остановка
```
