# Jarkom-Modul-1-D27-2023

Anggota Kelompok Jarkom D27:
* Duevano Fairuz Pandya (5025211052)
* Choirul Rijal Dawam Iba (5025211206)

# No. 1
### Soal
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?

b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

### Penyelesaian
Untuk mengetahui protokol FTP yang digunakan untuk mengupload file bisa menggunakan sintaks display filter berikut:

```ftp contains "STOR"```
![1_1](images/1_1.png)

setelah mengetahui file yang diupload, kita bisa lakukan display filter berikut untuk mengetahui `Request` dan `Response` nya

```ftp contains "zip"```
![1_2](images/1_2.png)

Untuk soal a dan b kita bisa lihat pada paket Request bagian berikut:
![1_3](images/1_3.png)

Sedangkan untuk soal b dan c kita bisa lihat pada paket Response bagian berikut:
![1_4](images/1_4.png)

Perolehan Flag:
![1_5](images/1_5.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 2
### Soal
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

### Penyelesaian
Kita perlu mencari paket-paket dengan alamat IP portal praktikum yakni **10.21.78.111** menggunakan display filter berikut:

```ip.addr == 10.21.78.111```
![2_1](images/2_1.png)

setelah itu kita klik salah satu paket dan follow ke tcp streamnya
![2_2](images/2_2.png)

server yang dipakai adalah **gunicorn**

Perolehan Flag:
![2_3](images/2_3.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 3
### Soal
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702

b. Protokol layer transport apa yang digunakan?

### Penyelesaian
Lakukan display filter sesuai alamat IP soal sebagai berikut:

```ip.addr == 239.255.255.250```
![3_1](images/3_1.png)

lalu kita bisa lihat protocol layer yang digunakan adalah **UDP** (jawaban soal b), sehingga bisa kita tambahkan ke display filter menjadi:
```ip.addr == 239.255.255.250 and udp.port == 3702```
![3_2](images/3_2.png)

setelah itu dapat kita hitung total paket nya yakni **21** (jawaban soal a)

Perolehan Flag:
![3_3](images/3_3.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 4
### Soal
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

### Penyelesaian
Kita cukup scroll hingga menemukan paket nomor 130 lalu buka deskripsi TCP nya seperti berikut:
![4_1](images/4_1.png)

nilai checksum yang dimaksud adalah: **0x18e5**

Perolehan Flag:
![4_2](images/4_2.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 5
### Soal
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

b. Port berapakah pada server yang digunakan untuk service SMTP?

c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

### Penyelesaian
Di soal nomor 5 ini kita tidak mendapatkan **kode netcat** nya secara langsung, jadi untuk menyelesaikannya 
* Pertama-tama kita download file **.zip** yang disediakan soal
* Lalu kita cari **password** nya dengan cara mencari file / paket yang unik yang ada di file pcap, berikut ini adalah paket yang unik
![5_1](images/5_1.png)

* Buka tcp stream dan scroll hingga menemukan clue password
![5_2](images/5_2.png)

* Decode password **NWltcGxlUGFzNXdvcmQ=** menggunakan base64
![5_3](images/5_3.png)
PASSWORD: **5implePas5word**

* Setelah itu ekstrak file zip, dan kita mendapatkan kode netcat nya yakni `nc 10.21.78.111 11111`

* Untuk menyelesaikan soal a kita cukup scroll dan lihat total paket nya yakni **60** (jawaban soal a)
* Untuk menyelesaikan soal b kita cukup klik salah satu paket dengan protokol SMTP
![5_4](images/5_4.png)
port yang digunakan adalah port **25** (jawaban soal b)

* Untuk menyelesaikan soal c, karena hanya ada dua alamat IP di file capture tersebut kita cukup coba satu persatu, sehingga IP address yang dimaksud adalah **74.53.140.153** (jawaban soal c)

Perolehan Flag:
![5_5](images/5_5.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 6
### Soal
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan **"server SOURCE ADDRESS 7812 is invalid"**. ketika ditelusuri di google, hasil pencarian hanya menampilkan **a1 e5 u21**. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

### Penyelesaian
Karena di soal diketahui **SOURCE ADDRESS 7812** maka kita cari paket nomor 7812 dan lihat alamat ip source nya
![6_1](images/6_1.png)
alamat ip yang dimaksud adalah: **104.18.14.101**

Selanjutnya kita terjemahkan alamat ip tersebut menggunakan clue yang diberikan soal yakni **a1 e5 u21**
![6_2](images/6_2.png)
Kode error yang dimaksud: **JDRNJA**

Perolehan Flag:
![6_3](images/6_3.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 7
### Soal
Berapa jumlah packet yang menuju IP 184.87.193.88?

### Penyelesaian
Kita cukup lakukan sintaks display filter berikut:
```ip.dst == 184.87.193.88```
![7_1](images/7_1.png)

Jumlah paket yang menuju IP tersebut adalah **6**

Perolehan Flag:
![7_2](images/7_2.png)

----------------------------------------------------------------------------------------------------------------------------------
# No. 8
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

### Penyelesaian
Untuk menyelesaikkan soal no 8 di `filter` wireshark ketik `tcp.dtsport == 80 || udp.dstport == 80 ` sehingga di temukan jawaban yang benar seperti gambar dibawah
![8](https://github.com/duevanofairuz/Jarkom-Modul-1-D27-2023/assets/66956806/0d56838e-d4ef-4f78-9b33-409f1df6b48b)


----------------------------------------------------------------------------------------------------------------------------------
# No. 9
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

### Penyelesaian
Untuk mencari alamat `10.51.40.1` yaitu dengan cara `ip.src == 10.51.40.1` di tambah konjungsi `&&` dan untuk mencari alamat yang tidak ingin kita cari dengan cara `ip.dst != 10.39.55.34`, jika digabung seperti   `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34` sehingga di dapatkan jawaban yang benar seperti gambar di bawah
![9](https://github.com/duevanofairuz/Jarkom-Modul-1-D27-2023/assets/66956806/ec18c80d-2edc-48ae-8a33-1403a904bb72)


----------------------------------------------------------------------------------------------------------------------------------
# No. 10
### Soal
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet!

### Penyelesaian
Untuk mencari user yang melakukan login ,pertama 

```Telnet```
![telnet](https://github.com/duevanofairuz/Jarkom-Modul-1-D27-2023/assets/66956806/676a2112-d98b-4753-bb87-85eea7f2295b)

Setelah itu akan muncul tampilan `User` dan `password`
![fr-marker-60](https://github.com/duevanofairuz/Jarkom-Modul-1-D27-2023/assets/66956806/bc1fa108-7709-4aa2-8e7c-4cfd67984573)

