# Домашнее задание к занятию 14 «Средство визуализации Grafana»

## Обязательные задания

### Задание 1

![Img](https://i.imgur.com/SAB5vTt.png)


### Задание 2
1.Утилизация CPU для nodeexporter (в процентах, 100-idle):
```
100 - (avg by (instance) (rate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[1m])) * 100)
```
2.CPULA 1/5/15:
```
count without (cpu) (rate(node_cpu_seconds_total{job="nodeexporter", mode="system"}[1m])) * on (instance) group_left(node_load1) node_load1
```
```
count without (cpu) (rate(node_cpu_seconds_total{job="nodeexporter", mode="system"}[5m])) * on (instance) group_left(node_load5) node_load5
```
```
count without (cpu) (rate(node_cpu_seconds_total{job="nodeexporter", mode="system"}[15m])) * on (instance) group_left(node_load15) node_load15
```
3.Количество свободной оперативной памяти:
```
node_memory_MemFree_bytes{job="nodeexporter"}
```
4.Количество места на файловой системе:
```
node_filesystem_avail_bytes{job="nodeexporter", mountpoint="/"}
```
![Img](https://i.imgur.com/XoZPiWd.png)

### Задание 3

Alerts
![Img](https://i.imgur.com/Ljx5AYy.png)
![Img](https://i.imgur.com/LvPLSn9.png)

### Задание 4

[JSON](./JSON.json)