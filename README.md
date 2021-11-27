# Jarkom-Modul-4-A10-2021

## Perhitungan Pohon IP CISCO VLSM
### Pembagian Subnet

| Subnet      | Jumlah IP | Netmask |
| ----------- | --------- | ------- |
| A1          | 1001      |   /22   |
| A2          | 13        |   /28   | 
| A3          | 502       |   /23   | 
| A4          | 2         |   /30   | 
| A5          | 2         |   /30   | 
| A6          | 2         |   /30   | 
| A7          | 101       |   /25   | 
| A8          | 701       |   /22   | 
| A9          | 2021      |   /21   | 
| A10         | 521       |   /22   | 
| A11         | 2         |   /30   | 
| A12         | 721       |   /22   | 
| A13         | 252       |   /24   | 
| Total       | 5841      |   /19   | 


### Hasil Pembagian Pohon IP


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

### Router
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
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.4.144.2
netmask 255.255.255.252
gateway 10.4.144.1

auto eth1
iface eth1 inet static
address 10.4.136.1
netmask 255.255.255.128

auto eth2
iface eth2 inet static
address 10.4.128.1
netmask 255.255.248.0
```  
  
##### GUANHAO
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.4.32.2
netmask 255.255.255.252
gateway 10.4.32.1

auto eth1
iface eth1 inet static
address 10.4.20.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 10.4.8.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 10.4.16.1
netmask 255.255.254.0
```  
  
Untuk route nya dapat melakukan ```bash route.sh``` dengan route.sh yang berisi sebagai berikut:
```
route add -net 10.4.16.0 netmask 255.255.252.0 gw 10.4.16.3

route add -net 10.4.16.0 netmask 255.255.252.0 gw 10.4.16.2

route add -net 10.4.20.0 netmask 255.255.252.0 gw 10.4.20.2

route add -net 10.4.0.0 netmask 255.255.240.0 gw 10.4.8.2
```  
  
##### OIMO
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.4.8.2
netmask 255.255.255.252
gateway 10.4.8.1

auto eth1
iface eth1 inet static
address 10.4.4.1
netmask 255.255.255.0
```  
  
Untuk route nya dapat melakukan ```bash route.sh``` dengan route.sh yang berisi sebagai berikut:
```
route add -net 10.4.0.0 netmask 255.255.248.0 gw 10.4.4.3

route add -net 10.4.0.0 netmask 255.255.248.0 gw 10.4.4.2
```  
  
##### SEASTONE
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.4.4.2
netmask 255.255.255.0
gateway 10.4.4.1

auto eth1
iface eth1 inet static
address 10.4.0.1
netmask 255.255.252.0
```  
  
##### ALABASTA
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.4.16.2
netmask 255.255.254.0
gateway 10.4.16.1

auto eth1
iface eth1 inet static
address 10.4.18.1
netmask 255.255.255.240
```  
  
### Klien

##### BLUENO
```
auto eth0
iface eth0 inet static
address 10.4.64.2
netmask 255.255.252.0
gateway 10.4.64.1
```

##### CIPHER
```
auto eth0
iface eth0 inet static
address 10.4.160.2
netmask 255.255.252.0
gateway 10.4.160.1
```

##### JIPANGU
```
auto eth0
iface eth0 inet static
address 10.4.136.2
netmask 255.255.255.128
gateway 10.4.136.1
```

##### CALMBELT
```
auto eth0
iface eth0 inet static
address 10.4.128.2
netmask 255.255.248.0
gateway 10.4.128.1
```

##### COURTYARD
```
auto eth0
iface eth0 inet static
address 10.4.128.3
netmask 255.255.248.0
gateway 10.4.128.1
```

##### JABRA
```
auto eth0
iface eth0 inet static
address 10.4.20.2
netmask 255.255.252.0
gateway 10.4.20.1
```

##### ENIESLOBBY
```
auto eth0
iface eth0 inet static
address 10.4.4.3
netmask 255.255.255.0
gateway 10.4.4.1
```

##### ELENA
```
auto eth0
iface eth0 inet static
address 10.4.0.2
netmask 255.255.252.0
gateway 10.4.0.1
```

##### MAINGATE
```
auto eth0
iface eth0 inet static
address 10.4.16.3
netmask 255.255.254.0
gateway 10.4.16.1
```

##### JORGE
```
auto eth0
iface eth0 inet static
address 10.4.18.2
netmask 255.255.255.240
gateway 10.4.18.1
```

