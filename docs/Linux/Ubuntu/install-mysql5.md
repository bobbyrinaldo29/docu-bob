# Install MySQL 5.5.45

## Download
1. Download paket aplikasi
```bash
wget https://downloads.mysql.com/archives/get/p/23/file/mysql-5.5.45-debian6.0-x86_64.deb
```

## Instalasi
1. Install paket aplikasi
```bash
sudo dpkg -i mysql-5.5.45-debian6.0-x86_64.deb
```

:::note Catatan
Jika terjadi error seperti berikut pada saat dump SQL
```bash
mysqldump: Error: 'Access denied; you need (at least one of) the PROCESS privilege(s) for this operation' when trying to dump tablespaces
```

lakukan perintah berikut
```bash
mysqldump --no-tablespaces -u youruser -p yourdatabase > backup.sql
```
:::
