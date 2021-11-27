# Jarkom-Modul-4-A10-2021

## Perhitungan Pohon IP CISCO VLSM
### Pembagian Subnet
#### Pertama yang perlu kita lakukan adalah pembagian subnet seperti dibawah ini. Untuk penentuan A1, A2 ... dan seterusnya bisa diambil secara bebas namun nanti akan menghasilkan ip yang sama. 

![a](https://imgur.com/ThUivSB.png)

#### Kedua kita perlu memperhatikan hasil yang sudah kita dapatkan diatas dan dibuat tabel untuk mempermudah menghitung pohon. 

Note : Cara menghitungnya adalah sebagai berikut :

Blueno Memiliki 1000 setelah itu ditambah dengan jumlah router yaitu 1 sehingga subnet A1 = 1000+1 begitupun seterusnya sehingga didapatkan A1 = 1001


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
#### Ketiga Membuat gambar Pohon IP setelah kita mendapatkan tabel diatas kita harus membuat dalam bentuk pohon sehingga mempermudah untuk pembagian IP serta mempermudah memperhitungan ip-ip apa saja yang didapatkan.

![images](https://github.com/Fitrah1812/Jarkom-Modul-4-A10-2021/blob/main/Dokumentasi/pohonIp.jpeg)

#### Keempat selanjutnya pembagian pohon ip diatas diletakkan di dalam tabel sehingga mempermudah routing di cisco packet tracer untuk mengenali setiap nodenya

Cara perhitungannya yaitu kita melihat netmask yang available setelah itu kita turunkan pohonnya dan ambil ip yang sesuai

| Subnet      | Jumlah IP | Netmask |     IP       |  Subnet Mask    |
| ----------- | --------- | ------- | ------------ | --------------- |
| A1          | 1001      |   /22   |  10.4.8.0    | 255.255.252.0   |
| A2          | 13        |   /28   |  10.4.27.128 | 255.255.255.240 |
| A3          | 502       |   /23   |  10.4.24.0   | 255.255.254.0   |
| A4          | 2         |   /30   |  10.4.27.144 | 255.255.255.252 |
| A5          | 2         |   /30   |  10.4.27.148 | 255.255.255.252 |
| A6          | 2         |   /30   |  10.4.27.152 | 255.255.255.252 |
| A7          | 101       |   /25   |  10.4.27.0   | 255.255.255.128 |
| A8          | 701       |   /22   |  10.4.12.0   | 255.255.252.0   |
| A9          | 2021      |   /21   |  10.4.0.0    | 255.255.248.0   |
| A10         | 521       |   /22   |  10.4.16.0   | 255.255.252.0   |
| A11         | 2         |   /30   |  10.4.27.156 | 255.255.255.252 |
| A12         | 721       |   /22   |  10.4.20.0   | 255.255.252.0   |
| A13         | 252       |   /24   |  10.4.26.0   | 255.255.255.0   |
| Total       | 5841      |   /19   |              | 255.255.224.0   |

#### Kelima sesudah kita mendapatkan data diatas, selanjutnya kita harus melakukan routing di cisco packet tracernya

Kita akan membuat rangkaiannya terlebih dahulu di Cisco Packet Tracer. Seperti dibawah  ini : 

![images](https://github.com/Fitrah1812/Jarkom-Modul-4-A10-2021/blob/main/Dokumentasi/Gambar_cisco/gambar.jpeg)

#### Keenam setelah kita membuat rangkaian serperti diatas kita akan menghubungkan setiap node yang sudah kita dapatkan ip nya diatas, dengan perhitungan apabila dari router dihitung 1 sedangkan klien dihitung 2. Untuk contohnya di A8 dengan ip 10.4.12.0 jadi dari water7 ipnya 10.4.12.1 sedangkan ip dari cipher 10.4.12.2 dengan default gateway mengarahkan ke ip water7 apabila paket ingin keluar ke tempat lain.

![iamges](https://github.com/Fitrah1812/Jarkom-Modul-4-A10-2021/blob/main/Dokumentasi/Gambar_cisco/router.jpeg)

#### Ketujuh kita perlu lakukan pengenalan setiap node bahwa paket akan melewati router tersebut

![images](https://github.com/Fitrah1812/Jarkom-Modul-4-A10-2021/blob/main/Dokumentasi/Gambar_cisco/static.jpeg)

#### Kedelapan kita harus testing ping apabila routing sudah terhubung semua

On Progress

![images](https://github.com/Fitrah1812/Jarkom-Modul-4-A10-2021/blob/main/Dokumentasi/Gambar_cisco/onprogress.jpeg)

Succesful

![images](https://github.com/Fitrah1812/Jarkom-Modul-4-A10-2021/blob/main/Dokumentasi/Gambar_cisco/sukses.jpeg)

Apabila sudah sukses maka akan muncul succesful sehingga ping berhasil

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
![tabelcidr1](https://imgur.com/yQUjlNK.png)
![tabelcidr2](https://imgur.com/FqSZKUb.png)  
  
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

