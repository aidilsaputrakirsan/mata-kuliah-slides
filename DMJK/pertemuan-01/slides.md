---
theme: default
layout: center
background: /bg-dark.jpg
---

# Dasar Jaringan Komputer & Pengenalan Packet Tracer
### Minggu 1 - Mata Kuliah Desain dan Jaringan Komputer

![logo](/cisco-logo.png) <!-- CARI GAMBAR: "Cisco Logo PNG transparan" -->

---
layout: default
---

# Agenda Hari Ini

- **Dasar Jaringan Komputer**
  - Definisi, tujuan, jenis jaringan
  - Komponen & topologi
  - Model OSI vs TCP/IP
- **Pengenalan Packet Tracer**
  - Fitur dan antarmuka
  - Simulasi jaringan dasar
- Rekomendasi gambar untuk presentasi

---
layout: default
---

# Apa Itu Jaringan Komputer?

> Kumpulan perangkat yang saling terhubung untuk berbagi sumber daya, data, dan layanan

- **Contoh nyata**:
  - Jaringan kampus (LAN)
  - Internet (WAN global)
  - Printer bersama di kantor

![jaringan-dasar](/network-basics.jpg) <!-- CARI GAMBAR: "Ilustrasi jaringan komputer sederhana di kantor" -->

---
layout: default
---

# Jenis-Jenis Jaringan

| Tipe | Skala | Contoh |
|------|-------|--------|
| **LAN** | Lokal (1 gedung) | Jaringan lab komputer |
| **WAN** | Global | Internet |
| **MAN** | Kota | Jaringan ISP kota |
| **PAN** | Pribadi | Bluetooth headset |

![jenis-jaringan](/lan-wan-man-pan.jpg) <!-- CARI GAMBAR: "Perbandingan skala LAN WAN MAN PAN ilustrasi" -->

---
layout: default
---

# Topologi Jaringan

- **Star**: Semua perangkat terhubung ke switch/router pusat
- **Bus**: Kabel utama menghubungkan semua perangkat
- **Ring**: Struktur melingkar
- **Mesh**: Koneksi langsung antar-perangkat

![topologi](/network-topologies.jpg) <!-- CARI GAMBAR: "Diagram 4 topologi jaringan (star, bus, ring, mesh) berdampingan" -->

---
layout: default
---

# Model OSI vs TCP/IP

| OSI (7 Lapisan) | TCP/IP (4 Lapisan) |
|-----------------|--------------------|
| Application     | Application        |
| Presentation    |                    |
| Session         |                    |
| Transport       | Transport          |
| Network         | Internet           |
| Data Link       | Network Interface  |
| Physical        |                    |

![osi-tcpip](/osi-tcpip-comparison.jpg) <!-- CARI GAMBAR: "Tabel perbandingan model OSI dan TCP/IP" -->

---
layout: default
---

# Apa Itu Packet Tracer?

> Software simulasi jaringan dari Cisco untuk:
> - Merancang topologi virtual
> - Mengkonfigurasi perangkat
> - Menguji alur data

**Fitur utama**:
- Simulasi tanpa hardware fisik
- Persiapan sertifikasi CCNA
- Analisis lalu lintas jaringan

![packet-tracer-logo](/packet-tracer-logo.png) <!-- CARI GAMBAR: "Packet Tracer logo resmi Cisco" -->

---
layout: default
---

# Antarmuka Packet Tracer

![interface](/packet-tracer-ui.jpg) <!-- CARI GAMBAR: "Tampilan antarmuka Packet Tracer dengan label toolbar dan workspace" -->

- **Workspace**: Area desain topologi
- **Toolbar**: Pilihan perangkat & kabel
- **Mode**:
  - *Realtime*: Konfigurasi perangkat
  - *Simulation*: Analisis alur paket

---
layout: default
---

# Simulasi Jaringan Sederhana

Langkah membuat jaringan LAN:
1. Tambahkan 2 PC dan 1 switch
2. Sambungkan dengan kabel **Straight-through**
3. Konfigurasi IP address:
```bash
PC0> ipconfig 192.168.1.10 255.255.255.0
PC1> ipconfig 192.168.1.11 255.255.255.0
```
4. Uji koneksi:
```bash
PC0> ping 192.168.1.11
```

![simulasi](/pt-lan-simulation.jpg) <!-- CARI GAMBAR: "Contoh konfigurasi IP dan ping di Packet Tracer" -->

---
layout: default
---

# Tips Praktis Packet Tracer

- Gunakan **Auto Connect** untuk koneksi cepat
- Perhatikan warna kabel:
  - Hijau = koneksi aktif
  - Merah = kesalahan konfigurasi
- Ekspor konfigurasi sebagai `.pkt` untuk presentasi

![tips](/pt-tips.jpg) <!-- CARI GAMBAR: "Ilustrasi warna kabel di Packet Tracer (hijau/merah)" -->

---
layout: center
class: text-center
---

# Rekomendasi Gambar Tambahan

1. **Cari di Google**:
   - `"Packet Tracer simulation mode alur paket"`
   - `"Perbedaan kabel straight-through crossover"`
   - `"Contoh jaringan mesh di lingkungan kota"`

2. **Format file**:
   - PNG transparan untuk logo
   - JPG resolusi tinggi untuk diagram

![summary](/search-tips.jpg) <!-- CARI GAMBAR: "Screenshot pencarian Google Images dengan kata kunci spesifik" -->

---
layout: center
class: text-center
---

# Terima Kasih

## Praktikkan Konsep Ini di Packet Tracer!
### Pertanyaan? 💬

![qna](/qna-time.jpg) <!-- CARI GAMBAR: "Ilustrasi sesi tanya jawab kreatif" -->
```

---
