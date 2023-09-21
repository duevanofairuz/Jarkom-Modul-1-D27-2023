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
werwerewr

----------------------------------------------------------------------------------------------------------------------------------
# No. 3
### Soal
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702

b. Protokol layer transport apa yang digunakan?

### Penyelesaian
werwerwr

----------------------------------------------------------------------------------------------------------------------------------
# No. 4
### Soal
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

### Penyelesaian
werwerwerw

----------------------------------------------------------------------------------------------------------------------------------
# No. 5
### Soal
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

b. Port berapakah pada server yang digunakan untuk service SMTP?

c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

### Penyelesaian
werwerwewe

----------------------------------------------------------------------------------------------------------------------------------
# No. 6
### Soal
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

### Penyelesaian
rwerwerwer

----------------------------------------------------------------------------------------------------------------------------------
# No. 7
### Soal
Berapa jumlah packet yang menuju IP 184.87.193.88?

### Penyelesaian
rwerwerw

----------------------------------------------------------------------------------------------------------------------------------
# No. 8
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

### Penyelesaian
werwerwer

----------------------------------------------------------------------------------------------------------------------------------
# No. 9
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

### Penyelesaian
werwerwer

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

