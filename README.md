# Tugas-1-Jarkom_Salsa-Bil-Ulla_052

## Screenshot Topologi dengan Subnetting dan Supernetting
<img width="1135" height="666" alt="Screenshot 2025-11-13 120913" src="https://github.com/user-attachments/assets/c9b28f2a-31a9-4862-b48b-7676b7a84921" />

## Tabel VLSM
| Subnet | Needed Host | Mask | Block Size | Prefix | Network Address | Broadcast Address | Gateway | End of Host Range | Usable Hosts |
|--------|-------------|------|------------|--------|-----------------|-------------------|---------|-------------------|-------------|
| Sekretariat | 380 | 255.255.254.0 | 512 | /23 | 10.92.0.0 | 10.92.1.255 | 10.92.0.1 | 10.92.1.254 | 510 |
| Kurikulum | 220 | 255.255.255.0 | 256 | /24 | 10.92.2.0 | 10.92.2.255 | 10.92.2.1 | 10.92.2.254 | 254 |
| Guru & Tendik | 95 | 255.255.255.128 | 128 | /25 | 10.92.3.0 | 10.92.3.127 | 10.92.3.1 | 10.92.3.126 | 126 |
| Sarana Prasarana | 45 | 255.255.255.192 | 64 | /26 | 10.92.3.128 | 10.92.3.191 | 10.92.3.129 | 10.92.3.190 | 62 |
| Server & Admin | 6 | 255.255.255.248 | 8 | /29 | 10.92.3.224 | 10.92.3.231 | 10.92.3.225 | 10.92.3.230 | 6 |
| Link antar-router<br>(Pusat ↔ Cabang) | 2 | 255.255.255.252 | 4 | /30 | 10.92.3.232 | 10.92.3.235 | RouterPusat: 10.92.3.233<br>RouterCabang: 10.92.3.234 | - | 2 |
| Pengawas (Cabang) | 18 | 255.255.255.224 | 32 | /27 | 10.92.4.0 | 10.92.4.31 | 10.92.4.1 | 10.92.4.30 | 30 |

## Tabel CIDR
| Label | Subnet | Mask | Prefix | Network Address | Broadcast Address | Gateway | Range Host (Usable) |
|-------|--------|------|--------|-----------------|-------------------|---------|---------------------|
| A1 | Sekretariat | 255.255.254.0 | /23 | 10.92.0.0 | 10.92.1.255 | 10.92.0.1 | 10.92.0.1 – 10.92.1.254 |
| A2 | Kurikulum | 255.255.255.0 | /24 | 10.92.2.0 | 10.92.2.255 | 10.92.2.1 | 10.92.2.1 – 10.92.2.254 |
| A3 | Guru & Tendik | 255.255.255.128 | /25 | 10.92.3.0 | 10.92.3.127 | 10.92.3.1 | 10.92.3.1 – 10.92.3.126 |
| A4 | Sarana & Prasarana | 255.255.255.192 | /26 | 10.92.3.128 | 10.92.3.191 | 10.92.3.129 | 10.92.3.129 – 10.92.3.190 |
| A5 | Server / Admin | 255.255.255.248 | /29 | 10.92.3.224 | 10.92.3.231 | 10.92.3.225 | 10.92.3.225 – 10.92.3.230 |
| A6 | Link Router<br>Pusat–Cabang | 255.255.255.252 | /30 | 10.92.3.232 | 10.92.3.235 | Router Pusat: 10.92.3.233<br>Router Cabang: 10.92.3.234 | 10.92.3.233 – 10.92.3.234 |
| A7 | Pengawas (Cabang) | 255.255.255.224 | /27 | 10.92.4.0 | 10.92.4.31 | 10.92.4.1 | 10.92.4.1 – 10.92.4.30 |

## Tabel Supernet
| Label | Mencakup Subnet | Mask | Prefix | Network (Supernet) | Broadcast | Range Host (Usable) | Keterangan |
|-------|------------------|------|--------|---------------------|-----------|---------------------|------------|
| B1 | A1–A5<br>(LAN di Router Pusat) | 255.255.252.0 | /22 | 10.92.0.0 | 10.92.3.255 | 10.92.0.1 – 10.92.3.254 | Supernet LAN Pusat<br>(semua LAN di router pusat) |
| C1 | A1–A7<br>(Seluruh jaringan Pusat + Cabang) | 255.255.248.0 | /21 | 10.92.0.0 | 10.92.7.255 | 10.92.0.1 – 10.92.7.254 | Supernet seluruh jaringan<br>(pusat + cabang) |
