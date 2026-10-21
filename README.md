# Simulasi Jaringan Komputer Antargedung

## Deskripsi

Proyek ini adalah simulasi jaringan sederhana antara Gedung A dan Gedung B menggunakan Cisco Packet Tracer. Jaringan terdiri dari dua switch Cisco 2960 dan empat PC virtual dalam satu subnet, yaitu `192.168.1.0/24`. Simulasi dibuat menggunakan satu laptop; perangkat jaringan di dalam Packet Tracer bersifat virtual.

## Tujuan

- Menghubungkan perangkat di Gedung A dan Gedung B menggunakan dua switch.
- Mengatur alamat IP empat PC dalam satu subnet.
- Menguji koneksi antargedung menggunakan perintah `ping`.

## Perangkat dan Topologi

- Cisco Packet Tracer
- 2 switch Cisco 2960
- 4 PC virtual
- Kabel Copper Straight-Through

```text
Gedung A                         Gedung B
PC1 ──┐                          ┌── PC3
      ├── Switch A ───────────── Switch B ──┤
PC2 ──┘                          └── PC4
```

## Pembagian Alamat IP

| Perangkat | Lokasi | IP Address | Subnet Mask |
|---|---|---|---|
| PC1 | Gedung A | 192.168.1.1 | 255.255.255.0 |
| PC2 | Gedung A | 192.168.1.2 | 255.255.255.0 |
| PC3 | Gedung B | 192.168.1.3 | 255.255.255.0 |
| PC4 | Gedung B | 192.168.1.4 | 255.255.255.0 |

Default gateway dibiarkan kosong karena semua PC berada dalam satu subnet dan simulasi tidak menggunakan router.

## Langkah Simulasi

1. Buka Cisco Packet Tracer dan buat proyek baru melalui **File > New**.
2. Tambahkan dua switch Cisco 2960 dan empat PC ke area kerja.
3. Beri nama perangkat: Switch A, Switch B, PC1, PC2, PC3, dan PC4.
4. Hubungkan PC1 dan PC2 ke Switch A.
5. Hubungkan PC3 dan PC4 ke Switch B.
6. Hubungkan Switch A ke Switch B.
7. Gunakan kabel **Copper Straight-Through** dan port **FastEthernet**.
8. Atur alamat IP setiap PC melalui **Desktop > IP Configuration** sesuai tabel di atas. Pilih **Static** dan biarkan Default Gateway kosong.
9. Tunggu hingga indikator koneksi aktif dan berwarna hijau.

## Pengujian Koneksi

Dari PC1, buka **Desktop > Command Prompt**, kemudian jalankan:

```text
ping 192.168.1.3
ping 192.168.1.4
```

Koneksi berhasil jika PC tujuan memberikan balasan `Reply from ...`. Jika ping pertama gagal, jalankan kembali perintah ping.

## Pembagian Tugas Kelompok

| Anggota | Tugas |
|---|---|
| Zuli Arifin | Membuat topologi di Cisco Packet Tracer dan memberi nama perangkat serta lokasi gedung. |
| Nafran Julian | Menghubungkan kabel dan mengatur alamat IP pada PC1 sampai PC4. |
| Meriadi | Menguji koneksi dengan ping, mencatat hasil, dan membantu menyusun laporan. |
| Semua anggota | Memeriksa simulasi, menyimpan file proyek `.pkt`, dan menyiapkan presentasi. |

Simulasi dikerjakan menggunakan satu laptop. Anggota dapat bergantian mengoperasikan Packet Tracer; anggota lain membantu memeriksa konfigurasi, mencatat hasil, dan menyiapkan laporan.

## Troubleshooting

- **Koneksi kabel belum aktif:** periksa kabel dan port FastEthernet, lalu tunggu beberapa detik.
- **Ping gagal:** periksa kembali IP address dan subnet mask setiap PC, serta pastikan tidak ada alamat IP yang sama.
- **Ping pertama gagal:** ulangi perintah ping; perangkat mungkin sedang mencari alamat MAC melalui ARP.
- **PC antargedung tidak terhubung:** periksa kabel antara Switch A dan Switch B serta indikator link-nya.

## File Proyek

Simpan file simulasi Packet Tracer dengan nama `Jaringan_Antargedung.pkt`, lalu unggah bersama `README.md` ke repositori GitHub.
