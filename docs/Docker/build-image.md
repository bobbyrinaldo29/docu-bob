---
title: Membuat Docker Image
description: Membuat Docker Image dari Dockerfile
---

Membuat Docker image melibatkan pembuatan serangkaian instruksi 
yang digunakan Docker untuk mengemas aplikasi beserta 
dependensinya menjadi unit yang portabel dan mandiri.

## Membuild Docker Image secara umum
Pastikan file Dockerfile sudah dibuat.

1. Buka Terminal dan arahkan path ketempat dimana Dockerfile berada.

2. Ketik perintah berikut untuk memulai build.
```bash
docker build -t <nama-image>:<tag-version> .
```
Contoh Penggunaan:
```bash
docker build -t ubuntu-php:latest .
```

## Membuat tag pada Docker Image
Gunakan versioning agar bisa men-track dan me-manage Docker Image dengan mudah.

### 1. Menggunakan Semantic Versioning (SemVer)
- Format: `MAJOR.MINOR.PATCH` (contoh: 1.0.0).
- Contoh Penggunaan:

    ```bash
    docker build -t bobbydev/myapp:1.0.0 .
    ```
    :::note Catatan
    Ubah `bobbydev` dengan user docker, dan ubah `myapp` dengan nama aplikasi.
    :::

### 2. Menggunakan Multiple Version untuk fleksibilitas
Tambahkan tag yang lebih luas untuk kenyamanan.

```bash
docker tag bobbydev/myapp:1.0.0 bobbydev/myapp:1.0
docker tag bobbydev/myapp:1.0.0 bobbydev/myapp:1
docker tag bobbydev/myapp:1.0.0 bobbydev/myapp:latest
```

### 3. Push semua tag ke Docker Hub
```bash
docker push bobbydev/myapp:1.0.0
docker push bobbydev/myapp:1.0
docker push bobbydev/myapp:1
docker push bobbydev/myapp:latest
```

## Best Practices
- Hindari menggunakan Image dengan Tag `latest` pada production.
- Gunakan Immutable tags (seperti commit hash atau timestamps).
- Tambahkan dokumentasi pada Readme di repo.