---
title: Install PHP
description: Install PHP
time: 2025-07-17
author: Sukma Dewa
tags: [linux, php]
---

PHP adalah singkatan dari Hypertext Preprocessor, yakni sebuah bahasa scripting yang dibuat oleh 
Rasmus Lerdorf pada tahun 1994 untuk membuat halaman, website, aplikasi web, 
dan Graphical User Interface (GUI).

1. Update sistem operasi menggunakan perintah berikut
```bash
sudo pacman -Syu
```

2. Install PHP
```bash
sudo pacman -S php
```

:::note Catatan
Manjaro akan menginstall PHP dengan versi terbaru yang ada dalam repositorinya.
:::

3. Install Ekstensi PHP (Opsional tapi direkomendasikan untuk di install).
    - php-apache: Jika kamu menggunakan Apache untuk webserver.
    - php-fpm: Jika kamu menggunakan Nginx atau ingin menggunakan PHP-FPM dengan apache untuk performa yang lebih baik.
    - php-gd: Untuk manipulasi gambar.
    - php-mysqli or php-pdo_mysql: Untuk koneksi MySQL/MariaDB database.
    - php-curl: untuk membuat HTTP requests.
    - php-mbstring: Untuk fungsi multi-byte string.
    - php-intl: Untuk internationalization.
    - php-zip: Untuk menggunakan zip archives.
    - php-json: Untuk menghandle JSON.
    - php-xml: Untuk menghandle XML.

Kamu bisa menginstall paket-paket diatas dengan cara berikut
```bash
sudo pacman -S php-gd php-intl php-apache php-fpm

```

4. Konfigurasi PHP
Konfigurasi PHP biasanya disimpan di `/etc/php/php.ini`. Kamu perlu mengubah baris kode
untuk mengaktifkan ekstensi PHP. sebagai contoh, untuk mengaktifkan ekstensi `gd` bisa
dengan melakukan perubahan pada baris berikut.
```bash
;extension=gd
```

Ubah menjadi
```bash
extension=gd
```

:::note Catatan
Lakukan hal yang sama jika ingin mengaktifkan ekstensi yang lainnya.
:::