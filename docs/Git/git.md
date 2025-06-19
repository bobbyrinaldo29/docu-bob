# GIT
GIT adalah sebuah sistem kontrol versi terdistribusi (Distributed Version Control System - DVCS) 
yang dirancang untuk melacak perubahan pada file dan mengkoordinasikan pekerjaan di antara banyak 
orang yang mengerjakan proyek yang sama. Ini berarti setiap pengembang memiliki salinan lengkap 
dari seluruh riwayat proyek di komputer lokal mereka, tidak hanya versi terbaru.


## Sintaks Dasar GIT
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
