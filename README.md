# Jarkom-Modul-4-A10-2021

## Perhitungan Pohon IP GNS3 CIDR
### Penggabungan subnet
![a](https://imgur.com/ThUivSB.png)
![b](https://imgur.com/kgF6ZOt.png)
![c](https://imgur.com/qerxpKh.png)
![d](https://imgur.com/8oKQnnx.png)
![e](https://imgur.com/1oNf5mo.png)
![f](https://imgur.com/qCKhqgF.png)
![g](https://imgur.com/qqT0GRZ.png)
### Pohon pembagian IP
![pohoncidr](https://imgur.com/a3jsjKY.png)
### Config pada GNS3
Pada semua node SELAIN ROUTER FOOSHA dilakukan ```echo nameserver 192.168.122.1 > /etc/resolv.conf```
#### Router
Pada semua router dilakukan ```nano /etc/sysctl.conf``` lalu uncommand ```net.ipv4.ip_forward=1```
##### FOOSHA
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 10.4.64.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 10.4.192.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 10.4.32.1
netmask 255.255.255.252
```
Lakukan command berikut pada router FOOSHA : ```iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.4.0.0/16```  

Untuk route nya dapat melakukan ```bash route.sh``` dengan route.sh yang berisi sebagai berikut:
```
route add -net 10.4.64.0 netmask 255.255.252.0 gw 10.4.64.2

route add -net 10.4.128.0 netmask 255.255.128.0 gw 10.4.192.2

route add -net 10.4.0.0 netmask 255.255.192.0 gw 10.4.32.2  
```  
  
##### WATER7
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.4.192.2
netmask 255.255.255.252
gateway 10.4.192.1

auto eth1
iface eth1 inet static
address 10.4.160.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 10.4.144.1
netmask 255.255.255.252
```

Untuk route nya dapat melakukan ```bash route.sh``` dengan route.sh yang berisi sebagai berikut:
```
route add -net 10.4.160.0 netmask 255.255.252.0 gw 10.4.160.2

route add -net 10.4.128.0 netmask 255.255.224.0 gw 10.4.144.2
```  
  
##### PUCCI
```
```
##### GUANHAO
##### OIMO
##### SEASTONE
##### ALABASTA
#### Klien
##### BLUENO
##### CALMBELT
##### CIPHER
##### COURTYARD
##### ELENA
##### ENIESLOBBY
##### JABRA
##### JIPANGU
##### JORGE
##### MAINGATE
