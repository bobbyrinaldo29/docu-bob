# Docker
Docker adalah sebuah platform perangkat lunak open-source yang merevolusi cara aplikasi dibuat, 
dikemas, didistribusikan, dan dijalankan. Intinya, Docker menggunakan teknologi kontainerisasi 
untuk membungkus aplikasi beserta semua dependensinya (kode, runtime, system tools, libraries, 
dan settings) ke dalam satu unit standar yang disebut kontainer.

## Sintaks Dasar docker
Berikut beberapa sintaks yang biasa digunakan pada docker CLI


### Pull Image
Dalam Docker, "pull image" (menarik image) adalah perintah yang digunakan untuk 
mengunduh (download) Docker image dari sebuah Docker Registry ke Docker daemon lokal Anda.

Sebelum membuat sebuah container pada local, kita harus mendownload Image terlebih dahulu.
```bash
docker pull {nama_image}:{tag_version}
```
Contoh penggunaan:
```bash
docker pull sdewa29/ubuntu-php53:latest
```

### Menampilkan Image
Untuk mengecek image yang sudah di pull/download bisa menggunakan perintah berikut:
```bash
docker image ls
```

Jika Image sudah berhasil terdownload akan muncul seperti berikut:
```bash
REPOSITORY             TAG       IMAGE ID       CREATED         SIZE
sdewa29/ubuntu-php53   latest    530f0ec84e1a   18 months ago   305MB
```

:::note Catatan
`IMAGE ID` ditiap komputer akan berbeda-beda.
:::


### Membuat container
Kontainer (Container) adalah sebuah unit standar yang dapat dieksekusi, 
yang berisi semua yang dibutuhkan oleh sebuah aplikasi untuk berjalan: 
kode, runtime, alat sistem, pustaka, dan pengaturan.

Secara umum membuat kontainer bisa dengan perintah berikut:
```bash
docker run [IMAGE]:[TAG] --name <nama-container>
```
:::note Catatan
- `docker run` : Perintah untuk membuat dan memulai kontainer baru.
- `IMAGE` : Nama Docker image yang akan digunakan sebagai dasar untuk kontainer.
- `TAG` : Bisa tambahkan tag jika ingin menggunakan image yang lebih spesifik.
- `--name` : Nama pada sebuah kontainer tidak boleh menggunakan spasi.
:::


Pembuatan kontainer bisa juga dengan menggunakan perintah berikut:

```bash
docker container create [OPTIONS] [IMAGE_ID] --name <nama-container>
```
:::note Catatan
- `[OPTIONS]` : perintah optional yang mengubah perilaku kontainer.
- `[IMAGE_ID]` : Ini didapat dari perintah `docker image ls`.
- `--name <nama-container>` : Nama pada sebuah kontainer tidak boleh menggunakan spasi.
:::


### Menampilkan Container
Untuk menampilkan kontainer yang sudah dibuat.
```bash
docker container ls
# atau bisa juga menggunakan perintah:
docker ps -a
```


## Perintah-perintah Optional
Untuk mengubah perilaku kontainer bisa menambahankan `[OPTIONS]` atau perintah optional.
berikut perintah-perintah optional yang bisa ditambahkan pada sintaks:

### Menjalankan Kontainer di Latar Belakang (Detached Mode)
Seringkali kita ingin kontainer berjalan terus-menerus tanpa mengikat terminal.
- `-d` atau `--detach`
	<br/>Menjalankan kontainer dalam "detached mode" (mode terpisah), 
	artinya kontainer akan berjalan di latar belakang dan Anda akan mendapatkan kembali prompt terminal Anda. 
	Docker akan mencetak ID kontainer setelah berhasil memulai.
	
Contoh Penggunaan:
```bash
docker container create -d [IMAGE_ID]
```

### Memberi nama kontainer
Memberi nama pada kontainer memudahkan identifikasi dan pengelolaan.
- `--name kontainer-saya`
	<br/>Memberi nama kontainer "kontainer-saya". Jika tidak menggunakan option ini
	maka docker akan menggunakan nama secara acak.
	
Contoh Penggunaan:
```bash
docker container create --name kontainer-saya [IMAGE_ID]
```
:::note Catatan
Tidak diperbolehkan menggunakan spasi pada nama kontainer.
:::

### Memberi Port kontainer
Membuat PORT secara spesifik antara HOST dan kontainer.
- `-p <host-port>:<container-port>`

Contoh Penggunaan:
```bash
docker container create -p 8053:80 [IMAGE_ID]
```

### Memasang Volume (Sharing Data)
Untuk membuat data di dalam kontainer persisten atau berbagi data antara host dan kontainer.

- `-v` atau `--volume <host-path>:<container-path>`

Contoh Penggunaan:
```bash
docker container create -v /home/user/sites/:/var/www/html/ [IMAGE_ID]
```

### Menjalankan Kontainer Interaktif (dengan Shell)
Berguna untuk debugging atau menjelajahi isi kontainer.

- `-i` atau `--interactive` 
	<br/>Menjaga STDIN (input standar) tetap terbuka, bahkan jika tidak terhubung.
- `-t` atau `--tty`
	<br/>Mengalokasikan pseudo-TTY, yang memungkinkan Anda berinteraksi dengan shell 
	kontainer seolah-olah itu adalah terminal biasa.
- `bash`
	<br/>Perintah yang akan dijalankan di dalam kontainer, yaitu membuka shell Bash.
	
Contoh Penggunaan:
```bash
docker exec -it <nama-container> bash
```
