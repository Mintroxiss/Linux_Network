## Part 1. Инструмент ipcalc

Поднимаем виртуальную машину WS1.

### 1.1. Сети и маски

**1) Определить адрес сети 192.167.38.54/13**

Используя команду `ipcalc 192.167.38.54/13` определяем адрес сети: \
![screen_1.1.1](images/screen_1.1.1.png)

Адрес сети: `192.167.38.54`.

**2) Перевести маски 255.255.255.0 в префиксную и двоичную запись, /15 в обычную и двоичную, 11111111.11111111.11111111.11110000 в обычную и префиксную**

С помощью команды `ipcalc 192.167.38.54/255.255.255.0` определяем префиксную и двоичную запись: \
![screen_1.1.2](images/screen_1.1.2.png)

- Префиксная: `/24`
- Двоичная: `11111111.11111111.11111111. 000000000`

Благодаря команде `ipcalc 192.167.38.54/15` определяем обычную и двоичную запись: \
![screen_1.1.3](images/screen_1.1.3.png)

- Обычная: `255.254.0.0`
- Двоичная: `11111111.11111110.00000000. 000000000`

С помощью команды `ipcalc 192.167.38.54/11111111.11111111.11111111.11110000` определяем обычную и префиксную запись: \
![screen_1.1.4](images/screen_1.1.4.png)

Поскольку в `ipcalc` нельзя указывать маску в двоичном представлении, переводим число в обычное представление: \
![screen_1.1.5](images/screen_1.1.5.png)

- Обычная: `255.255.255.240`
- Префиксная: `28`

**3) Определить минимальный и максимальный хост в сети 12.167.38.4 при масках: /8, 11111111.11111111.00000000.00000000, 255.255.254.0 и /4**

Благодаря команде `ipcalc 12.167.38.4/8` находим минимальный и максимальный хост в сети: \
![screen_1.1.6](images/screen_1.1.6.png)

- Минимальный: `12.0.0.1`
- Максимальный: `12.255.255.254`

Преобразуем `11111111.11111111.00000000.00000000` в обыное представление. С помощью команды `12.167.38.4/255.255.0.0` находим минимальный и максимальный хост в сети: \
![screen_1.1.7](images/screen_1.1.7.png)

- Минимальный: `12.167.0.1`
- Максимальный: `12.167.255.254`

Благодаря команде `12.167.38.4/255.255.254.0` находим минимальный и максимальный хост в сети: \
![screen_1.1.8](images/screen_1.1.8.png)

- Минимальный: `12.167.38.1`
- Максимальный: `12.169.39.254`

С помощью команды `12.167.38.4/4` находим минимальный и максимальный хост в сети: \
![screen_1.1.9](images/screen_1.1.9.png)

- Минимальный: `0.0.0.1`
- Максимальный: `15.255.255.254`

### 1.2. localhost

**Определить и записать в отчёт, можно ли обратиться к приложению, работающему на localhost, со следующими IP: 194.34.23.100, 127.0.0.2, 127.1.0.1, 128.0.0.1**

Определяем, можно ли обратиться к приложению или нет, с помощью раздела `Hosts/Net`, в котором при возможности обращения будет выведено `Loopback`.

`ipcalc 194.34.23.100`: \
![screen_1.2.1](images/screen_1.2.1.png)

- Обратиться к приложению с IP `194.34.23.100` нельзя

`ipcalc 127.0.0.2`: \
![screen_1.2.2](images/screen_1.2.2.png)

- Обратиться к приложению с IP `127.0.0.2` можно

`ipcalc 127.1.0.1`: \
![screen_1.2.3](images/screen_1.2.3.png)

- Обратиться к приложению с IP `127.1.0.1` можно

`ipcalc 128.0.0.1`: \
![screen_1.2.4](images/screen_1.2.4.png)

- Обратиться к приложению с IP `128.0.0.1` нельзя

### 1.3. Диапазоны и сегменты сетей

**1) Какие из перечисленных IP можно использовать в качестве публичного, а какие только в качестве частных: 10.0.0.45, 134.43.0.2, 192.168.4.2, 172.20.250.4, 172.0.2.1, 192.172.0.1, 172.68.0.2, 172.16.255.255, 10.10.10.10, 192.169.168.1**

Определяем, какие IP можно использовать только в качестве частных, с помощью раздела `Hosts/Net`, в котором будет указано `Private Internrt`.

`ipcalc 10.0.0.45`: \
![screen_1.3.1](images/screen_1.3.1.png)

- Частный IP

`ipcalc 134.43.0.2`: \
![screen_1.3.2](images/screen_1.3.2.png)

- Публичный IP

`ipcalc 192.168.4.2`: \
![screen_1.3.3](images/screen_1.3.3.png)

- Частный IP

`ipcalc 172.20.250.4`: \
![screen_1.3.4](images/screen_1.3.4.png)

- Частный IP

`ipcalc 172.0.2.1`: \
![screen_1.3.5](images/screen_1.3.5.png)

- Публичный IP

`ipcalc 192.172.0.1`: \
![screen_1.3.6](images/screen_1.3.6.png)

- Публичный IP

`ipcalc 172.68.0.2`: \
![screen_1.3.7](images/screen_1.3.7.png)

- Публичный IP

`ipcalc 172.16.255.255`: \
![screen_1.3.8](images/screen_1.3.8.png)

- Частный IP

`ipcalc 10.10.10.10`: \
![screen_1.3.9](images/screen_1.3.9.png)

- Частный IP

`ipcalc 192.169.168.1`: \
![screen_1.3.10](images/screen_1.3.10.png)

- Публичный IP

**2) Какие из перечисленных IP адресов шлюза возможны у сети 10.10.0.0/18: 10.0.0.1, 10.10.0.2, 10.10.10.10, 10.10.100.1, 10.10.1.255**

Используя команду `ipcalc 10.10.0.0/18` выводим информацию об IP: \
![screen_1.3.11](images/screen_1.3.11.png)

Подходящие IP находятся в диапозоне от минимального IP хоста (`10.10.0.1`) до максимального (`10.10.63.254`).

- Возможные IP: `10.10.0.2`, `10.10.10.10`, `10.10.1.255`


## Part 2. Статическая маршрутизация между двумя машинами

Поднимаем 2-ую виртуальную машину WS2: \
![screen_2.1](images/screen_2.1.png)

В `VirtualBox` заходим в `Settings`, далее в `Network` и меняем режим адаптера на `Internal Network` у обеих машин: \
![screen_2.2](images/screen_2.2.png)

С помощью команды `ip a` смотрим существующие сетевые интерфейсы: \
![screen_2.3](images/screen_2.3.png)
![screen_2.4](images/screen_2.4.png)

**Опиши сетевой интерфейс, соответствующий внутренней сети, на обеих машинах и задать следующие адреса и маски: ws1 - 192.168.100.10, маска /16, ws2 - 172.24.116.8, маска /12.**

С помощью команды `netstat -nr` проверяем адреса машин: \
![screen_2.5](images/screen_2.5.png)
![screen_2.6](images/screen_2.6.png)

Открываем файл с помощью редактора nano командой `sudo nano /etc/netplan/00-installer-config.yaml` на каждой машине, отключаем `dhcp4` и указываем необходимые внутренние IP-адреса: \
![screen_2.7](images/screen_2.7.png)
![screen_2.8](images/screen_2.8.png)

Перезапускаем сервис сети командой `sudo netplan apply` на обоих машинах и проверяем новые IP-адреса командой `ip a`: \
![screen_2.9](images/screen_2.9.png)
![screen_2.10](images/screen_2.10.png)

### 2.1. Добавление статического маршрута вручную

**Добавь статический маршрут от одной машины до другой и обратно при помощи команды вида ip r add**

Добавляем статистический маршрут к `wm2` в `wm1` с помощью команды `sudo ip route add 172.24.116.8 dev enp0s3` и проверяем адреса машин командой `netstat -nr`: \
![screen_2.11](images/screen_2.11.png)

Добавляем статистический маршрут к `wm1` в `wm2` с помощью команды `sudo ip route add 192.168.100.10 dev enp0s3` и проверяем адреса машин командой `netstat -nr`: \
![screen_2.12](images/screen_2.12.png)

Пингуем соединение на `wm1` командой `ping -c 5 172.24.116.8`: \
![screen_2.13](images/screen_2.13.png)

Пингуем соединение на `wm2` командой `ping -c 5 192.168.100.10`: \
![screen_2.14](images/screen_2.14.png)

### 2.2. Добавление статического маршрута с сохранением

Перезапускаем машины командой `ip route`: \
![screen_2.15](images/screen_2.15.png)
![screen_2.16](images/screen_2.16.png)

Открываем конфигурационный файл для редактирования командой `sudo nano /etc/netplan/00-installer-config.yaml` и дописываем нужные строки: \
![screen_2.17](images/screen_2.17.png)
![screen_2.18](images/screen_2.18.png)

Применяем изменения командой `sudo netplan aplly`, после чего пингуем соединение между машинами: \
![screen_2.19](images/screen_2.19.png)
![screen_2.20](images/screen_2.20.png)


## Part 3. Утилита iperf3

### 3.1. Скорость соединения

**Переведи и запиши в отчёт: 8 Mbps в MB/s, 100 MB/s в Kbps, 1 Gbps в Mbps**

- 8 Mbps (мегабит в секунду) = 1 MB/s (мегабайт в секунду)
- 100 MB/s (мегабайт в секунду) = 819200 Kbps (килобит в секунду)
- 1 Gbps (гигабайт в секунду) = 1024 Mbps (мегабит в секунду)

### 3.2. Утилита iperf3

В `VirtualBox` заходим в `Settings`, далее в `Network`, меняем режим адаптера обратно на `NAT` и добавляем 2-ой адаптер `Internal Network` у обеих машин: \
![screen_3.1](images/screen_3.1.png)

Открываем конфигурационный файл для редактирования командой `sudo nano /etc/netplan/00-installer-config.yaml` и дописываем нужные строки: \
![screen_3.2](images/screen_3.2.png)
![screen_3.3](images/screen_3.3.png)

Принимаем изменения командой `sudo netplan apply` и выводим настройки интерфейсов командой `ip a` для проверки: \
![screen_3.4](images/screen_3.4.png)
![screen_3.5](images/screen_3.5.png)

Запускаем утилиту iperf3 на ws1 в режиме сервер командой `iperf -с`: \
![screen_3.6](images/screen_3.6.png)

После запускаем утилиту `iperf3` на `ws2` в режиме сервер командой `iperf -s`: \
![screen_3.7](images/screen_3.7.png)

Далее в выводе на `ws1` появится скорость обмена пакетов.


## Part 4. Сетевой экран

### 4.1. Утилита iptables

Создаем на `wm1` и `wm2` файлы, имитирующие `firewall`, командой `sudo touch /etc/firewall.sh`.

#### Нужно добавить в файл подряд следующие правила:

1) На `ws1` примени стратегию, когда в начале пишется запрещающее правило, а в конце пишется разрешающее правило (это касается пунктов 4 и 5).
2) На `ws2` примени стратегию, когда в начале пишется разрешающее правило, а в конце пишется запрещающее правило (это касается пунктов 4 и 5).
3) Открой на машинах доступ для порта `22` (ssh) и порта `80` (http).
4) Запрети `echo reply` (машина не должна «пинговаться», т.е. должна быть блокировка на OUTPUT).
5) Разреши echo reply (машина должна «пинговаться»). \
![screen_3.8](images/screen_3.8.png)
![screen_3.9](images/screen_3.9.png)

Запускаем файлы на обеих на обеих машинах с помощью команд `chmod +x /etc/firewall.sh` и `sudo bash /etc/firewall.sh`: \
![screen_3.10](images/screen_3.10.png)
![screen_3.11](images/screen_3.11.png)

Разница между стратегиями заключается в том, что `ws1` не сможет пропинговать `ws2`, поскольку очерёдность выполнения правил утилиты `iptables` производится сверху вниз. Поскольку запрет на вывод происходит первее, пингование прекращается. У `wm2` разрешается вывод первее, поэтому она может пропинговать `ws1`.

### 4.2. Утилита nmap

Пингуем машины: \
![screen_3.12](images/screen_4.1.png)
![screen_4.2](images/screen_4.2.png)

В файле `firewall.sh` для `ws1` первым было указано запрещающее правило, поэтому она не пингуется.

Используя команду `sudo nmap 172.24.116.8` на `ws1` проверяем, включен ли хост ws2 (должно вывестись `Host is up`): \
![screen_4.3](images/screen_4.3.png)

Видим, что хост включен.

Для сохранения дампов виртуальных машин открываем меню машин, заходим в `Snapshots`, нажимаем `Take` и добавляем дампы: \
![screen_4.4](images/screen_4.4.png)
![screen_4.5](images/screen_4.5.png)
![screen_4.6](images/screen_4.6.png)


## Part 5. Статическая маршрутизация сети

Необходимо создать сеть по этой схеме: \
![screen_5.1](images/screen_5.1.png)

Поднимаем 5 машин. Создаем машину r1, после чего клонируем её 4 раза и меняем имена хостов командой `sudo hostnamectl set-hostname new_hostname` на соответствующие названия: `r1`, `r2`, `w11`, `w21`, `w22`.

Для машин `r1` и `r2` в VirtualBox заходим в Settings, далее в Network и включаем два адаптера Internal Network, присваивая имена определенным образом: \
![screen_5.2](images/screen_5.2.png)
![screen_5.3](images/screen_5.3.png)

Для машин `w11`, `w21` и `w22` в VirtualBox заходим в Settings, далее в Network и включаем 2-ой адаптер Internal Network, присваивая имена определенным образом: \
![screen_5.4](images/screen_5.4.png)
![screen_5.5](images/screen_5.5.png)
![screen_5.6](images/screen_5.6.png)

Проверяем интерфейсы на всех машинах командой `ip a`.

### 5.1. Настройка адресов машин

Редактируем конфигурационные netplan-файлы благодаря команде `sudo nano /etc/netplan/00-00-installer-config.yaml` и дописываем нужные строки:

`r1`: \
![screen_5.7](images/screen_5.7.png)

`r2`: \
![screen_5.8](images/screen_5.8.png)

`w11`: \
![screen_5.9](images/screen_5.9.png)

`w21`: \
![screen_5.10](images/screen_5.10.png)

`w22`: \
![screen_5.11](images/screen_5.11.png)

Принимаем изменения командой `netplan apply` и проверяем их на корректность командой `ip -4 a`: \
![screen_5.12](images/screen_5.12.png)
![screen_5.13](images/screen_5.13.png)
![screen_5.14](images/screen_5.14.png)
![screen_5.15](images/screen_5.15.png)
![screen_5.16](images/screen_5.16.png)

Пингуем `ws22` c `ws21` командой `ping -c 5 10.20.0.20`: \
![screen_5.17](images/screen_5.17.png)

Также пингуем `r1` с `ws11` командой `ping -c 4 10.10.0.2`: \
![screen_5.18](images/screen_5.18.png)

### 5.2. Включение переадресации IP-адресов

Выполняем команду `sudo sysctl -w net.ipv4.ip_forward=1` на роутерах `r1` и `r2` для включения переадремации IP: \
![screen_5.19](images/screen_5.19.png)
![screen_5.20](images/screen_5.20.png)

Однако в таком случае после перезагрузки переадресация не будет работать. Открываем для редактирования `sysctl`-конфиг командой `sudo nano /etc/sysctl.conf` и раскомменчиваем строку `net.ipv4.ip_forward = 1`: \
![screen_5.21](images/screen_5.21.png)
![screen_5.22](images/screen_5.22.png)

### 5.3. Установка маршрута по-умолчанию

Настраиваем маршрут по-умолчанию (шлюз) для рабочих станций `ws11`, `ws21` и `ws22`. Открываем для редактирования `netplan`-конфиг у каждой машины командой `sudo nano /etc/netplan/00-installer-config.yaml` и дописываем недостающие строки: \
![screen_5.23](images/screen_5.23.png)
![screen_5.24](images/screen_5.24.png)
![screen_5.25](images/screen_5.25.png)

Принимаем изменения командой `sudo netplan apply` и проверяем маршрут командой `ip r`: \
![screen_5.26](images/screen_5.26.png)
![screen_5.27](images/screen_5.27.png)
![screen_5.28](images/screen_5.28.png)

С помощью команды `tcpdump -tn -i enp0s8` на роутере `r2` выводим отправляемые ему пакеты. Пингуем `r2` с машины `ws11`: \
![screen_5.29](images/screen_5.29.png)
![screen_5.30](images/screen_5.30.png)

Наблюдаем, что `r1` получает пакеты, но не может отправить их обратно, поскольку не имеет маршрута.  

### 5.4. Добавление статических маршрутов

Добавляем в роутеры `r1` и `r2` статические маршруты, путем редактирования netplan-конфига командой `sudo nano /etc/netplan/00-installer-config.yaml`.
`r1`: \
![screen_5.31](images/screen_5.31.png)

`r2`: \
![screen_5.32](images/screen_5.32.png)

Принимаем изменения командой `sudo netplan apply` и проверяем маршрут командой `ip r` (строка оканчивается на `proro static`): \
![screen_5.33](images/screen_5.33.png)
![screen_5.34](images/screen_5.34.png)

**Запусти команды на ws11: `ip r list 10.10.0.0/[маска сети]` и `ip r list 0.0.0.0/0`**

На `ws11` вводим команды `ip r list 10.10.0.0/18` и `ip r list 0.0.0.0/0`: \
![screen_5.35](images/screen_5.35.png)

Для адреса `10.10.0.0/18` был выбран маршрут, отличный от `0.0.0.0/0` (он попадает под маршрут по-умолчанию), т.к. машина `ws11` соединена с сетью `10.10.0.0/18` по своему IP-адресу `10.10.0.2`, для других адресов используется маршрут по умолчанию, который указан в файле `10.10.0.1`.

### 5.5. Построение списка маршрутизаторов

Запускаем на `r1` команду дампа: `tcpdump -tnv -i enp0s8` (вывод можно увидеть ниже).

Используемые флаги:
- `-n` - не конвертировать адреса в имена;
- `-t` - не выводить время при выводе каждой строкчи дампа;
- `-v` - выводить более подробную информацию.

При помощи утилиты `traceroute` строим список маршрутизаторов на пути от `ws11` до `ws21`, используя команду `traceroute 10.20.0.10` на `ws11`: \
![screen_5.36](images/screen_5.36.png)

Далее в выводе команды `tcpdump -tnv -i enp0s8` на машине `r1` построится список маршрутизаторов: \
![screen_5.37](images/screen_5.37.png)

- Каждый пакет проходит на своем пути определенное количество узлов, пока достигнет своей цели. Причем, каждый пакет имеет свое время жизни. Это количество узлов, которые может пройти пакет перед тем, как он будет уничтожен. Этот параметр записывается в заголовке `TTL`, каждый маршрутизатор, через который будет проходить пакет уменьшает его на единицу. При `TTL=0` пакет уничтожается, а отправителю отсылается сообщение `Time Exceeded`.
- Команда `traceroute` в `linux` использует `UDP` пакеты. Она отправляет пакет с `TTL=1` и смотрит адрес ответившего узла, дальше `TTL=2`, `TTL=3` и так пока не достигнет цели. Каждый раз отправляется по три пакета и для каждого из них измеряется время прохождения. Пакет отправляется на случайный порт, который, скорее всего, не занят. Когда утилита `traceroute` получает сообщение от целевого узла о том, что порт недоступен трассировка считается завершенной.

### 5.6. Использование протокола ICMP при маршрутизации

Запускаем на `r1` перехват сетевого трафика, проходящего через `enp0s8` с помощью команды `sudo tcpdump -n -i enp0s8 icmp` (изображение вывода будет ниже).

Пингуем несуществующий адрес на `ws11` командой `sudo ping -c 5 10.105.3.111`: \
![screen_5.38](images/screen_5.38.png)

В итоге в выводе `r1` увидим это: \
![screen_5.39](images/screen_5.39.png)

Сохраняем дампы образов виртуальных машин (как в part 4.2): \
![screen_5.40](images/screen_5.40.png)


## Part 6. Динамическая настройка IP с помощью DHCP

**1) Укажи адрес маршрутизатора по-умолчанию, `DNS`-сервер и адрес внутренней сети**

Для маршрутизатора `r2` открываем для редактирования `DHCP`-конфиг командой `sudo nano /etc/dhcp/dhcpd.conf` и указываем адрес маршрутизатора по-умолчанию, DNS-сервер и адрес внутренней сети (дописываем строки): \
![screen_6.1](images/screen_6.1.png)

**2) В файле `resolv.conf` пропиши nameserver `8.8.8.8`**

На роутере `r2` открываем конфиг `/etc/resolv.conf` для редактирования командой `sudo nano /etc/resolv.conf` и редактируем строки: \
![screen_6.2](images/screen_6.2.png)

**3) Перезагрузи службу `DHCP` командой `systemctl restart isc-dhcp-server`. Машину `ws21` перезагрузи при помощи reboot и через ip a покажи, что она получила адрес. Также пропингуй `ws22` с `ws21`**

Перезагружаем службу `DHCP` командой `systemctl restart isc-dhcp-server`: \
![screen_6.3](images/screen_6.3.png)

Открываем для редактирования `netplan`-конфиг командой `sudo nano /etc/netplan/00-installer-config.yaml`на машинах `ws21` и `ws22`, после чего принимаем изменения командой `sudo netplan apply` :\
![screen_6.4](images/screen_6.4.png)
![screen_6.5](images/screen_6.5.png)

Перезагружаем `ws21` командой `sudo systemctl reboot`.

Проверяем присвоенные адреса устройств: \
![screen_6.6](images/screen_6.6.png)
![screen_6.7](images/screen_6.7.png)

Пингуем `ws22` с `ws21` для проверки: \
![screen_6.9](images/screen_6.9.png)

**4) Укажи `MAC` адрес у `ws11`, для этого в `etc/netplan/00-installer-config.yaml` надо добавить строки: `macaddress: 10:10:10:10:10:BA`, `dhcp4: true`**

На машине `ws11` открываем `netplan`-конфиг для редактирования командой `sudo nano /etc/netplan/00-installer-config.yaml`, редактируем строки и применяем изменения командой `sudo netplan apply`: \
![screen_6.10](images/screen_6.10.png)

Выключаем машину `ws11`.

В `VitualBox` заходим в `Settings`, далее в `Network` и для 2-ого адаптера указываем `MAC`-адрес: \
![screen_6.11](images/screen_6.11.png)

**5) Для r1 настрой аналогично r2, но сделай выдачу адресов с жесткой привязкой к MAC-адресу (ws11). Проведи аналогичные тесты**

На роутере `r1` открываем для редактирования `DHCP`-конфиг командой `sudo nano /etc/dhcp/dhcpd.conf` и настраиваем как `r2`, но но выдачу адресов сделаем с жесткой привязкой к `ws11`: \
![screen_6.12](images/screen_6.12.png)

На роутере `r1` открываем конфиг `/etc/resolv.conf` для редактирования командой `sudo nano /etc/resolv.conf` и редактируем строки: \
![screen_6.13](images/screen_6.13.png)

Перезагружаем службу `DHCP` командой `systemctl restart isc-dhcp-server`: \
![screen_6.14](images/screen_6.14.png)

На `ws11` проверяем новый IP командой `ip a`: \
![screen_6.15](images/screen_6.15.png)

Пингуем соединение `ws22` на `ws21` с помощью команды `ping -c 5 10.10.0.4`: \
![screen_6.16](images/screen_6.16.png)

**6) Запроси с ws21 обновление ip адреса**

Проверяем `IP` до обновления командой `ip a`: \
![screen_6.17](images/screen_6.17.png)

Командой `sudo dhclient -v` запрашиваем обновление `IP` у `DHCP`: \
![screen_6.18](images/screen_6.18.png)

- `-v` - выведение дополнительной информации

Перепроверяем `IP` командой `ip a`: \
![screen_6.19](images/screen_6.19.png)

Удаляем старый `IP` командой `sudo dhclient -r`: \
![screen_6.20](images/screen_6.20.png)

- `-r` - явно освобождает текущую аренду ip адреса

В части 6 были использованы следующие опции `DHCP`-протокола:
- option routers `ip-address [, ip-address...];` - адреса шлюзов для клиентской сети. Маршрутизаторы должны быть перечислены в порядке предпочтительности.
- option domain-name-servers `ip-address [, ip-address...];` - Список DNS серверов доступных клиенту. Сервера должны быть перечислены в порядке предпочтительности.

Сохраняем дампы образов виртуальных машин: \
![screen_6.21](images/screen_6.21.png)


## Part 7. NAT

**В файле /etc/apache2/ports.conf на ws22 и r1 измени строку Listen 80 на Listen 0.0.0.0:80, то есть сделай сервер Apache2 общедоступным**

На `ws22` и `r2` открываем конфиг для редактирования командой `sudo nano /etc/apache2/ports.conf` и дописываем нужные строки.

`r2`: \
![screen_7.1](images/screen_7.1.png)

`ws22`: \
![screen_7.2](images/screen_7.2.png)

**Запусти веб-сервер Apache командой service apache2 start на ws22 и r1**

На `ws22` и `r1` Запускаем веб-сервер `Apache` командой `service apache2 start`: \
![screen_7.3](images/screen_7.3.png)
![screen_7.4](images/screen_7.4.png)

**Добавь в фаервол, созданный по аналогии с фаерволом из Части 4, на `r2` следующие правила:**
**1) Удаление правил в таблице `filter` - `iptables -F;`**
**2) Удаление правил в таблице "NAT" - `iptables -F -t nat;`**
**3) Отбрасывать все маршрутизируемые пакеты - `iptables --policy FORWARD DROP`.**

Создаем и открываем файл для редактирования на `r2` командой `sudo nano /etc/firewall.sh` и вписываем нужные строки: \
![screen_7.5](images/screen_7.5.png)

Запускаем файл командами `sudo chmod +x /etc/firewall.sh` и `sudo bash /etc/firewall.sh: \
![screen_7.6](images/screen_7.6.png)

При запуске файла `firewall.sh` с этими правилами, `ws22` не должна "пинговаться" с `r1`: \
![screen_7.7](images/screen_7.7.png)
![screen_7.8](images/screen_7.8.png)

**Добавь в файл ещё одно правило:**
**4) Разрешить маршрутизацию всех пакетов протокола `ICMP`**

Прописываем правило для протокола `icmp` и цепочки `FORWARD` в `r2`. Открываем файл для редактирования командой `sudo nano /etc/firewall.sh` и вписываем нужные строки: \
![screen_7.9](images/screen_7.9.png)

Запускаем файл командами `sudo chmod +x /etc/firewall.sh` и `sudo bash /etc/firewall.sh: \
![screen_7.10](images/screen_7.10.png)

Теперь при запуске файла `firewall.sh` с этими правилами, `ws22` должна "пинговаться" с `r1`.

Проверяем соединение между `r1` и `ws22`: \
![screen_7.11](images/screen_7.11.png)
![screen_7.12](images/screen_7.12.png)

**Добавь в файл ещё два правила:**
**5) Включи `SNAT`, а именно маскирование всех локальных `ip` из локальной сети, находящейся за `r2` (по обозначениям из Части 5 - сеть 10.20.0.0)**
**6) Включи `DNAT` на `8080` порт машины `r2` и добавить к веб-серверу `Apache`, запущенному на `ws22`, доступ извне сети**

На роутере `r2` открываем `firewall.sh` для редактирования командой `sudo nano /etc/firewall.sh` и вписываем нужные строки: \
![screen_7.13](images/screen_7.13.png)

Используемые опции:
- `-t` - указывает на используемую таблицу;
- `-p` - указывает протокол, такие как tcp, udp, udplite и другие, поддерживаемые системой, ознакомиться со списком можно в файле `/etc/protocols`;
- `-m` - подключает указанный модуль;
- `-s` - указывает адрес источника пакета, в качестве значения можно указать как один IP-адрес, так и диапазон;
- `-i` - задает входящий сетевой интерфейс;
- `-o` - указывает исходящий сетевой интерфейс;
- `--dport` - порт получателя пакета;
- `DNAT` — подменяет адрес получателя в заголовке `IP`-пакета, основное применение — предоставление доступа к сервисам снаружи, находящимся внутри сети;
- `SNAT` — служит для преобразования сетевых адресов, применимо, когда за сервером находятся машины, которым необходимо предоставить доступ в Интернет, при этом от провайдера имеется статический IP-адрес.

Запускаем файл также, как в Части 4. Перед тестированием отключаем сетевой интерфейс `NAT` в VirtualBox: \
![screen_7.14](images/screen_7.14.png)

Проверяем соединение по `TCP` для `SNAT`, для этого с `ws22` подключаемся к серверу `Apache` на `r1` командой `telnet 10.100.0.11 80`: \
![screen_7.15](images/screen_7.15.png)

Проверить подмену `IP`-адреса можно с помощью команды `tcpdump` - пингуем с машины `ws22` роутер `r1`, в выводе `tcpdump` будет отображаться с какого адреса идет запрос - `IP`-адрес `r2`: \
![screen_7.16](images/screen_7.16.png)
![screen_7.17](images/screen_7.17.png)

Проверяем соединение по `TCP` для `DNAT`. Для этого с `r1` подключаемся к серверу `Apache` на `ws22` (обращаемся по адресу `r2` и порту `8080`): \
![screen_7.18](images/screen_7.18.png)

Для этой проверки отключаем на `ws22` автоматическую выдачу `ip` командой `sudo tcpdump -i enp0s8`: \
![screen_7.19](images/screen_7.19.png)

Сохраняем дампы в `VirtualBox`: \
![screen_7.20](images/screen_7.20.png)


## Part 8. Дополнительно. Знакомство с SSH Tunnels

На `r2` запускаем `firewall.sh` командами `sudo chmod +x /etc/firewall.sh` и `sudo bash /etc/firewall.sh`: \
![screen_7.13](images/screen_7.13.png)
![screen_7.14](images/screen_7.14.png)

Запускаем `Apache` на `ws22`. В конфиге `/etc/apache2/ports.conf` меняем строку `Listen 80` на `Listen localhost:80`: \
![screen_8.1](images/screen_8.1.png)

Используем `Local TCP forwarding` с `ws21` до `ws22`, чтобы получить доступ к веб-серверу на `ws22` с `ws21`: \
![screen_8.2](images/screen_8.2.png)

Используем `Remote TCP forwarding` c `ws11` до `ws22`, чтобы получить доступ к веб-серверу на `ws22` с `ws11`: \
![screen_8.3](images/screen_8.3.png)

Проверяем, сработало ли подключение. Переходим во 2-ой терминал (в терминале машины `ws11` нажимаем `Alt` + `F2`) и выполяем команду `telnet 127.0.0.1 8080`. В момент выполнения данной команды нажимаем любую клавишу: \
![screen_8.4](images/screen_8.4.png)

Сохраняем дампы образов виртуальных маштн в `VirtualBox`: \
![screen_8.5](images/screen_8.5.png)


