# Praktikum Jaringan Komputer
# Modul 1
### Kelompok B12
### Anggota :
|            Nama           |     NRP    |
| ------                    | ------     |
| Darvin Exaudi Simanjuntak | 5025211172 |
| Fathin Muhashibi Putra    | 5025211229 |

## NO. 1
> User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
### No. 1a 
> Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
### No. 1b
> Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
### No. 1c 
> Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
### No. 1d 
> Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

## NO. 2
> Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

#### Penjelasan :
**1. Pertama-tama, lakukan filtering untuk mendapatkan paket dengan protokol HTTP dengan mengetikkan `http` pada filter box dan klik `Enter` untuk memulai filtering.**
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/bd32769e-faf4-48b6-836c-ae0f854ce400">


**2. Kemudian, klik kanan pada salah satu paket dengan protokol http. Pilih `Follow` dan pilih `HTTP Stream`.**
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/7e8ec775-7279-4a01-88ac-104f9984c488">


**3. Setelah HTTP Stream dari paket tersebut ditampilkan, kita dapat melihat informasi terkait web server yang digunakan pada portal praktikum Jaringan Komputer, yaitu `gunicorn`.**

<img width="644" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/73162916-3e68-486d-9f12-b5e95b404488">


**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/20fdbede-a68d-47ec-a1ff-351c6f88350b)


## NO. 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
### No. 3a
Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
### No. 3b
Protokol layer transport apa yang digunakan?

## NO. 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

## NO. 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
### No. 5a
Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
### No. 5b
Port berapakah pada server yang digunakan untuk service SMTP?
### No. 5c
Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

## NO. 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## NO. 7
Berapa jumlah packet yang menuju IP 184.87.193.88?

## NO. 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

## NO. 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

## NO. 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet.
