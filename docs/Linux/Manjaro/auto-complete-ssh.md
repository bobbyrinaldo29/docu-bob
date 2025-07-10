# Auto Complete SSH

Jika autocomplete pada ssh tidak berjalan (seperti `ssh sta<TAB>` untuk kata `staging`)
di Linux Manjaro, lakukan pengecekan seperti berikut:

1. Pastikan `bash-completion` sudah ter-install
```bash
pacman -Qs bash-completion
```

Jika belum ter-install, install dengan perintah berikut:
```bash
sudo pacman -S bash-completion
```

2. Tambahkan di paling bawah Source Code Completion pada file `~/.bashrc`, jika belum ada.
```bash
[[ $PS1 && -f /usr/share/bash-completion/bash_completion ]] && \
    . /usr/share/bash-completion/bash_completion
```

Save perubahan tersebut dan lakukan reload terminal dengan cara:
```bash
source ~/.bashrc
```

3. Cek Shell pada terminal
Pastikan Shell yang kamu menggunakan `bash` atau `zsh`, bukan seperti `sh` atau `dash`.
Kamu bisa mengeceknya dengan cara berikut:
```bash
echo $SHELL
```

4. Cek konfig ssh
Lakukan pengecekan dengan menggunakan perintah ssh seperti
```bash
ssh sta<TAB> untuk kata `staging`
```

Jika masih tidak muncul, kemungkinan script SSH Completion kamu tidak ter-load.
Bisa lakukan dengan cara manual
```bash
source /usr/share/bash-completion/completions/ssh
```