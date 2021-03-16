<h1> Aplikasi Web "TextPattern" </h1>
<h1 align="center"><img src="https://andy-carter.com/files/cache/397/9ff0291dcee547b40660934ec4fceb44/txp.png"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:
  
  
  

  
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
    $ sudo service apache2 restart
    ```

3. Download TextPattern ke direktori kita. 
    ```
    $ wget https://textpattern.com/file_download/107/textpattern-4.8.4.zip
    ```

4. Extract.
    ```
    $ sudo apt-get install unzip
    $ sudo unzip textpattern-4.8.4.zip -d /var/www/html/
    ```
    ##### rename
    
    ```$ sudo mv var/www/html/textpattern-4.8.4.zip /var/www/html/textpattern```
    
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

      ![1](https://user-images.githubusercontent.com/74884859/111351328-a75ca000-86b5-11eb-8411-b9a03388907c.png)

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

- Menambah limit memory menjadi 128 Mb
  ![memory limit](https://user-images.githubusercontent.com/44494446/111346980-59de3400-86b1-11eb-9cb5-b8a9f8c3d360.png)
  
- Menambah maksimal ukuran upload file menjadi 16 Mb
  ![max size](https://user-images.githubusercontent.com/44494446/111346982-5ba7f780-86b1-11eb-8570-50f417219293.png)


# Cara Pemakaian
[`^ kembali ke atas ^`](#)
Cara pemakaian Textpattern ini sangat mudah, karena aplikasi ini telah menyediakan interface yang mudah dimengerti. Berikut untuk lebih jelasnya :  

- Login menggunakan akun yang telah dibuat sebelumnya  
<img width="264" alt="t1" src="https://user-images.githubusercontent.com/60084323/111364005-4dfb6d80-86c3-11eb-958b-92cf71b37c10.png">  

- Setelah login, kita akan masuk ke halaman Dashboard. Disini kita dapat menulis konten berupa artikel seperti contohnya content organization, date and time, dan lain sebagainya
![2](https://user-images.githubusercontent.com/74884859/111342444-0cf85e80-86ad-11eb-8496-e2b9209cd6ed.png)  

- apabila kita mengklik "article", maka akan keluar tampilan seperti dibawah ini. Tampilan ini digunakan untuk menulis maupun membuat sebuah konten dimana terdapat title, dan juga body untuk membuat artikel baru, apabila sudah selesai membuat, klik publish yang terdapat pada kanan atas
![3](https://user-images.githubusercontent.com/74884859/111344239-c60b6880-86ae-11eb-9cd2-c1238b1d82ec.png)

- Pada sidebar terdapat **sort and display** yang berguna untuk menentukan status, section, maupun overide form dari artikel yang telah dibuat. Selain itu, dibawah bar sort and display juga terdapat berbagai macam opsi yang dapat dipilih seperti date and time, kategori, meta, dan lain sebagainya.
<img width="228" alt="t3" src="https://user-images.githubusercontent.com/60084323/111364014-4fc53100-86c3-11eb-8827-6d400a613454.png">  

- Pada topbar terdapat tab "Presentation" yang berisi beberapa panel seperti panel section dibawah ini. **Panel section** ini berguna agar pengguna dapat melihat daftar list section/bagian dan fungsionalitasnya dan juga mengelolanya.
<img width="938" alt="t4" src="https://user-images.githubusercontent.com/60084323/111366702-6de06080-86c6-11eb-8b9b-321ba144d70b.png">  
- Selain panel section, ada juga **panel style** yang dapat mengubah style atau tampilan menggunakan css.

 


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
