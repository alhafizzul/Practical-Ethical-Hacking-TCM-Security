# Module 1 – Networking Refresher

## Section: MAC Address

Kalau sebelumnya **IP Address** mainnya di **Layer 3 (Network Layer)**, sekarang kita turun ke bawah → **MAC Address** ada di **Layer 2 (Data Link Layer)**.

---

### Apa itu MAC Address?

- **MAC (Media Access Control) Address** = alamat **unik** yang nempel ke setiap **NIC (Network Interface Card)** di device.
- Bentuknya **alamat hardware** (dipasang langsung sama pabrikan ke firmware/ROM).
- Tujuan: biar data di jaringan lokal (LAN) nyampe ke **device yang tepat**.

---

### Format MAC Address

- Panjang: **48-bit**.
- Biasanya ditulis: **6 pasang angka hex** (0–9, A–F), dipisah pake `:` atau `-`.
  - Contoh: `00:1A:2B:3C:4D:5E`
- Pembagiannya:
  - **3 pasang pertama** → kode pabrikan (**OUI – Organizationally Unique Identifier**)
  - **3 pasang terakhir** → identitas unik device.

👉 Jadi misalnya lo cek di `ifconfig` atau `ip a` → di bagian `ether`, itu adalah **MAC Address**.  
Contoh real: pernah dicek di video, MAC address yang muncul ternyata punya **VMware** (ketahuan via MAC lookup tool di internet).

---

### Fungsi MAC Address

- Dipake di **Ethernet Frame** sebagai **Source MAC** & **Destination MAC**.
- Switch / router di LAN make ini buat mutusin data harus dilempar ke device mana.
- Berlaku **lokal aja (LAN scope)** → kalau data mau keluar internet, baru mainnya **IP Address** (Layer 3).

---

### Catatan Penting

- Semua device yang bisa connect ke jaringan (PC, laptop, HP, IoT, VM, dll) **pasti punya MAC address**.
- MAC address itu **hardware-based** dan **relatif permanen**, tapi bisa di-**spoof** (diganti secara software).
- Beda sama **IP Address**:
  - **IP** bisa berubah-ubah (dinamis via DHCP atau di-set manual).
  - **MAC** biasanya tetap (hardware).

---

### Kesimpulan versi gw

- MAC = alamat fisik unik buat device, posisinya di **Layer 2**.
- Jadi kalo IP itu buat komunikasi antar jaringan (global), MAC itu buat komunikasi antar device di jaringan lokal.
- Pabrikan device bisa diidentifikasi dari MAC → berguna banget pas investigasi / pentest buat tau "ini device aslinya apa?".
