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
### Penjelasan :
**Pertama, buka file `soal1.pcapng`, kemudian karena di soal menggunakan FTP, maka lakukan analyze dengan melakukan `follow` ke `TCP Stream`**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1aa.png">

**Setelah itu, ubah index Stream nya hingga menemukan `aktivitas mengunngah suatu file`. Dimana dalam konteks soal ini ada di `Stream 4` dengan aktivitas unggah file bertuliskan `STOR c75-GrabThePhisher.zip`.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1ab.png">

**Terakhir, buka packet aktivitasnya dan buka `Transmission Control Protocol` untuk melihat sequence numbernya.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1ac.png">

### No. 1b
> Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?

**Untuk acknowledge number, ada persis di bawah sequence number.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1ad.png">

### No. 1c 
> Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

**Untuk melihatnya, buka packet response dari c75-GrabThePhisher.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1ae.png">

### No. 1d 
> Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

**Sama seperti 1b, untuk acknowledge berada di bawah sequence number.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1ae.png">

**SS Flag:**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/1Flag.png">
## NO. 2
> Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

#### Penjelasan :
**1. Pertama-tama, buka file `soal2.pcapng` yang telah disediakan. Lalu, lakukan filtering untuk mendapatkan paket dengan protokol HTTP dengan mengetikkan `http` pada filter box dan klik `Enter` untuk memulai filtering.**
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/bd32769e-faf4-48b6-836c-ae0f854ce400">


**2. Kemudian, klik kanan pada salah satu paket dengan protokol http. Pilih `Follow` dan pilih `HTTP Stream`.**
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/7e8ec775-7279-4a01-88ac-104f9984c488">


**3. Setelah HTTP Stream dari paket tersebut ditampilkan, kita dapat melihat informasi terkait web server yang digunakan pada portal praktikum Jaringan Komputer, yaitu `gunicorn`.**

<img width="644" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/73162916-3e68-486d-9f12-b5e95b404488">


**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/20fdbede-a68d-47ec-a1ff-351c6f88350b)


## NO. 3
> Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
### No. 3a
> Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
#### Penjelasan :
**1. Pertama-tama, buka file `soal2.pcapng` yang telah disediakan. Kemudian lakukan filtering dengan kueri `(ip.src == 239.255.255.250 && udp.srcport == 3702) || (ip.dst == 239.255.255.250 && udp.dstport == 3702)`.**

Keterangan Kueri : 
- `(ip.src == 239.255.255.250 && udp.srcport == 3702)` : Memfilter paket yang `berasal dari` address 239.255.255.250 dan Port 3702.
- `||` : Merupakan operator yang berarti `or`.
- `(ip.dst == 239.255.255.250 && udp.dstport == 3702)` : Memfilter paket yang `menuju` address 239.255.255.250 dan Port 3702.

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/a6bafbc3-1e3c-45ef-a213-c0513567d11b">


**2. Kemudian, lihat ke bagian bawah jendela wireshark dimana menunjukkan informasi terkait Jumlah Seluruh Paket `Packets` dan Jumlah Paket Hasil Filter yang tercapture `Displayed`. Berdasarkan informasi tersebut, banyak paket yang tercapture atau `Displayed`, yaitu sebanyak `21 paket`.**
<img width="269" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/e72b7d7a-5a78-4c5c-b1ca-820a85b752e2">

### No. 3b
> Protokol layer transport apa yang digunakan?
#### Penjelasan :
**Berdasarkan hasil filter dari kueri sebelumnya, pada `kolom protocol` ditunjukkan seluruhnya menggunakan Protokol Layer Transport `UDP`.**  

<img width="56" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/f4abb01e-98a2-41f4-8045-ec60d51755dc">

**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/8cf75ffa-3c33-4f0f-9fac-fdc7a257336e)


## NO. 4
> Berapa nilai checksum yang didapat dari header pada paket nomor 130?
#### Penjelasan :

**1. Buka file `soal4.pcapng`. Kemudian buka menu `Go` dan pilih `Go to Packet` agar bisa memilih nomor paket yang ingin dikunjungi.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/2a.png">

**2. Setelah itu, masukkan angka `130` untuk memilih packet nomor 130 (karena di soal didapat dari header paket nomor 130) dan klik `Go to Packet`.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/2b.png">

**3. Terakhir, setelah diarahkan ke paket nomor 130, buka `User Diagram Protocol`. Di dalam User Diagram Protocol akan ada `nilai Checksum`.**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/2c.png">

**SS Flag:**
<img width="960" alt="image" src="https://gitlab.com/DarvinExa/projek/-/raw/main/JarkomPrak1/4flag.png">

## NO. 5
> Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
### No. 5a
> Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
#### Penjelasan :

**1. Pertama-tama, buka file `soal5.pcap` yang telah disediakan.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/5ed7b500-0874-41d6-ab2f-da196798c279">

**2. Kemudian, lihat ke bagian bawah jendela wireshark dimana menunjukkan informasi terkait Jumlah Seluruh Paket `Packets`. Berdasarkan informasi tersebut,  banyak packet yang berhasil di capture dari file pcap tersebut `Displayed`, yaitu sebanyak `60 paket`.**

<img width="267" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/0697d27a-3076-45a4-a4af-ec63b4faac38">

### No. 5b
> Port berapakah pada server yang digunakan untuk service SMTP?
#### Penjelasan :
**Port default yang digunakan untuk layanan SMTP `port 25`**

### No. 5c
> Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
#### Penjelasan :
**1. Kemudian lakukan filtering dengan mengetikkan `ip.src` pada filter box dan klik `Enter` untuk memulai filtering.**

**2. Alamat IP yang tercapture, yaitu `10.10.1.1, 10.10.1.4, dan 74.53.140.153`. Ternyata IP yang merupakan public IP adalah `74.53.140.153`**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/b412bd54-38f2-4391-9467-7773e49abc94">

### Cara Mendapatkan IP nc untuk Connect ke Instance soal:
**1. Pertama-tama, download file `soal5.pcap` yang telah disediakan dan download `zippppfileee.zip` juga.**

**2. Karena kita membutuhkan password untuk ekstrak file zip, buka terlebih dahulu file `soal5.pcap`, cari paket yang memuat info terkait password, yaitu `paket 14`**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/869bdcf5-56cd-4e22-955d-0d3a5b6b32dd">

**3. Kemudian, klik kanan pada paket tersebut. Pilih `Follow` dan pilih `TCP Stream`.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/ae1fc791-a027-4410-a437-5b39c375488c">

**4. Setelah TCP Stream dari paket tersebut ditampilkan, maka cari informasi terkait password untuk membuka file zip**

<img width="643" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/b5ec29ec-fa19-4e7c-8599-aa25b52e3ade">

**5. Dari kode password yang didapatkan perlu dilakukan decode pada Base64 untuk mendapatkan password asli. Decode dilakukan dengan bantuan `https://www.base64decode.org/`. Maka, didapatkan bahwa password dari file zip adalah `5implePas5word`**

<img width="581" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/971e2f05-e79c-4ec2-a1fe-274434d51137">

**4. Extract file zip tersebut dengan password `5implePas5word`.**

<img width="401" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/fa097914-8bea-40b2-be5c-c2f8f6a44f43">

**5. Sehingga, didapatkan `nc 10.21.78.111 11111` untuk connect ke instance.**

<img width="354" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/280f4a44-5a8f-49e3-a245-c6b7c940c50e">


**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/bec813d8-e0fd-44aa-82c1-773eb9ea86f2)

## NO. 6
> Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
#### Penjelasan :

## NO. 7
> Berapa jumlah packet yang menuju IP 184.87.193.88?
#### Penjelasan :
**1. Pertama-tama, buka file `soal6-9.pcapng` yang telah disediakan.**
**2. Kemudian lakukan filtering dengan kueri `ip.dst == 184.87.193.88`.**
Keterangan Kueri : 
- `ip.dst == 184.87.193.88` : Memfilter paket yang menuju `IP 184.87.193.88`.
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/0e0d1af2-d853-4847-ba47-ba515fd19f36">
  
**3. Kemudian, lihat ke bagian bawah jendela wireshark dimana menunjukkan informasi terkait Jumlah Seluruh Paket `Packets` dan Jumlah Paket Hasil Filter yang tercapture `Displayed`. Berdasarkan informasi tersebut, banyak paket yang tercapture atau `Displayed`, yaitu sebanyak `6 paket`.****
<img width="268" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/3c54f926-c79f-4fd7-90cd-86236b33982b">


**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/4a9b5b06-724a-455d-b5e5-9adab47cb20d)


## NO. 8
> Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
#### Penjelasan :
**1. Pertama-tama, buka file `soal6-9.pcapng` yang telah disediakan.**

**2. Kemudian lakukan filtering dengan kueri `tcp.dstport == 80 || udp.dstport == 80`.**

Keterangan Kueri : 
- `tcp.dstport == 80` : Memfilter paket yang menuju `Port 80` menggunakan protocol TCP.
- `||` : Merupakan operator yang berarti `or`.
- `udp.dstport == 80` : Memfilter paket yang menuju `Port 80` menggunakan protocol UDP.

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/5af71588-a9f5-41c3-b9e6-c81835ee25ea">

**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/34b556c6-7ba9-49b5-a857-0eaf42dcdcda)


## NO. 9
> Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
#### Penjelasan : 
**1. Pertama-tama, buka file `soal6-9.pcapng` yang telah disediakan.**

**2. Kemudian lakukan filtering dengan kueri `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`.**

Keterangan Kueri : 
- `ip.src == 10.51.40.1` : Memfilter paket yang `berasal` dari alamat `10.51.40.1 `.
- `&&` : Merupakan operator yang berarti `and`.
- `ip.dst != 10.39.55.34` : Memfilter paket yang `tidak menuju` alamat `10.39.55.34`
  
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/aaf54497-5c37-4cf4-b4f0-fd496bcf9849">

**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/f89a7ab1-8cb4-4bca-ae57-a5302b23bd38)


## NO. 10
> Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet.
#### Penjelasan :
**1. Pertama-tama, buka file `soal10.pcapng` yang telah disediakan.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/81627828-2f5c-4040-89cc-f4c1545cf8d0">


**2. Kemudian lakukan filtering dengan mengetikkan `telnet` pada filter box dan klik `Enter` untuk memulai filtering.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/fc8c8189-0b42-43f4-b560-313b3d3ce110">


**3. Kemudian, klik kanan pada salah satu paket. Pilih `Follow` dan pilih `TCP Stream`.**

<img width="644" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/74ae75da-f6ea-4e9b-930a-3eb8bac4a9df">

**4. Setelah TCP Stream dari paket tersebut ditampilkan, maka cari informasi dari tiap stream.**

**5. Cek satu persatu stream, didapatkan beberapa kredensial. Coba satu persatu informasi kredensial yang ada. Sehingga, didapatkan kredensial yang tepat, yaitu `dhafin:kesayangannyak0k0` pada `stream 2`**

<img width="641" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/5d73728f-fa21-4d5b-9ece-a3a27e465f32">

**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/891e5879-4f98-4e0d-9201-b4f637a0b4f0)

