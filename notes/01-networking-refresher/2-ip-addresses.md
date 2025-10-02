# Module 1 – Networking Refresher

## Section: IP Address

IP Address itu ibarat **alamat rumah** buat device di jaringan/internet → biar bisa saling nemuin & komunikasi.

Ada **dua versi utama**:

- **IPv4** (versi lama, masih banyak dipake)
- **IPv6** (versi baru, muncul karena IPv4 udah mepet)

---

### IPv4

- Format: **32-bit**, ditulis **decimal pake titik**. Contoh: `192.168.0.1`
- Dibagi jadi 4 blok (**octet**), masing2 8 bit → range 0–255.
- Total alamat: **±4.3 miliar**.
- Masalah: makin banyak device online → alamat IPv4 **nyaris abis**.

---

### IPv6

- Format: **128-bit**, ditulis **hex pake titik dua**.  
  Contoh: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
- Dibagi jadi 8 grup, masing2 4 digit hex.
- Bisa disingkat:
  - `0370` → `370` (leading zero dihapus)
  - `0000:0000` → `::` (grup nol berturut-turut)
- Total alamat: **3.4 × 10^38** (nggak bakal habis).
- Plus fitur tambahan: security (IPsec), auto config, routing lebih oke.

---

### Public IP vs Private IP

- **Public IP** → alamat yang keliatan di internet (unik, bisa diakses langsung).
- **Private IP** → alamat internal (dipake di LAN). Contoh range:
  - `10.0.0.0 – 10.255.255.255`
  - `172.16.0.0 – 172.31.255.255`
  - `192.168.0.0 – 192.168.255.255`
- Private IP nggak langsung bisa ke internet → biasanya lewat **NAT (Network Address Translation)**.

---

### Transisi IPv4 → IPv6

- Ga bisa langsung switch, karena **dua-duanya ga kompatibel**.
- Solusi:
  - **Dual stack** (jalanin IPv4 & IPv6 barengan).
  - **Tunneling** (IPv6 dikirim dalam IPv4).
  - **Translation** (kayak NAT64, nerjemahin antar protokol).

---

### Kesimpulan versi gw

- IPv4 udah cukup lama dipake, tapi alamatnya terbatas → makanya muncul IPv6.
- IPv6 itu bukan sekadar versi lebih panjang, tapi juga bawa fitur tambahan.
- Public vs Private IP penting buat ngerti konsep internet vs jaringan lokal.
- Pentester/hacker wajib ngerti bedanya, karena sering main di **private IP (internal network)** waktu attack simulation, tapi juga harus ngerti cara ekspos ke **public IP**.
