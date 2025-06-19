# Install Docker Engine

Sebelum memulai cek system requirement agar bisa menginstall docker [cek disini.](https://docs.docker.com/engine/install/ubuntu/#prerequisites)

Pastikan Sistem Operasi dalam keadaan up to date.
```bash
sudo apt -y update
```

Ada beberapa dependensi yang perlu kita konfigurasi untuk repositori Docker dan melakukan instalasi paket yang sebenarnya. 
Instal dependensi tersebut dengan menjalankan perintah berikut di terminal:
```bash
sudo apt -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```
:::note Catatan
Jika sudah ada versi Docker yang lebih lama, hapus versi tersebut beserta paket-paket dependensinya.
```bash
sudo apt remove docker docker-engine docker.io containerd runc
```
:::


Import Docker repository GPG key:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-archive-keyring.gpg
```

Tambahkan repositori Docker CE ke Ubuntu:
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Lalu install docker:
```bash
sudo apt update
```
```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```

Setelah berhasil aktifkan docker service:
```bash
sudo systemctl enable docker && sudo systemctl start docker
```

Tambahkan akun pengguna ke grup docker
```bash
sudo usermod -aG docker $USER
```
```bash
newgrp docker
```

Verifikasi docker dengan perintah berikut:
```bash
docker ps -a
```
