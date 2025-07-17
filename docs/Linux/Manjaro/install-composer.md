---
title: Install Composer
description: Install Composer PHP
time: 2025-07-17
author: Sukma Dewa
tags: [linux, php]
---

Composer adalah tools dependency manager pada PHP, Dependency (ketergantungan) sendiri diartikan ketika project PHP yang kamu kerjakan masih membutuhkan atau memerlukan library dari luar. Composer berfungsi sebagai penghubung antara project PHP kamu dengan library dari luar.

## Prerequisites
Pastikan sistem operasi sudah ter-update dan juga PHP sudah terinstall. [Klik disini](install-php) untuk menginstall PHP.

1. Ambil installer Composer dan mengeksekusinya menggunakan php
```bash
curl -sS https://getcomposer.org/installer | php
```

2. Pindahkan file `composer.phar` ke `/usr/local/bin/composer`
```bash
sudo mv composer.phar /usr/local/bin/composer
```

3. Untuk mengkonfirmasi apakah composer sudah terinstall gunakan perintah berikut.
```bash
composer --version
```