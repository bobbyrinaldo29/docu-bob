---
title: Install ZSH
description: Install ZSH
time: 2025-07-17
author: Sukma Dewa
tags: [linux, terminal, zsh]
---

Z shell (Zsh) adalah sebuah Unix shell yang dapat digunakan sebagai login shell yang interaktif dan sebagai penerjemah perintah yang kuat untuk shell scripting.

## Langkah-langkal instalasi

1. Install ZSH
```bash
sudo pacman -Syu zsh
```
:::note Catatan
Pastikan untuk meng-update repository terlebih dahulu sebelum instalasi.
:::

2. Set ZSH sebagai default shell
```bash
chsh -s $(which zsh)
```
:::note Catatan
Lakukan Logout/Restart PC agar terminal berubah dari SHELL ke ZSH.
:::

3. Untuk memverifikasi apakah sudah berubah lakukan perintah berikut
```bash
echo $SHELL
```

4. Install `Oh My Zsh` (opsional tapi di rekomendasikan) dan menginstall 
beberapa tema, plugin, dll.
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
atau menggunakan `wget`
```bash
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

5. Pasang Plugin tambahan
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

6. edit file `~/.zshrc` dan ubah baris `plugin`
```bash
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

7. Muat ulang perubahan yang sudah diubah tadi.
```bash
source ~/.zshrc
```

8. Opsional: gunakan tema seperti Powerlevel10k
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```