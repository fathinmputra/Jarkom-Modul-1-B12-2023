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
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/47327d1f-47ea-4227-b0a7-69a27d3b2999">


**2. Kemudian, klik kanan pada salah satu paket dengan protokol http. Pilih `Follow` dan pilih `HTTP Stream`.**
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/3b194a5e-d420-4b6a-9765-cd09bb23ab42">


**3. Setelah HTTP Stream dari paket tersebut ditampilkan, kita dapat melihat informasi terkait web server yang digunakan pada portal praktikum Jaringan Komputer, yaitu `gunicorn`.**

<img width="646" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/13992672-8625-426f-bc0b-17ddb74d0f0c">


**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/fe7d1715-0be4-4c17-92a3-7f5d23e66814)


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

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/c04217e3-82fe-446c-962c-cea8495d7577">


**2. Kemudian, lihat ke bagian bawah jendela wireshark dimana menunjukkan informasi terkait Jumlah Seluruh Paket `Packets` dan Jumlah Paket Hasil Filter yang tercapture `Displayed`. Berdasarkan informasi tersebut, banyak paket yang tercapture atau `Displayed`, yaitu sebanyak `21 paket`.**

<img width="272" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/ba845ce2-0910-4da7-ac48-4203e7a6b937">


### No. 3b
> Protokol layer transport apa yang digunakan?
#### Penjelasan :
**Berdasarkan hasil filter dari kueri sebelumnya, pada `kolom protocol` ditunjukkan seluruhnya menggunakan Protokol Layer Transport `UDP`.**  

<img width="65" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/f9e05e0f-aca0-4d50-9393-a65b18b99097">

**ScreenShoot Flag :**

![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/9e330ca3-e87a-4393-a7c7-1067fe34170a)

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

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/b5ad30db-390c-48db-9d09-50f7d654f425">

**2. Kemudian, lihat ke bagian bawah jendela wireshark dimana menunjukkan informasi terkait Jumlah Seluruh Paket `Packets`. Berdasarkan informasi tersebut,  banyak packet yang berhasil di capture dari file pcap tersebut `Displayed`, yaitu sebanyak `60 paket`.**

<img width="270" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/ed767f42-e47f-4c12-ab53-3702fea2fdc2">

### No. 5b
> Port berapakah pada server yang digunakan untuk service SMTP?
#### Penjelasan :
**Port default yang digunakan untuk layanan SMTP `port 25`**

### No. 5c
> Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
#### Penjelasan :
**1. Kemudian lakukan filtering dengan mengetikkan `ip.src` pada filter box dan klik `Enter` untuk memulai filtering.**

**2. Alamat IP yang tercapture, yaitu `10.10.1.1, 10.10.1.4, dan 74.53.140.153`. Ternyata IP yang merupakan public IP adalah `74.53.140.153`**

<img width="959" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/e53982bd-2688-48f8-99fd-8ccd4f3ef66a">


### Cara Mendapatkan IP nc untuk Connect ke Instance soal:
**1. Pertama-tama, download file `soal5.pcap` yang telah disediakan dan download `zippppfileee.zip` juga.**

**2. Karena kita membutuhkan password untuk ekstrak file zip, buka terlebih dahulu file `soal5.pcap`, cari paket yang memuat info terkait password, yaitu `paket 14`**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/e95cdba3-83be-4be2-ba99-57d6fcc6520e">


**3. Kemudian, klik kanan pada paket tersebut. Pilih `Follow` dan pilih `TCP Stream`.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/f6706868-5080-4242-9f2f-2e0db15f416b">


**4. Setelah TCP Stream dari paket tersebut ditampilkan, maka cari informasi terkait password untuk membuka file zip**

<img width="644" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/905fae3e-4732-4993-9fa8-427d35198426">

**5. Dari kode password yang didapatkan perlu dilakukan decode pada Base64 untuk mendapatkan password asli. Decode dilakukan dengan bantuan `https://www.base64decode.org/`. Maka, didapatkan bahwa password dari file zip adalah `5implePas5word`**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/aad2a4fe-e944-49be-b9f6-3cff45f1b7f7">

**4. Extract file zip tersebut dengan password `5implePas5word`.**

<img width="250" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/0f71ed41-1d25-417d-8be8-a3c231d134dc">


**5. Sehingga, didapatkan `nc 10.21.78.111 11111` untuk connect ke instance.**

<img width="427" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/fbf2fcc9-c593-48ec-b42c-fb68dd27f3c1">

**ScreenShoot Flag :**
![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/aeb19b64-5241-49e1-b654-5f5f02594892)


## NO. 6
> Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
#### Penjelasan :
**1. Berdasarkan soal yang didapat, terdapat beberapa hint sebagai berikut.**

<img width="310" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/8ab46fff-55c1-4582-937a-cdccdf08cc13">

**2. Buka file `soal6-9.pcapng` yang telah disediakan.**

**3. Cari paket ke `7812`. Lalu didapatkan ip.src, yaitu `104.18.14.101`**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/b366f660-119a-49c7-8b9c-d9d28c347211">

<img width="319" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/10c67a51-8bad-4a7c-865c-32e3ef94d4bd">

**4. Dari Hint yang sebelumnya didapatkan, terdapat 6 huruf. Namun, karena ip.src hanya terdiri dari 4 digit angka (`104.18.14.101`) kita harus bagi menjadi 6 digit angka (`10.4.18.14.10.1`)**

**5. Selanjutnya ubah tiap digit angka dari `10.4.18.14.10.1` dengan substitusi a1z26 Cipher. Rentang Huruf yang digunakan Huruf A-R, 1-18. Sehingga, didapatkan jawaban `JDRNJA`.**

**ScreenShoot Flag :**
<img width="863" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/9e8e406e-97e2-4496-bd1d-851edc021afc">


## NO. 7
> Berapa jumlah packet yang menuju IP 184.87.193.88?
#### Penjelasan :
**1. Pertama-tama, buka file `soal6-9.pcapng` yang telah disediakan.**
**2. Kemudian lakukan filtering dengan kueri `ip.dst == 184.87.193.88`.**
Keterangan Kueri : 
- `ip.dst == 184.87.193.88` : Memfilter paket yang menuju `IP 184.87.193.88`.

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/af21556d-101d-402d-b26d-45b16c2d1b06">

  
**3. Kemudian, lihat ke bagian bawah jendela wireshark dimana menunjukkan informasi terkait Jumlah Seluruh Paket `Packets` dan Jumlah Paket Hasil Filter yang tercapture `Displayed`. Berdasarkan informasi tersebut, banyak paket yang tercapture atau `Displayed`, yaitu sebanyak `6 paket`.****

<img width="265" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/5f891fdf-e766-474a-9ac2-de77133f4c7f">

**ScreenShoot Flag :**

![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/39fd223f-952a-41e5-b1bb-8213aa77075d)

## NO. 8
> Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
#### Penjelasan :
**1. Pertama-tama, buka file `soal6-9.pcapng` yang telah disediakan.**

**2. Kemudian lakukan filtering dengan kueri `tcp.dstport == 80 || udp.dstport == 80`.**

Keterangan Kueri : 
- `tcp.dstport == 80` : Memfilter paket yang menuju `Port 80` menggunakan protocol TCP.
- `||` : Merupakan operator yang berarti `or`.
- `udp.dstport == 80` : Memfilter paket yang menuju `Port 80` menggunakan protocol UDP.

<img width="953" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/14320b49-ce31-46d3-b921-ab3f30d07a2b">

**ScreenShoot Flag :**

![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/f01e847c-f4a3-49ae-9f1b-633f84aaa237)


## NO. 9
> Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
#### Penjelasan : 
**1. Pertama-tama, buka file `soal6-9.pcapng` yang telah disediakan.**

**2. Kemudian lakukan filtering dengan kueri `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`.**

Keterangan Kueri : 
- `ip.src == 10.51.40.1` : Memfilter paket yang `berasal` dari alamat `10.51.40.1 `.
- `&&` : Merupakan operator yang berarti `and`.
- `ip.dst != 10.39.55.34` : Memfilter paket yang `tidak menuju` alamat `10.39.55.34`
  
<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/08cfa9d9-2ba5-4533-b346-1c2a7ebba9fd">

**ScreenShoot Flag :**

![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/2aad49cb-a2f3-43b7-aa6c-8de99ec6b6c3)


## NO. 10
> Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet.
#### Penjelasan :
**1. Pertama-tama, buka file `soal10.pcapng` yang telah disediakan.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/6677bf17-d55a-4ca1-aac8-658acae47f50">


**2. Kemudian lakukan filtering dengan mengetikkan `telnet` pada filter box dan klik `Enter` untuk memulai filtering.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/e15f9045-e7f3-4ac6-96cb-f0843d4ebe16">

**3. Kemudian, klik kanan pada salah satu paket. Pilih `Follow` dan pilih `TCP Stream`.**

<img width="960" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/9c20e5b6-29b9-4a30-9f47-5875990e8258">

**4. Setelah TCP Stream dari paket tersebut ditampilkan, maka cari informasi dari tiap stream.**

**5. Cek satu persatu stream, didapatkan beberapa kredensial. Coba satu persatu informasi kredensial yang ada. Sehingga, didapatkan kredensial yang tepat, yaitu `dhafin:kesayangannyak0k0` pada `stream 2`**

<img width="644" alt="image" src="https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/8599e879-5151-4d55-a735-c6b986e70b4f">

**ScreenShoot Flag :**

![image](https://github.com/fathinmputra/Jarkom-Modul-1-B12-2023/assets/103252800/c5921c01-bf16-4523-b65e-18c3cffab221)

