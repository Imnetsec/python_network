# Python Работа с сетью
## Задание 1
Просканируйте с помошью Python ВМ Metasploitable. Определите установленные службы (нужно вывести название и версию службы, номер порта.)

### Решение

import nmap3
import json
from pprint import pprint

nmap_v = nmap3.Nmap() 
result_v = nmap_v.nmap_version_detection("10.0.0.7") 
pprint(result_v) 

## Задание 2
Попробуйте повторить сканирование Wi-Fi, приведенное в лекции.

### Решение

import pywifi
import time

wifi = pywifi.PyWiFi()
iface = wifi.interfaces()[0]

iface.scan()
time.sleep(5)

result = iface.scan.results()
print("Networks:")

for i in range(len(result)):
    print(result[i].ssid, result[i].bssid, result[i].auth, result[i].akm)

