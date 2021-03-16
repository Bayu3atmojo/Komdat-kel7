<h1> Aplikasi Web "TextPattern" </h1>
<h1 align="center"><img src="https://andy-carter.com/files/cache/397/9ff0291dcee547b40660934ec4fceb44/txp.png"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Otomatisasi](#otomatisasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:
  
  
  

  
# Sekilas Tentang
[`^ kembali ke atas ^`](#)

**Textpattern** CMS adalah sistem manajemen konten elegan yang gratis dan _open-source_. Desainer web, pengembang, penerbit, dan _blogger_ menyukai fleksibilitas dan ekstensibilitasnya. **TextPattern** memiliki performa yang kuat dan canggih yang dapat disetel tanpa batas agar sesuai dengan jenis situs web apa pun yang dapat Anda bayangkan. Ini memberikan pengalaman pengguna yang lebih baik, pengelolaan konten yang lebih mudah dan lebih cepat, lingkungan yang menarik secara visual, dan fleksibilitas.


# Instalasi
[`^ kembali ke atas ^`](#)

#### Kebutuhan Sistem :
- Unix, Linux atau Windows
- Apache Web Server 2.4+
- PHP 7.3+
- MySQL 5.0+

#### Proses Instalasi :
1. Login dengan SSH menggunakan [PuTTY](http://www.putty.org/) untuk windows.
   
   ![putty](https://user-images.githubusercontent.com/74884859/111350795-14bc0100-86b5-11eb-8591-ebdcc2cec2d0.png)

2. Update dan Install LAMP (Linux Apache MySQL PHP).
    ```
    $ sudo apt-get update
    $ sudo apt-get install apache2
    $ sudo apt-get install mysql-server
    $ sudo apt-get install php
    $ sudo apt-get install libapache2-mod-php
    $ sudo apt-get install php-mysql
    $ sudo apt-get install php-gd php-mcrypt php-mbstring php-xml php-ssh2 php-curl php-zip php-intl
    ```

3. download TextPattern ke direktori kita. 
    ```
    $ wget https://textpattern.com/file_download/107/textpattern-4.8.4.zip
    ```

4. Extract.
    ```
    $ sudo apt-get install unzip
    $ sudo unzip textpattern-4.8.4.zip -d var/www/html/
    ```
    ##### rename
    
    ```$ sudo mv var/www/html/textpattern-4.8.4.zip var/www/html/textpattern```
    
5. Ubah kepemilikan ke user www-data.
    ```
    $ sudo chown -R www-data:www-data /var/www/html/textpattern
    ```

6. Buat database dan user untuk TextPattern.
    ```
    $ mysql -u root -ve "
        CREATE DATABASE db;
        CREATE USER user@localhost IDENTIFIED BY 'password';
        GRANT ALL PRIVILEGES ON db.* TO user@localhost;"
    ```
      ##### db, user, dan password bebas

7. Lanjutkan instalasi dengan membuka page localhost:8000/textpattern dan ikuti petunjuk.
      - entah kenapa error. klik aja linknya.

      ![1](https://user-images.githubusercontent.com/74884859/111342429-0a960480-86ad-11eb-8e9e-40fa3392451c.png)

      - isi sesuai data yang kita buat pada tahap 6
 
      ![2](https://user-images.githubusercontent.com/74884859/111342433-0bc73180-86ad-11eb-860b-ccdb182c571e.png)

      - lalu kita diminta untuk membuat config.php isi seperti berikut
    
      ![3](https://user-images.githubusercontent.com/74884859/111342435-0bc73180-86ad-11eb-9837-50fbde829b75.png)
      
      ```$ sudo nano /var/www/html/textpattern/textpattern/config.php```
      ##### Paste kedalam config.php, CTRL+X, pencet Y , lalu Enter. Lanjut dengan menekan tombol "I did it".

      - Isi bebas.

      ![4](https://user-images.githubusercontent.com/74884859/111343950-817fcd00-86ae-11eb-9ece-be3fa8f4174a.png)

      - Isi sesuai login name dan password

      ![5](https://user-images.githubusercontent.com/74884859/111344799-4c27af00-86af-11eb-9a98-666507b9864d.png)
    
      - TextPattern siap dipakai

      ![6](https://user-images.githubusercontent.com/74884859/111342444-0cf85e80-86ad-11eb-8496-e2b9209cd6ed.png)
      ![7](https://user-images.githubusercontent.com/74884859/111344239-c60b6880-86ae-11eb-9cd2-c1238b1d82ec.png)

# Konfigurasi
[`^ kembali ke atas ^`](#)

- Bagian **Konfigurasi** dapat diakses dari bilah navigasi Admin dan memungkinkan Anda mengelola dan mengedit pengaturan global situs Anda.
  ![Settings1](https://user-images.githubusercontent.com/44494446/111302915-83359a80-8686-11eb-950f-623cef1e093c.png)
  
  
- Tab **Situs web** membantu Anda mengoptimalkan situs Anda dengan sebaik-baiknya. Kamu bisa:
  - Tetapkan nama situs web Anda untuk Search Engine Optimization (SEO) yang lebih baik
  - Sertakan deskripsi singkat tentang tujuan situs Anda
  - Sertakan kata kunci Situs Web
  - Edit pengaturan lain seperti format tanggal, posting per halaman atau zona waktu.
    ![settings2_1](https://user-images.githubusercontent.com/44494446/111302918-83ce3100-8686-11eb-9749-2bd3d094e123.png)
   
   
- Di **Template**, Anda dapat memilih template kustom dan tata letak halaman situs Anda. Perlu diingat bahwa saat ini kami sedang mengerjakan pengiriman template baru selain dari Microweber default.
  ![Template_Microweber](https://user-images.githubusercontent.com/44494446/111302924-84ff5e00-8686-11eb-848b-0be19d5fcecb.png)


- Tab **Login and Register** adalah kunci Anda untuk berinteraksi dengan pengguna lain. Jika ingin, Anda dapat menonaktifkan pendaftaran pengguna untuk situs Anda, atau mengizinkan masuk dengan jaringan sosial yang berbeda seperti Facebook, Twitter, Google+, dan lainnya.
  ![Login_Register](https://user-images.githubusercontent.com/44494446/111302913-83359a80-8686-11eb-9662-dc254a84d35f.png)


- Menavigasi melalui tab **E-mail** memungkinkan Anda mengkonfigurasi pengaturan teknis saat mengirim email (penggunaan Server SMTP, fungsi PHP, Gmail, Yahoo atau HotMail). Anda juga dapat menyesuaikan profil Anda sebagai pengirim, memilih nama atau email tertentu yang akan muncul di email yang Anda kirim ke pengunjung atau klien.
  ![E_mail](https://user-images.githubusercontent.com/44494446/111302905-816bd700-8686-11eb-8f0a-440e355981b3.png)


- Jika terjadi sesuatu yang salah dengan situs web Anda, ada tab **Cadangan**. Anda bisa:
  - Buat cadangan database untuk penggunaan dan keamanan di masa mendatang
  - Unggah cadangan yang ada jika Anda misalnya kehilangan informasi di situs web Anda
  - Unduh, Pulihkan, atau Hapus dari daftar dengan cadangan yang tersedia
  ![Backup](https://user-images.githubusercontent.com/44494446/111302903-816bd700-8686-11eb-9245-12ce1c4fc76c.png)


- Tab **Pembaruan** memungkinkan Anda mengetahui apakah situs Anda sudah diperbarui. Jika ada pembaruan sistem, pembaruan tersebut akan muncul di tab ini dan Anda dapat memilih mana yang akan diinstal. Jika Anda sudah mendapatkan informasi terbaru, kotak hijau akan memberi tahu Anda tentang hal ini. Ada juga tombol yang memungkinkan Anda memeriksa pembaruan pada waktu tertentu.
  ![Updates](https://user-images.githubusercontent.com/44494446/111302893-7fa21380-8686-11eb-82ba-6d0173a45aec.png)


- Tab **Toko** Anda memiliki fungsi yang sama dengan sub-bagian Pengaturan di bagian Toko Online Anda. Kamu bisa:
  - Kelola metode dan penyedia Pembayaran
  - Atur mata uang yang digunakan di toko online Anda
  ![Shop](https://user-images.githubusercontent.com/44494446/111302919-8466c780-8686-11eb-8228-8aeef07dd4c5.png)
  

- Tab **Advanced** benar-benar untuk pengguna tingkat lanjut, jadi berhati-hatilah saat bekerja dengannya. Kamu bisa:
  - Kosongkan tembolok situs Anda
  - Lacak log Sistem Anda
  - Muat ulang database
  - Masukkan tag kepala khusus.
  ![Advanced_2](https://user-images.githubusercontent.com/44494446/111302901-80d34080-8686-11eb-9a67-e5a83fc4719c.png)


-Tab **Bahasa** memungkinkan Anda memilih bahasa untuk antarmuka situs Anda. Anda juga dapat mengedit file bahasa Anda, mengganti nama elemen yang berbeda sesuai pilihan Anda.
  ![Language](https://user-images.githubusercontent.com/44494446/111302912-829d0400-8686-11eb-9bd4-f3583c5ebdcd.png)



# Maintenence 
[`^ kembali ke atas ^`](#)

# Otomatisasi 
[`^ kembali ke atas ^`](#)

# Cara Pemakaian
[`^ kembali ke atas ^`](#)

# Pembahasan
[`^ kembali ke atas ^`](#)

**Textpattern** adalah salah satu perangkat lunak _Open Source_ berbasis CMS (_Content Management Systems_). Textpattern sering disejajarkan dengan perangkat lunak untuk membangun blog pada umumnya, walaupun tujuan pembangunan awal dari **Textpattern** itu sendiri adalah untuk membuat suatu CMS untuk keperluan umum, yang cocok digunakan untuk berbagai macam kebutuhan. **Textpattern** ditulis dalam bahasa pemprograman `PHP`, dan dilepas ke umum dibawah naungan _GNU General Public License_. Beberapa kelebihan dari **TextPattern** yaitu :
- Menyediakan berbagai pilihan modifikasi _platform_, tema, dan _plugin_ gratis.
- Menggabungkan manajemen komentar yang efisien dan fitur _log visitor_.
- Memiliki fitur _subscription_ yang bisa dikelola, memungkinkan para pengunjung situs untuk menyesuaikan _feed_ konten sesuai dengan kebutuhan mereka.
- Mekanisme _template_ berbasis _tag_, yang memungkinkan pembuatan _blocks_ maupun isi beserta dengan _code_ yang di **Textpattern** dikenal dengan terminologi _forms_, dan sistem _tag builder_ untuk proses automasi pembentukan situs yang dibangun dengan **Texppatern**.
- Sistem Hierarki untuk pengguna, yang memungkinkan pengorganisasian struktural untuk para penulis, editor dan penerbit sehingga dapat bekerja sama dalam proses publikasi.
- Kemudahan dalam penulisan serta visualisasi laman pra tayang. 
- Keamanan anti _spam_ komentar, _CSS editor_ sudah terpasang, adanya _link_, _image_ dan _file management_.

Selain beberapa kelebihan di atas, **TextPattern** juga memiliki beberapa kelemahan, diantaranya :
- Fitur dan fungsi website terbatas, tidak 100% sesuai dengan keinginan pemilik website.
- Plugin kurang lengkap. Bahkan fitur untuk _pingback_ dan _trackback_ tidak tersedia.
- Hasil blog dari CMS ini sedikit lambat dan tidak responsif.

# Referensi
[`^ kembali ke atas ^`](#)

1. [How to Install PHP 7.3 on Ubuntu 16.04](https://www.rosehosting.com/blog/how-to-install-php-7-3-on-ubuntu-16-04/) - Rose Hosting
2. [How to Log Into a VPS with PuTTY on Windows](https://www.digitalocean.com/community/tutorials/how-to-log-into-a-vps-with-putty-windows-users) - DigitalOcean
3. [Kelebihan TextPattern](https://www.hostinger.co.id/tutorial/alternatif-wordpress#:~:text=Keunggulan%20Textpattern%3A,feed%20konten%20sesuai%20kebutuhan%20mereka) - Hostinger
4. [TextPattern](https://textpattern.com/) - TextPattern
5. [Wiki TextPattern](https://id.wikipedia.org/wiki/Textpattern) - Wikipedia
