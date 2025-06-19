# Global User
Untuk mengatur nama pengguna dan email Git secara global (agar semua commit Git menggunakan identitas ini secara default), 
jalankan perintah berikut di terminal:
```bash
git config --global user.name "username"
```

```bash
git config --global user.email "email@example.com"
```

## Untuk Memverifikasi
```bash
git config --global --list
```

## Menyimpan Kredensial Sementara
```bash
git config --global credential.helper cache
```

atau bisa menggunakan
```bash
git config --global credential.helper 'cache --timeout=3600'
```

:::note Catatan
'cache --timeout=3600' akan menyimpan kredensial selama 1 jam.
:::


## Menghapus Konfigurasi Lokal
Jika ingin menghapus konfigurasi di repository saat ini saja, hilangkan opsi --global:
```bash
git config --global --unset user.name "username"
```

```bash
git config --global --unset user.email "email@example.com"
```

## Memverifikasi Setelah Unset
Untuk mengecek apakah konfigurasi sudah terhapus:
```bash
git config --global --list
```
atau untuk lokal
```bash
git config --list
```
