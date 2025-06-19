# Install OpenVPN 3 pada Ubuntu

1. Pastikan `apt-transport-https` dan `curl` sudah terinstall di sistem.
```bash
sudo apt install apt-transport-https curl -y
```

2. Tambahkan repository OpenVPN3
```bash
sudo mkdir -p /etc/apt/keyrings && curl -fsSL https://packages.openvpn.net/packages-repo.gpg | sudo tee /etc/apt/keyrings/openvpn.asc
```

3. Tambahkan repo OpenVPN 3 kedalan Source List
```bash
echo "deb [signed-by=/etc/apt/keyrings/openvpn.asc] https://packages.openvpn.net/openvpn3/debian noble main" | sudo tee /etc/apt/sources.list.d/openvpn-packages.list
```
:::note Catatan
Pastikan repo sesuai dengan versi Ubuntu
:::

4. Update paket aplikasi
```bash
sudo apt update
```

5. Install OpenVPN 3
```bash
sudo apt install openvpn3 -y
```

6. Install OpenVPN Data Channel Offload (DCO) (Opsional, untuk performa)
```bash
sudo apt install openvpn-dco-dkms -y
```

7. Import file konfigurasi profile OpenVPN
```bash
openvpn3 config-import --config /path/to/your/profile.ovpn --name YourVPNProfileName
```
:::note Catatan
- ganti `/path/to/your/profile.ovpn` dengan path file ovpn nya.
- ganti `YourVPNProfileName` dengan nama vpn sesuai keinginan.
:::

8. Cek list konfigurasi
```bash
openvpn3 configs-list
```

9. Koneksikan VPN
```bash
openvpn3 session-start --config YourVPNProfileName
```

untuk cek apakah sudah terkoneksi atau belum bisa dengan menggunakan perintah:
```bash
openvpn3 sessions-list
```

10. Diskonek VPN
```bash
openvpn3 session-manage --config YourVPNProfileName --disconnect
```