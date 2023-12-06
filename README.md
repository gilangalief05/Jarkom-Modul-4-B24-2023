# Jarkom-Modul-4-B24-2023

## Laporan Resmi Modul 4 Kelompok B24 (Subnetting & Routing)

### Anggota kelompok:

| Nama                | NRP        |
| ------------------- | ---------- |
| Gilang Aliefidanto  | 5025211119 |
| Vito Febrian Ananta | 5025211224 |

## Soal

### Topologi

![soal-topologi](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/23439c57-d7b9-40f9-9544-5c8af603629f)

## Pengerjaan

### Prefix IP

Prefix IP B24: 192.190.x.x

### VLSM (CPT)
Pada cara VLSM, kami menyesuaikan IP dan subnet mask sesuai tabel dengan IP yang dapat digunakan. Berikut tabel subnet mask
[resource/list-netmask.png](https://github.com/gilangalief05/Jarkom-Modul-4-B24-2023/blob/9f90a86f7b24223592f638701aea46872ea6d39b/resource/list-netmask.png)

#### Menambahkan rute
- Tabel rute
  | Nama subnet | Rute                                     | Jumlah IP | Netmask |
  | ----------- | ---------------------------------------- | --------- | ------- |
  | A1 | Aura-Frieren | 2 | /30 |
  | A2 | Frieren-Switch3-LakeKorridor | 25 | /27 |
  | A3 | Frieren-Flamme | 2 | /30 |
  | A4 | Flamme-Fern | 2 | /30 |
  | A5 | Fern-Switch4-AppetitRegion-Switch4-LaubHills | 1023 | /21 |
  | A6 | Flamme-Switch5-RohrRoad | 1001 | /22 |
  | A7 | Flamme-Himmel | 2 | /30 |
  | A8 | Himmel-Switch6-SchwerMountains | 6 | /29 |
  | A9 | Aura-Denken | 2 | /30 |
  | A10 | Denken-Switch2-Royal-Capital-Switch2-WilleRegion | 127 | /24 |
  | A11 | Aura-Eisen | 2 | /30 |
  | A12 | Eisen-Switch0-Stark | 2 | /30 |
  | A13 | Eisen-Switch1-Richter-Switch1-Revolte | 3 | /29 |
  | A14 | Eisen-Lugner | 2 | /30 |
  | A15 | Lugner-Switch9-GrobeForest | 251 | /24 |
  | A16 | Lugner-Switch10-TurkRegion | 1001 | /22 |
  | A17 | Eisen-Linie | 2 | /30 |
  | A18 | Linie-Switch11-GranzChannel | 255 | /23 |
  | A19 | Linie-Lawine | 2 | /30 |
  | A20 | Lawine-Switch7-BredtRegion-Switch7-Heiter | 31 | /26 |
  | A21 | Heiter-Switch8-Sein-Switch8-RiegelCanyon | 512 | /22 |

- Tree VLSM
  [[gambar tree vlsm]](https://github.com/gilangalief05/Jarkom-Modul-4-B24-2023/blob/9f90a86f7b24223592f638701aea46872ea6d39b/resource/B24-tree-VLSM.png)
  [[resource/B24-CPT-VLSM.png]](https://github.com/gilangalief05/Jarkom-Modul-4-B24-2023/blob/9f90a86f7b24223592f638701aea46872ea6d39b/resource/B24-CPT-VLSM.png)

- Pembagian IP (VLSM)
  | Nama subnet | Network ID         | Netmask            | Netmask            |
  | ----------- | ------------------ | ------------------ | ------------------ |
  | A1 | 192.190.0.40 | 255.255.255.252 | 192.190.0.43 |
  | A2 | 192.190.0.128 | 255.255.255.224 | 192.190.0.159 |
  | A3 | 192.190.0.32 | 255.255.255.252 | 192.190.0.35 |
  | A4 | 192.190.0.28 | 255.255.255.252 | 192.190.0.31 |
  | A5 | 192.190.16.0 | 255.255.248.0 | 192.190.23.255 |
  | A6 | 192.190.12.0 | 255.255.252.0 | 192.190.15.255 |
  | A7 | 192.190.0.24 | 255.255.255.252 | 192.190.0.27 |
  | A8 | 192.190.0.56 | 255.255.255.248 | 192.190.0.63 |
  | A9 | 192.190.0.20 | 255.255.255.252 | 192.190.0.23 |
  | A10 | 192.190.2.0 | 255.255.255.0 | 192.190.2.255 |
  | A11 | 192.190.0.16 | 255.255.255.252 | 192.190.0.19 |
  | A12 | 192.190.0.12 | 255.255.255.252 | 192.190.0.15 |
  | A13 | 192.190.0.48 | 255.255.255.248 | 192.190.0.55 |
  | A14 | 192.190.0.8 | 255.255.255.252 | 192.190.0.11 |
  | A15 | 192.190.1.0 | 255.255.255.0 | 192.190.1.255 |
  | A16 | 192.190.8.0 | 255.255.252.0 | 192.190.11.255 |
  | A17 | 192.190.0.4 | 255.255.255.252 | 192.190.0.7 |
  | A18 | 192.190.24.0 | 255.255.254.0 | 192.190.25.255 |
  | A19 | 192.190.0.0 | 255.255.255.252 | 192.190.0.3 |
  | A20 | 192.190.0.64 | 255.255.255.192 | 192.190.0.127 |
  | A21 | 192.190.4.0 | 255.255.252.0 | 192.190.7.255 |


### CIDR (GNS3)

- Subnetting

  - Tingkat A
    ![Subnet Tingkat A](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/84b5073e-909e-4aba-b632-316e3b17a5a8)

  - Tingkat B
    ![Subnet Tingkat B](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/ac1d651e-54bd-4c57-a93b-9545ec0fcb69)

  - Tingkat C
    ![Subnet Tingkat C](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/eabf019c-e643-4136-abc2-cce7763429fb)

  - Tingkat D
    ![Subnet Tingkat D](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/7b05baeb-7d91-4ff0-bceb-f8f56bbdccba)

  - Tingkat E
    ![Subnet Tingkat E](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/41bd6dbb-a86d-4a8e-8aa4-f3d573c469f2)

  - Tingkat F
    ![Subnet Tingkat F](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/5e231963-4e15-4666-825b-419248c16507)

  - Tingkat G
    ![Subnet Tingkat G](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/28e0ceaa-c93c-471b-a092-61c76d45dab4)

  - Tingkat H
    ![Subnet Tingkat H](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/d387df44-5d00-4cd3-aeb7-358d9551ade5)

- Perhitungan Subnet

  - Total netmask: /14
  - Subnet mask: 255.252.0.0
  - Karena mask-nya /14, subnet address akan diawali menjadi 192.188.0.0/14 (14 static, 18 dynamic)
  - 192.190.0.0 = 11000000 10111110 00000000 00000000 menjadi:
    - 192.188.0.0 = 11000000 10111100 00000000 00000000
    - 192.189.0.0 = 11000000 10111101 00000000 00000000
    - 192.190.0.0 = 11000000 10111110 00000000 00000000
    - 192.191.0.0 = 11000000 10111111 00000000 00000000
  - Oleh karena itu, range usable IP nya adalah 192.188.0.1 - 192.191.255.254
  - Tree
    ![B24-CIDR-Tree](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/1c12be05-f86d-452b-814e-0577e6d8c36e)

- Konfigurasi GNS3

  - Router

    - Aura

    ```
    auto eth0
    iface eth0 inet dhcp

    #A13
    auto eth1
    iface eth1 inet static
        address 192.189.0.1
        netmask 255.255.255.252

    #A21
    auto eth2
    iface eth2 inet static
        address 192.190.96.1
        netmask 255.255.255.252

    #A20
    auto eth3
    iface eth3 inet static
        address 192.190.128.1
        netmask 255.255.255.252
    ```

    - Frieren

    ```
    #A13
    auto eth0
    iface eth0 inet static
        address 192.189.0.2
        netmask 255.255.255.252

    #A1
    auto eth1
    iface eth1 inet static
        address 192.188.128.1
        netmask 255.255.255.224

    #A14
    auto eth2
    iface eth2 inet static
        address 192.188.64.1
        netmask 255.255.255.252
    ```

    - Eisen

    ```
    #A21
    auto eth0
    iface eth0 inet static
        address 192.190.96.2
        netmask 255.255.255.252

    #A10
    auto eth1
    iface eth1 inet static
        address 192.190.32.1
        netmask 255.255.255.248

    #A18
    auto eth2
    iface eth2 inet static
        address 192.190.16.1
        netmask 255.255.255.252

    #A19
    auto eth3
    iface eth3 inet static
        address 192.190.72.1
        netmask 255.255.255.252

    #A12
    auto eth4
    iface eth4 inet static
        address 192.190.80.1
        netmask 255.255.255.252
    ```

    - Denken

    ```
    #A20
    auto eth0
    iface eth0 inet static
        address 192.190.128.2
        netmask 255.255.255.252

    #A9
    auto eth1
    iface eth1 inet static
        address 192.190.129.1
        netmask 255.255.255.0
    ```

    - Flamme

    ```
    #A14
    auto eth0
    iface eth0 inet static
        address 192.188.64.2
        netmask 255.255.255.252

    #A15
    auto eth1
    iface eth1 inet static
        address 192.188.8.1
        netmask 255.255.255.252

    #A3
    auto eth2
    iface eth2 inet static
        address 192.188.16.1
        netmask 255.255.252.0

    #A16
    auto eth3
    iface eth3 inet static
        address 192.188.32.9
        netmask 255.255.255.252
    ```

    - Fern

    ```
    #A15
    auto eth0
    iface eth0 inet static
        address 192.188.8.2
        netmask 255.255.255.252

    #A2
    auto eth1
    iface eth1 inet static
        address 192.188.0.1
        netmask 255.255.248.0
    ```

    - Himmel

    ```
    #A16
    auto eth0
    iface eth0 inet static
        address 192.188.32.10
        netmask 255.255.255.252

    #A4
    auto eth1
    iface eth1 inet static
        address 192.188.32.1
        netmask 255.255.255.248
    ```

    - Linie

    ```
    #A18
    auto eth0
    iface eth0 inet static
        address 192.190.16.2
        netmask 255.255.255.252

    #A17
    auto eth1
    iface eth1 inet static
        address 192.190.10.1
        netmask 255.255.255.252

    #A6
    auto eth2
    iface eth2 inet static
        address 192.190.8.1
        netmask 255.255.254.0
    ```

    - Lawine

    ```
    #A17
    auto eth0
    iface eth0 inet static
        address 192.190.10.2
        netmask 255.255.255.252

    #A11
    auto eth1
    iface eth1 inet static
        address 192.190.4.1
        netmask 255.255.255.192
    ```

    - Heiter

    ```
    #A11
    auto eth0
    iface eth0 inet static
        address 192.190.4.2
        netmask 255.255.255.192

    #A5
    auto eth1
    iface eth1 inet static
        address 192.190.0.1
        netmask 255.255.252.0
    ```

    - Lugner

    ```
    #A19
    auto eth0
    iface eth0 inet static
        address 192.190.72.2
        netmask 255.255.255.252

    #A7
    auto eth1
    iface eth1 inet static
        address 192.190.64.1
        netmask 255.255.255.0

    #A8
    auto eth2
    iface eth2 inet static
        address 192.190.68.1
        netmask 255.255.252.0
    ```

  - Client

    - LakeKorridor

    ```
    auto eth0
    iface eth0 inet static
        address 192.188.128.2
        netmask 255.255.255.224
        gateway 192.188.128.1
    ```

    - LaubHills

    ```
    auto eth0
    iface eth0 inet static
        address 192.188.0.2
        netmask 255.255.248.0
        gateway 192.188.0.1
    ```

    - AppetitRegion

    ```
    auto eth0
    iface eth0 inet static
        address 192.188.0.3
        netmask 255.255.248.0
        gateway 192.188.0.1
    ```

    - RohrRoad

    ```
    auto eth0
    iface eth0 inet static
        address 192.188.16.2
        netmask 255.255.252.0
        gateway 192.188.16.1
    ```

    - SchwerMountains

    ```
    auto eth0
    iface eth0 inet static
        address 192.188.32.2
        netmask 255.255.255.248
        gateway 192.188.32.1
    ```

    - BredtRegion

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.4.2
        netmask 255.255.255.192
        gateway 192.190.4.1
    ```

    - RiegelCanyon

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.0.2
        netmask 255.255.252.0
        gateway 192.190.0.1
    ```

    - GranzChannel

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.8.2
        netmask 255.255.254.0
        gateway 192.190.8.1
    ```

    - GrobeForest

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.64.2
        netmask 255.255.255.0
        gateway 192.190.64.1
    ```

    - TurkRegion

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.68.2
        netmask 255.255.252.0
        gateway 192.190.68.1
    ```

    - WilleRegion

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.129.2
        netmask 255.255.255.0
        gateway 192.190.129.1
    ```

    - RoyalCapital

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.129.3
        netmask 255.255.255.0
        gateway 192.190.129.1
    ```

    - Richter

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.32.2
        netmask 255.255.255.248
        gateway 192.190.32.1
    ```

    - Revolte

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.32.3
        netmask 255.255.255.248
        gateway 192.190.32.1
    ```

    - Sein

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.0.3
        netmask 255.255.252.0
        gateway 192.190.0.1
    ```

    - Stark

    ```
    auto eth0
    iface eth0 inet static
        address 192.190.80.2
        netmask 255.255.255.252
        gateway 192.190.80.1
    ```

- Routing

  - Aura

    ```
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.189.0.2 (connect flamme)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.190.128.2 (connect royalcapital and willeregion)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.189.0.2 (connect lakekorridor)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.189.0.2 (connect rohrroad)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.189.0.2 (connect fern)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.189.0.2 (connect appetitregion and laubhills)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.189.0.2 (connect himmel)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.189.0.2 (connect schwermountains)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.190.96.2 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.190.96.2 (connect stark)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.190.96.2 (connect linie)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.190.96.2 (connect lugner)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.190.96.2 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.190.96.2 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.190.96.2 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.190.96.2 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.190.96.2 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.190.96.2 (connect riegelcanyon and sein)
    ```

  - Frieren

    ```
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.189.0.1 (connect denken)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.189.0.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.188.64.2 (connect rohrroad)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.188.64.2 (connect fern)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.188.64.2 (connect appetitregion and laubhills)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.188.64.2 (connect himmel)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.188.64.2 (connect schwermountains)
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.189.0.1 (connect eisen)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.189.0.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.189.0.1 (connect stark)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.189.0.1 (connect linie)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.189.0.1 (connect lugner)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.189.0.1 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.189.0.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.189.0.1 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.189.0.1 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.189.0.1 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.189.0.1 (connect riegelcanyon and sein)
    ```

  - Denken

    ```
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.190.128.1 (connect frieren)
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.190.128.1 (connect flamme)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.190.128.1 (connect lakekorridor)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.190.128.1 (connect rohrroad)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.190.128.1 (connect fern)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.190.128.1 (connect appetitregion and laubhills)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.190.128.1 (connect himmel)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.190.128.1 (connect schwermountains)
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.190.128.1 (connect eisen)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.190.128.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.190.128.1 (connect stark)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.190.128.1 (connect linie)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.190.128.1 (connect lugner)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.190.128.1 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.190.128.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.190.128.1 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.190.128.1 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.190.128.1 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.190.128.1 (connect riegelcanyon and sein)
    ```

  - Flamme

    ```
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.188.64.1 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.188.64.1 (connect denken)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.188.64.1 (connect lakekorridor)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.188.64.1 (connect royalcapital and willeregion)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.188.8.2 (connect appetitregion and laubhills)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.188.32.10 (connect schwermountains)
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.188.64.1 (connect eisen)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.188.64.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.188.64.1 (connect stark)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.188.64.1 (connect linie)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.188.64.1 (connect lugner)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.188.64.1 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.188.64.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.188.64.1 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.188.64.1 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.188.64.1 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.188.64.1 (connect riegelcanyon and sein)
    ```

  - Fern

    ```
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.188.8.1 (connect frieren)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.188.8.1 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.188.8.1 (connect denken)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.188.8.1 (connect lakekorridor)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.188.8.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.188.8.1 (connect rohrroad)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.188.8.1 (connect himmel)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.188.8.1 (connect schwermountains)
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.188.8.1 (connect eisen)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.188.8.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.188.8.1 (connect stark)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.188.8.1 (connect linie)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.188.8.1 (connect lugner)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.188.8.1 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.188.8.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.188.8.1 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.188.8.1 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.188.8.1 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.188.8.1 (connect riegelcanyon and sein)
    ```

  - Himmel

    ```
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.188.32.9 (connect frieren)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.188.32.9 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.188.32.9 (connect denken)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.188.32.9 (connect fern)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.188.32.9 (connect lakekorridor)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.188.32.9 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.188.32.9 (connect rohrroad)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.188.32.9 (connect appetitregion and laubhills)
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.188.32.9 (connect eisen)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.188.32.9 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.188.32.9 (connect stark)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.188.32.9 (connect linie)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.188.32.9 (connect lugner)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.188.32.9 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.188.32.9 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.188.32.9 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.188.32.9 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.188.32.9 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.188.32.9 (connect riegelcanyon and sein)
    ```

  - Eisen

    ```
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.190.96.1 (connect denken)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.190.96.1 (connect frieren)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.190.96.1 (connect fern)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.190.96.1 (connect himmel)
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.190.96.1 (connect flamme)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.190.96.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.190.96.1 (connect rohrroad)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.190.96.1 (connect lakekorridor)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.190.96.1 (connect appetitregion and laubhills)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.190.96.1 (connect schwermountains)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.190.16.2 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.190.72.2 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.190.72.2 (connect turkregion)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.190.16.2 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.190.16.2 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.190.16.2 (connect riegelcanyon and sein)
    ```

  - Linie

    ```
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.190.16.1 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.190.16.1 (connect denken)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.190.16.1 (connect frieren)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.190.16.1 (connect fern)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.190.16.1 (connect himmel)
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.190.16.1 (connect flamme)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.190.16.1 (connect lugner)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.190.16.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.190.16.1 (connect rohrroad)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.190.16.1 (connect lakekorridor)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.190.16.1 (connect appetitregion and laubhills)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.190.16.1 (connect schwermountains)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.190.16.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.190.16.1 (connect stark)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.190.16.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.190.16.1 (connect turkregion)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.190.10.2 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.190.10.2 (connect riegelcanyon and sein)
    ```

  - Lugner

    ```
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.190.72.1 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.190.72.1 (connect denken)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.190.72.1 (connect frieren)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.190.72.1 (connect fern)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.190.72.1 (connect himmel)
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.190.72.1 (connect flamme)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.190.72.1 (connect linie)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.190.72.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.190.72.1 (connect rohrroad)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.190.72.1 (connect lakekorridor)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.190.72.1 (connect appetitregion and laubhills)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.190.72.1 (connect schwermountains)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.190.72.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.190.72.1 (connect stark)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.190.72.1 (connect granzchannel)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.190.72.1 (connect lawine)
    route add -net 192.190.4.0 netmask 255.255.255.192 gw 192.190.72.1 (connect heiter and bredtregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.190.72.1 (connect riegelcanyon and sein)
    ```

  - Lawine

    ```
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.190.10.1 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.190.10.1 (connect denken)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.190.10.1 (connect frieren)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.190.10.1 (connect fern)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.190.10.1 (connect himmel)
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.190.10.1 (connect flamme)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.190.10.1 (connect lugner)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.190.10.1 (connect eisen)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.190.10.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.190.10.1 (connect rohrroad)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.190.10.1 (connect lakekorridor)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.190.10.1 (connect appetitregion and laubhills)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.190.10.1 (connect schwermountains)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.190.10.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.190.10.1 (connect stark)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.190.10.1 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.190.10.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.190.10.1 (connect turkregion)
    route add -net 192.190.0.0 netmask 255.255.252.0 gw 192.190.4.2 (connect riegelcanyon and sein)
    ```

  - Heiter
    ```
    route add -net 192.190.96.0 netmask 255.255.255.252 gw 192.190.4.1 (connect aura)
    route add -net 192.190.128.0 netmask 255.255.255.252 gw 192.190.4.1 (connect denken)
    route add -net 192.189.0.0 netmask 255.255.255.252 gw 192.190.4.1 (connect frieren)
    route add -net 192.188.8.0 netmask 255.255.255.252 gw 192.190.4.1 (connect fern)
    route add -net 192.188.32.8 netmask 255.255.255.252 gw 192.190.4.1 (connect himmel)
    route add -net 192.188.64.0 netmask 255.255.255.252 gw 192.190.4.1 (connect flamme)
    route add -net 192.190.72.0 netmask 255.255.255.252 gw 192.190.4.1 (connect lugner)
    route add -net 192.190.16.0 netmask 255.255.255.252 gw 192.190.4.1 (connect eisen)
    route add -net 192.190.10.0 netmask 255.255.255.252 gw 192.190.4.1 (connect linie)
    route add -net 192.190.129.0 netmask 255.255.255.0 gw 192.190.4.1 (connect royalcapital and willeregion)
    route add -net 192.188.16.0 netmask 255.255.252.0 gw 192.190.4.1 (connect rohrroad)
    route add -net 192.188.128.0 netmask 255.255.255.224 gw 192.190.4.1 (connect lakekorridor)
    route add -net 192.188.0.0 netmask 255.255.248.0 gw 192.190.4.1 (connect appetitregion and laubhills)
    route add -net 192.188.32.0 netmask 255.255.255.248 gw 192.190.4.1 (connect schwermountains)
    route add -net 192.190.32.0 netmask 255.255.255.248 gw 192.190.4.1 (connect richter and revolte)
    route add -net 192.190.80.0 netmask 255.255.255.252 gw 192.190.4.1 (connect stark)
    route add -net 192.190.8.0 netmask 255.255.254.0 gw 192.190.4.1 (connect granzchannel)
    route add -net 192.190.64.0 netmask 255.255.255.0 gw 192.190.4.1 (connect grobeforest)
    route add -net 192.190.68.0 netmask 255.255.252.0 gw 192.190.4.1 (connect turkregion)
    ```

- Test
    - (Host - Host)
        - Frieren - Lawine
            - ![host-host](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/9e8a27bb-d7eb-4d3b-9636-66961944f989)

        - Lawine - Frieren
            - ![host-host-2](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/a769564c-30f1-49f3-a183-eba785bf2b35)

    - (Server - Host)
        - Stark - Flamme
            - ![server-host](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/039a664d-b205-41e8-ad3c-bf9125675353)

        - Flamme - Stark
            - ![server-host-2](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/6021bc40-d223-4736-bc9b-6f9ab248416c)

    - (Client - Host)
        - BredtRegion - Denken 
            - ![client-host](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/522c2cb6-bef2-472b-8897-c011f3323152)

        - Denken - BredtRegion
            - ![client-host-2](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/00bc1b4d-25a1-409e-b9b5-e2196ccc8022)

    - (Client-Client)
        - SchwerMountains - TurkRegion 
            - ![client-client](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/82f9d352-7d10-44a7-b35c-b677f05d0bf3)

        - TurkRegion - SchwerMountains
            - ![client-client-2](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/assets/142609964/fe209bd9-0c8f-4e45-b2ab-3f2c9d3b16a9)
