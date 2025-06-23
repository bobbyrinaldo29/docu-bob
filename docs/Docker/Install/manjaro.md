---
title: Manjaro
description: Install Docker Engine di Linux Manjaro
---

# Install Docker Engine di Linux Manjaro

## Instalasi
Sebelum memulai cek system requirement agar bisa menginstall Docker.

Pastikan Sistem Operasi dalam keadaan up to date.
```bash
sudo pacman -Syu
```

Install Docker
```bash
sudo pacman -S docker
```

Setelah instalasi selesai, mulai dan aktifkan service Docker.
```bash
sudo systemctl start docker.service
sudo systemctl enable docker.service
```

Untuk memverifikasi apakah Docker sudah terinstall, bisa
lakukan perintah berikut:
```bash
sudo docker version
```

## Jalankan Docker tanpa Root
Secara default, kita harus menggunakan user `Root` setiap kita akan
menggunakan perintah Docker. Untuk itu kita perlu merubah hak akses
agar bisa menjalankan perintah Docker dengan user yang sedang aktif.

Tambahkan akun kedalam grup Docker dengan perintah berikut:
```bash
sudo usermod -aG docker $USER
```

Lalu `Restart` PC dengan perintah:
```bash
reboot
```