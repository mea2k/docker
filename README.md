# docker

## Задание 1

1. Загрузите образ busybox последней версии

`docker pull busybox`

2. Запустите новый контейнер busybox с командой ping сайта netology.ru, и количеством пингов 7, поименуйте контейнер pinger

`docker run --name pinger -it busybox ping netology.ru`

3. Выведите список всех контейнеров - запущенных и остановленных
```
docker ps -a
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS        PORTS     NAMES
851820bc03cc   busybox   "ping netology.ru"   3 seconds ago   Up 1 second             pinger
```
После остановки:
```
docker ps -a
CONTAINER ID   IMAGE     COMMAND              CREATED          STATUS                     PORTS     NAMES
851820bc03cc   busybox   "ping netology.ru"   15 seconds ago   Exited (0) 3 seconds ago             pinger
```
4. Выведите на экран логи контейнера с именем pinger
```
docker logs pinger
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=62 time=23.370 ms
64 bytes from 188.114.99.224: seq=1 ttl=62 time=23.191 ms
64 bytes from 188.114.99.224: seq=2 ttl=62 time=25.486 ms
64 bytes from 188.114.99.224: seq=3 ttl=62 time=23.529 ms
64 bytes from 188.114.99.224: seq=4 ttl=62 time=22.581 ms
64 bytes from 188.114.99.224: seq=5 ttl=62 time=22.628 ms
64 bytes from 188.114.99.224: seq=6 ttl=62 time=25.279 ms
64 bytes from 188.114.99.224: seq=7 ttl=62 time=26.037 ms
64 bytes from 188.114.99.224: seq=8 ttl=62 time=27.976 ms
64 bytes from 188.114.99.224: seq=9 ttl=62 time=24.682 ms
^C
--- netology.ru ping statistics ---
10 packets transmitted, 10 packets received, 0% packet loss
round-trip min/avg/max = 22.581/24.475/27.976 ms
```
5. Запустите второй раз контейнера с именем pinger

`docker start --name pinger`

Остановка контейнера

`docker stop pinger`

6. Выведите список всех контейнеров - запущенных и остановленных
```
docker ps -a
CONTAINER ID   IMAGE     COMMAND              CREATED              STATUS         PORTS     NAMES
851820bc03cc   busybox   "ping netology.ru"   About a minute ago   Up 5 seconds             pinger
```
После остановки:
```
docker ps -a
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS                       PORTS     NAMES
851820bc03cc   busybox   "ping netology.ru"   2 minutes ago   Exited (137) 2 seconds ago             pinger
```
7. Выведите на экран логи контейнера с именем pinger
```
docker logs pinger
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=62 time=23.370 ms
64 bytes from 188.114.99.224: seq=1 ttl=62 time=23.191 ms
64 bytes from 188.114.99.224: seq=2 ttl=62 time=25.486 ms
64 bytes from 188.114.99.224: seq=3 ttl=62 time=23.529 ms
64 bytes from 188.114.99.224: seq=4 ttl=62 time=22.581 ms
64 bytes from 188.114.99.224: seq=5 ttl=62 time=22.628 ms
64 bytes from 188.114.99.224: seq=6 ttl=62 time=25.279 ms
64 bytes from 188.114.99.224: seq=7 ttl=62 time=26.037 ms
64 bytes from 188.114.99.224: seq=8 ttl=62 time=27.976 ms
64 bytes from 188.114.99.224: seq=9 ttl=62 time=24.682 ms
^C
--- netology.ru ping statistics ---
10 packets transmitted, 10 packets received, 0% packet loss
round-trip min/avg/max = 22.581/24.475/27.976 ms
PING netology.ru (188.114.99.224): 56 data bytes
64 bytes from 188.114.99.224: seq=0 ttl=62 time=22.666 ms
64 bytes from 188.114.99.224: seq=1 ttl=62 time=27.519 ms
64 bytes from 188.114.99.224: seq=2 ttl=62 time=26.531 ms
64 bytes from 188.114.99.224: seq=3 ttl=62 time=27.907 ms
64 bytes from 188.114.99.224: seq=4 ttl=62 time=27.783 ms
64 bytes from 188.114.99.224: seq=5 ttl=62 time=24.108 ms
64 bytes from 188.114.99.224: seq=6 ttl=62 time=28.123 ms
64 bytes from 188.114.99.224: seq=7 ttl=62 time=28.585 ms
64 bytes from 188.114.99.224: seq=8 ttl=62 time=28.013 ms
64 bytes from 188.114.99.224: seq=9 ttl=62 time=24.993 ms
64 bytes from 188.114.99.224: seq=10 ttl=62 time=26.318 ms
64 bytes from 188.114.99.224: seq=11 ttl=62 time=25.736 ms
64 bytes from 188.114.99.224: seq=12 ttl=62 time=26.126 ms
64 bytes from 188.114.99.224: seq=13 ttl=62 time=25.689 ms
64 bytes from 188.114.99.224: seq=14 ttl=62 time=26.231 ms
64 bytes from 188.114.99.224: seq=15 ttl=62 time=28.257 ms
64 bytes from 188.114.99.224: seq=16 ttl=62 time=26.267 ms
64 bytes from 188.114.99.224: seq=17 ttl=62 time=25.500 ms
64 bytes from 188.114.99.224: seq=18 ttl=62 time=28.143 ms
64 bytes from 188.114.99.224: seq=19 ttl=62 time=27.958 ms
64 bytes from 188.114.99.224: seq=20 ttl=62 time=28.105 ms
64 bytes from 188.114.99.224: seq=21 ttl=62 time=27.955 ms
64 bytes from 188.114.99.224: seq=22 ttl=62 time=27.890 ms
64 bytes from 188.114.99.224: seq=23 ttl=62 time=24.795 ms
```
8. Определите по логам общее количество запусков команды ping и какое общее количество отправленых запросов

В первый запуск было 10 пакетов, во второй - 24 - итого 34 пакета.

9. Удалите контейнер с именем pinger

`docker rm pinger`

10. Удалите образ busybox
```
docker rmi busybox
Untagged: busybox:latest
Untagged: busybox@sha256:b5d6fe0712636ceb7430189de28819e195e8966372edfc2d9409d79402a0dc16
Deleted: sha256:7cfbbec8963d8f13e6c70416d6592e1cc10f47a348131290a55d43c3acab3fb9
Deleted: sha256:baacf561cfff825708763ce7ee4a18293716c533e6ece3bd39009a5fb3c804d2
```
