---
title: Sintaks Dasar GIT
description: Sintaks-sintaks Dasar pada GIT
time: 2025-07-10
author: Sukma Dewa
tags: [git]
---

Berikut beberapa sintaks yang biasa digunakan pada GIT CLI.

### Inisialisasi GIT
Untuk memulai proyek baru dengan Git:
```bash
git init
```

### Download Repo
Mengunduh repositori yang sudah ada dari lokasi remote (misalnya GitHub) ke komputer lokal. 
Ini akan membuat folder baru dengan nama repositori tersebut.
```bash
git clone <url-repositori> <nama-repo-di-lokal>
```

Contoh penggunaan:
```bash
git clone https://github.com/bobbyrinaldo29/bobbyrinaldo29.git project-saya
```

:::note Catatan
Nama repo tidak disarankan menggunakan spasi
:::