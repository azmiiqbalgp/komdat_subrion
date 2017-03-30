# Aplikasi Web "Subrion"
<center><img src="https://subrion.org/templates/org/img/fb_subrion-logo.png" width="500px"></center>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Otomatisasi](#otomatisasi) | [Maintenance](#maintenance) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:

## Sekilas Tentang

Subrion CMS adalah PHP sistem manajemen konten yang *powerful* dan mudah digunakan. Subrion muncul dengan banyak fitur, termasuk bebas menyunting *source code*-nya, izin per-halaman, *user activity monitoring*, dan banyak lagi. Pilihan yang sempurna untuk setiap solusi dari *entry* sampai ke tingkat perusahaan. Dashboard Admin Subrion juga sepenuhnya responsif, sehingga dapat dilihat melalui tablet dan *smartphone*, yang memungkinkan pengguna dapat mengelola konten dengan mudah. Fitur manajemen untuk bidang item *listing* juga ada. *Field* yang berhubungan dengan anggota, daftar otomatis, daftar *real estate*, kupon, atau apapun, dapat dengan mudah diperpanjang dengan fitur tambahan. *Field* ini dapat dibuat dalam berbagai bentuk, termasuk *field* teks, WYSIWYG, *checkbox*, radio, gambar, lampiran, dan banyak lagi, semua demi kenyamanan panel admin Subrion.


## Instalasi
### Kebutuhan
1. *Server Requirements*
- Linux/FreeBSD/Windows OS server platform
- Apache 1.3 or above (mod_rewrite module installed)
- MySQL 4.1 or above
- PHP 5 or above (GD lib, XML lib, FreeType installed)

2. *Client Requirements*
- Web browser terbaru

### Cara Instalasi
1. Mengunduh file subrion terbaru 
```
$ wget https://tools.subrion.org/get/latest.zip
```
2. Mengekstrak file yang telah diunduh.
```
$ sudo apt install unzip

$ mkdir subrion
$ unzip -d subrion latest.zip
```
4. Memindahkan direktori subrion ke  /var/www/html/
```
$ sudo mv subrion /var/www/html
```
5. Mengatur *permission* folder
```
$ cd /var/www/html/subrion

$ chmod 777 backup/
$ chmod 777 tmp/
$ chmod 777 uploads/
```
6. Membuat user & database MySQL
```
$ mysql -u root -p

mysql> CREATE USER 'subrion'@'localhost' IDENTIFIED BY 'subrion';
mysql> CREATE DATABASE subrion;
mysql> GRANT ALL PRIVILEGES ON subrion2.* TO 'subrion'@'localhost';
mysql> FLUSH PRIVILEGES;

mysql> quit
```
6. [Mengaktifkan mod_rewrite](#mengaktifkan-modrewrite).
7. Meng-*install* subrion
- Buka http://localhost:8888/subrion
- Pada halaman *Pre-Installation Check*, pastikan semua yang dibutuhkan (*required*) terpenuhi. Jika sudah, klik tombol **Next**.
- Pada halaman *Subrion License*, silakan baca peraturan dari lisensi. Jika setuju, klik tombol **Next**.
- Pada halaman *Configuration*, isikan
	-- DB username: `subrion`,
	-- DB password: `subrion`,
	-- DB name: `subrion`.
	-- Username, password, dan email pada bagian *Administrator Configuration* bisa diisi sesuai keinginan.
- Jika sudah, klik tombol *Istall*.

### Membuat config.inc.php
1. Setelah proses instalasi selesai, akan muncul pesan `Error during configuration write`.

2. Salin kode  php dari browser. Jika belum muncul, klik tombol **View config file**.

3. Buat file config.inc.php. 
```
$ cd /var/www/html/subrion/includes
$ nano config.inc.php
```
4. Tempel kode yang terlah disalin ke editor nano.
5. Simpan (Ctrl+O) dengan nama config.inc.php (Enter).
6. Tutup file (Ctrl+X).


## Konfigurasi

###Mengaktifkan *mod_rewrite*
1. Edit konfigurasi 000-default.
```
$ cd /etc/apache2/sites-enabled
$ sudo nano 000-default.conf
```
2. Tambahkan baris di dalam block ``<VirtualHost *:80>``.
```
...
<Directory /var/www/html>
Options Indexes FollowSymLinks MultiViews
	AllowOverride All
	Order allow,deny allow from all
</Directory>
...
```
3. Simpan (Ctrl+O) dengan nama yang sama (Enter).
4. Tutup file (Ctrl+X).
5. Restart apache.
```
$ sudo service apache2 restart
```



<!--## *Maintenance* (Opsional)-->


## Otomatisasi
Tidak dilakukan otomatisasi karena kebutuhan instalasi Subrion menyesuaikan web server masing-masing. Diperlukan konfigurasi untuk mengaktifkan *mod_rewrite*. Pengaturan nama database, username, dan password MySQL semestinya bisa dikustomisasi (tidak dibuat otomatis).

## Cara Pemakaian

- Tampilan aplikasi web

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/1.PNG)

- Fungsi-fungsi utama

1. Mengelola konten

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_1.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_2.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_3.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_4.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/page_5.PNG)


2. *Manage* Template

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/template_1.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/template_2.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/template_3.PNG)


3. *Manage* Plugin

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/plugin_1.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/plugin_2.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/plugin_3.PNG)

![](https://raw.githubusercontent.com/azmiiqbalgp/komdat_subrion/master/plugin_4.PNG)


## Pembahasan

- Kelebihan : 
1. Mudah dioperasikan
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

