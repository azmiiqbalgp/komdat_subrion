# Aplikasi Web "Subrion"
<h1 align="center"><img src="https://subrion.org/templates/org/img/fb_subrion-logo.png" width="500px"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Otomatisasi](#otomatisasi) | [Maintenance](#maintenance) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:

## Sekilas Tentang

Subrion CMS adalah PHP sistem manajemen konten yang *powerful* dan mudah digunakan. Subrion muncul dengan banyak fitur termasuk, bebas menyunting *source code*-nya, izin per-halaman, *user activity monitoring*, dan banyak lagi. Pilihan yang sempurna untuk setiap solusi dari *entry* sampai ke tingkat perusahaan. Dashboard Admin Subrion juga sepenuhnya responsif, sehingga dapat dilihat melalui tablet dan *smartphone*, yang memungkinkan pengguna dapat mengelola konten dengan mudah. Fitur manajemen untuk bidang item *listing* juga ada. Bidang yang berhubungan dengan anggota, daftar otomatis, daftar *real estate*, kupon, atau apapun, dapat dengan mudah diperpanjang dengan fitur tambahan. Bidang ini dapat dibuat dalam berbagai bentuk, termasuk bidang teks, WYSIWYG, *checkboxes*, radio, gambar, lampiran, dan banyak lagi, semua demi kenyamanan panel admin Subrion.


## Instalasi
### Kebutuhan
1. *Server Requirements*
- Linux/FreeBSD/Windows OS server platform
- Apache 1.3 or above (mod_rewrite module installed)
- MySQL 4.1 or above
- PHP 5 or above (GD lib, XML lib, FreeType installed)
2. *Client Requirements*
- Web browser terbaru

### Cara Instalasi: 
1. Mengunduh file subrion terbaru. 
```
$ wget https://tools.subrion.org/get/latest.zip
```
2. Menyimpan file yang terunduh kedalam direktori subrion.
```
$ sudo apt install unzip
$ mkdir subrion
$ cd subrion
```
3. Meng-*extract* atau meng-*unzip* file yang telah terunduh.
```
$ mv latest.zip subrion
$ unzip latest.zip
```
4. Memindahkan direktori subrion ke  /var/www/html/ --
```
$ mv subrion /var/www/html
```
5. Meng-*install* subrion 
- buka localhost:8888/subrion
- username db: subrion
- password db: subrion
- nama db: subrion
	
### Membuat Database :
```
$ mysql -u root -p
- password: student

$ CREATE USER subrion IDENTIFIED BY ‘subrion’;
$ CREATE DATABASE subrion;
$ GRANT ALL PRIVILEGES ON subrion.* TO subrion;
$ FLUSH PRIVILEGES;

Quit
```
### Membuat config.inc.php --#
- copy code dari browser
```
$ cd /var/www/html/subrion/includes
$ nano config.inc.php
```
- paste
- write
- close


## Konfigurasi

Mengaktifkan *module* ``mod_rewrite``
```
$ cd /etc/apache2/sites-enabled
$ sudo nano 000-default.conf
```
Menambahkan baris di dalam block ``<VirtualHost *:80>``
```
...
<Directory /var/www/html>
Options Indexes FollowSymLinks MultiViews
	AllowOverride All
	Order allow,deny allow from all
</Directory>
…
```
- Overwrite
- Close
```
$ sudo service apache2 restart
```


## *Maintenance*

Setting tambahan untuk maintenance secara periodik, misalnya:
- hapus tmp sehari sekali
- buat backup seminggu sekali
- etc.


## Otomatisasi
Tidak dilakukan otomatisasi karena kebutuhan instalasi Subrion menyesuaikan komputer masing-masing.


## Cara Pemakaian

- Tampilan aplikasi web

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/1.PNG)

- Fungsi-fungsi utama

1. *Manage* Konten

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_1.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_2.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_3.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_4.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_5.PNG)



## Pembahasan

- Kelebihan : 
1. Mudah di operasikan
2. Fitur yang bagus
3. *Blocks, pages, menus* semua mudah digunakan
4. Memiliki *pre-defined 'positions'* untuk menempatkan konten begitu baik.
5. Sangat informatif dan juga menawarkan beberapa informasi tambahan yang mungkin tidak menjadi bagian dari pekerjaan.
6. Pemberitahuan atau peringatan tepat dipanel Admin
7. Mengubah status pada halaman / menu / blok begitu baik. Kita dapat mengubah status dan klik di tempat lain pada halaman dan secara otomatis halaman tersebut akan memperbarui.
8. Mudah menambahkan tema.
9. Pergantian *style* juga baik untuk digunakan.
10. Posisi slider dan *active bubble* yang baik untuk digunakan. Web designer juga mampu memodifikasinya dengan bantuan dukungan teknis Subrion.

- Kekurangan:
1. Admin *all in one view* tidak tersedia.
2. *Users banned*.
3. Menunggu persetujuan menambah html berita.
4. Menunggu persetujuan untuk *upload file*.
5. Menunggu persetujuan untuk menambahkan komentar pada blog.
6. Menunggu perstujuan untuk menambahkan member
7. Jumlah login yang gagal
8. Komplain *member*
9. *Members logged in*
10. Hanya  15 item disetiap halaman. Daerah yang bisa di *scroll*, sehingga jumlah *default* harus diperbesar.
11. Pengguna tidak bisa mengganti dengan tema sendiri.

- Komparasi aplikasi sejenis

Aplikasi web PageKit merupakan CMS yang bisa dikatakan baru, namun memiliki beberapa fitur yang diunggulkan, di antaranya :
1. Dibangun menggunakan *framework* PHP Symfony dan Vue.js
2. Tampilan yang modern dan *responsive*, namun tetap terlihat sederhana
3. Proses instalasi dan konfigurasi yang sangat mudah dan serba otomatis
4. Terdapat editor teks berupa Markdown dan HTML
5. Terdapat *file manager* untuk mengatur *file* apa saja yang diunggah ke server
6. Personalisasi dan pengaturan halaman situs yang tidak rumit.

Namun, dari keunggulan yang diberikan, masih terdapat beberapa kekurangan, di antaranya:
1. Variasi tema dan ekstensi (*plugin*) yang diberikan masih terbilang sedikit
2. Walaupun terbilang mudah, tidak seperti wordpress yang memiliki *live preview*, untuk mengatur tata letak *widget* yang akan ditampilkan di situs masih menggunakan menu *dropdown*.


## Referensi

1. https://dev.subrion.org/projects/subrion-cms/wiki/Installation
2. https://www.cmscritic.com/dir/products/subrion/
3. http://www.geekycorner.com/software-reviews/subrion-16.html
