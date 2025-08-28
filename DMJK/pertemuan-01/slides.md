---
theme: default
layout: center
background: /bg-dark.jpg
---

# Dasar Jaringan Komputer & Pengenalan Packet Tracer
### Minggu 1 - Mata Kuliah Desain dan Jaringan Komputer

<div v-click>

🌐 **Cisco Networking Academy**

</div>

---
layout: default
---

# Capaian Pembelajaran

<div v-click="1">

- **Memahami sejarah dan evolusi jaringan komputer** 📚

</div>

<div v-click="2">

- **Menguasai dasar jaringan komputer** 🖧

</div>

<div v-click="3">

  - Definisi, tujuan, jenis jaringan

</div>

<div v-click="4">

  - Komponen & topologi

</div>

<div v-click="5">

  - Model OSI vs TCP/IP

</div>

<div v-click="6">

- **Mengidentifikasi keuntungan mempelajari jaringan** 💡

</div>

<div v-click="7">

- **Mengenal tools simulasi Packet Tracer** 🔧

</div>

<div v-click="8">

- **Menganalisis dampak jaringan dalam kehidupan** 🌍

</div>

---
layout: default
---

# Sejarah Jaringan Komputer

<div class="grid grid-cols-2 gap-8 mt-6">

<!-- Konten Kiri -->
<div>

<div v-click="1">

## Era Awal (1960-1970an) 📡

</div>

<div v-click="2">

- **ARPANET (1969)**: Jaringan pertama, menghubungkan 4 universitas di AS

</div>

<div v-click="3">

- Tujuan awal: Berbagi sumber daya komputer yang mahal

</div>

<div v-click="4">

## Perkembangan Pesat (1980-1990an) 🚀

</div>

<div v-click="5">

- **Ethernet (1980)**: Standar LAN pertama

</div>

<div v-click="6">

- **TCP/IP (1983)**: Protokol standar internet

</div>

<div v-click="7">

- **World Wide Web (1991)**: Revolusi akses informasi

</div>

<div v-click="8">

*Timeline: ARPANET → Internet → World Wide Web → Era Digital*

</div>

</div>

<!-- Gambar Kanan -->
<div class="flex flex-col gap-4">

<div v-click="2" class="flex justify-center">
<img src="/arpanet-gambar1.jpg" alt="ARPANET Network Map" class="max-h-48 w-auto object-contain" />
</div>

<div v-click="6" class="flex justify-center">
<img src="/arpanet-gambar2.jpg" alt="ARPANET Evolution" class="max-h-48 w-auto object-contain" />
</div>

</div>

</div>

---
layout: default
---

# Apa Itu Jaringan Komputer?

<div v-click="1">

> 🌐 Kumpulan perangkat yang saling terhubung untuk berbagi sumber daya, data, dan layanan

</div>

<div v-click="2">

- **Contoh nyata**:

</div>

<div v-click="3">

  - 🏫 Jaringan kampus (LAN)

</div>

<div v-click="4">

  - 🌍 Internet (WAN global)

</div>

<div v-click="5">

  - 🖨️ Printer bersama di kantor

</div>

<div v-click="6">

  - 📱 Media sosial dan komunikasi digital

</div>

<div v-click="7">

*Konsep dasar: Konektivitas untuk berbagi dan komunikasi*

</div>

---
layout: default
---

# Jenis-Jenis Jaringan

<div class="grid grid-cols-2 gap-4">

<div v-click="1">

**PAN (Personal Area Network)** 📱
- Skala: 1-10 meter
- Contoh: Bluetooth, WiFi hotspot
- Kecepatan: 1-24 Mbps

</div>

<div v-click="2">

**LAN (Local Area Network)** 🏢
- Skala: 1 gedung/kampus
- Contoh: Jaringan lab komputer
- Kecepatan: 100 Mbps - 10 Gbps

</div>

<div v-click="3">

**MAN (Metropolitan Area Network)** 🏙️
- Skala: Dalam kota (10-50 km)
- Contoh: Jaringan ISP kota
- Kecepatan: 10-100 Gbps

</div>

<div v-click="4">

**WAN (Wide Area Network)** 🌍
- Skala: Global/antar negara
- Contoh: Internet
- Kecepatan: Bervariasi

</div>

</div>

---
layout: default
---

# Topologi Jaringan

<div class="grid grid-cols-2 gap-6">

<div v-click="1" class="text-center">
<img src="/topology-star.jpg" alt="Star" class="h-28 w-auto mx-auto mb-2" />
<div class="text-sm">
<strong>⭐ Star Topology</strong>
<div class="text-xs mt-1 leading-tight">
- Semua perangkat terhubung ke pusat<br>
✅ Mudah diperbaiki<br>
❌ Pusat rusak, semua mati
</div>
</div>
</div>

<div v-click="2" class="text-center">
<img src="/topology-bus.jpg" alt="Bus" class="h-28 w-auto mx-auto mb-2" />
<div class="text-sm">
<strong>🚌 Bus Topology</strong>
<div class="text-xs mt-1 leading-tight">
- Satu kabel utama untuk semua<br>
✅ Hemat kabel<br>
❌ Sering tabrakan data
</div>
</div>
</div>

<div v-click="3" class="text-center">
<img src="/topology-ring.jpg" alt="Ring" class="h-28 w-auto mx-auto mb-2" />
<div class="text-sm">
<strong>🔄 Ring Topology</strong>
<div class="text-xs mt-1 leading-tight">
- Bentuk lingkaran tertutup<br>
✅ Data mengalir teratur<br>
❌ Satu putus, semua terganggu
</div>
</div>
</div>

<div v-click="4" class="text-center">
<img src="/topology-mesh.jpg" alt="Mesh" class="h-28 w-auto mx-auto mb-2" />
<div class="text-sm">
<strong>🕷️ Mesh Topology</strong>
<div class="text-xs mt-1 leading-tight">
- Semua saling terhubung langsung<br>
✅ Sangat aman dari gangguan<br>
❌ Mahal dan rumit
</div>
</div>
</div>

</div>

---
layout: default
---

# Model OSI vs TCP/IP

<div class="grid grid-cols-2 gap-8 mt-8">

<div v-click="1" class="flex justify-center">
<img src="/gambar-osi1.jpg" alt="Model OSI 7 Layers" class="max-h-96 w-auto object-contain" />
</div>

<div v-click="2" class="flex justify-center">
<img src="/gambar-osi2.jpg" alt="Model TCP/IP 4 Layers" class="max-h-96 w-auto object-contain" />
</div>

</div>

---
layout: default
---

# Mengapa Mempelajari Jaringan Penting?

<div v-click="1">

## **💰 Peluang Karir Cemerlang**

</div>

<div v-click="2">

- **Network Engineer**: Rp 8-15 juta/bulan

</div>

<div v-click="3">

- **Network Security Analyst**: Rp 10-20 juta/bulan

</div>

<div v-click="4">

- **Cloud Network Architect**: Rp 15-30 juta/bulan

</div>

<div v-click="5">

## **🚀 Skill Masa Depan**

</div>

<div v-click="6">

- 🏠 Internet of Things (IoT)

</div>

<div v-click="7">

- ☁️ Cloud Computing

</div>

<div v-click="8">

- 🔒 Cybersecurity

</div>

<div v-click="9">

- 📡 5G dan teknologi wireless

</div>

<div v-click="10">

*Demand tinggi, supply masih terbatas!*

</div>

---
layout: default
---

# Keuntungan Menguasai Jaringan

<div class="grid grid-cols-2 gap-8">

<div>
<div v-click="1">
<h2 class="text-xl font-bold mb-4">🏢 Di Dunia Kerja</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="2">⚡ Troubleshoot koneksi cepat</div>
<div v-click="3">🏗️ Merancang infrastruktur IT</div>
<div v-click="4">📈 Optimasi performa aplikasi</div>
<div v-click="5">💼 Konsultan teknologi</div>
</div>
</div>

<div>
<div v-click="6">
<h2 class="text-xl font-bold mb-4">🏠 Kehidupan Sehari-hari</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="7">🌐 Memahami cara kerja internet</div>
<div v-click="8">🔐 Keamanan data pribadi</div>
<div v-click="9">🎮 Optimasi gaming/streaming</div>
<div v-click="10">📱 Setup jaringan rumah pintar</div>
</div>
</div>

</div>

<div v-click="11" class="text-center mt-6 italic text-gray-600">
Knowledge is power - terutama di era digital!
</div>

---
layout: default
---

# Pengenalan Packet Tracer

<div v-click="1">

## 🔧 **Apa itu Packet Tracer?**

</div>

<div v-click="2">

> Software simulasi jaringan dari Cisco untuk pembelajaran dan sertifikasi

</div>

<div v-click="3">

## 💡 **Mengapa Simulator?**

</div>

<div v-click="4">

- 💸 Hemat biaya (tanpa hardware fisik)

</div>

<div v-click="5">

- 🛡️ Eksperimen aman tanpa risiko

</div>

<div v-click="6">

- 📜 Persiapan sertifikasi CCNA

</div>

<div v-click="7">

- 🎯 Fokus pada konsep, bukan maintenance

</div>

<div v-click="8">

## ⚙️ **Fitur Utama**

</div>

<div v-click="9">

- 🖥️ Simulasi perangkat Cisco

</div>

<div v-click="10">

- 👀 Visualisasi alur data

</div>

<div v-click="11">

- 🧪 Lab virtual interaktif

</div>

---
layout: default
---

# Dampak Jaringan di Era Digital

<div class="grid grid-cols-2 gap-8">

<div>
<div v-click="1">
<h2 class="text-xl font-bold mb-4">🏭 Transformasi Industri</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="2">🛒 <strong>E-commerce</strong>: Shopee, Tokopedia</div>
<div v-click="3">📺 <strong>Streaming</strong>: Netflix, YouTube</div>
<div v-click="4">💼 <strong>Remote Work</strong>: Zoom, Teams</div>
<div v-click="5">💳 <strong>Fintech</strong>: GoPay, OVO, Banking</div>
</div>
</div>

<div>
<div v-click="6">
<h2 class="text-xl font-bold mb-4">👥 Perubahan Sosial</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="7">💬 Komunikasi global real-time</div>
<div v-click="8">📚 Akses pendidikan online</div>
<div v-click="9">🏥 Telemedicine & konsultasi virtual</div>
<div v-click="10">🤝 Social networking & communities</div>
</div>
</div>

</div>

<div v-click="11" class="text-center mt-6 italic text-gray-600">
Jaringan = fondasi revolusi digital
</div>

---
layout: default
---

# Tantangan dan Peluang Masa Depan

<div class="grid grid-cols-2 gap-8">

<div>
<div v-click="1">
<h2 class="text-xl font-bold mb-4">⚠️ Tantangan</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="2">🛡️ <strong>Keamanan Siber</strong>: Malware, phishing</div>
<div v-click="3">🔒 <strong>Privacy</strong>: Perlindungan data pribadi</div>
<div v-click="4">📊 <strong>Digital Divide</strong>: Kesenjangan akses</div>
<div v-click="5">⚡ <strong>Bandwidth</strong>: Demand vs capacity</div>
</div>
</div>

<div>
<div v-click="6">
<h2 class="text-xl font-bold mb-4">🌟 Peluang</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="7">📡 <strong>5G Networks</strong>: Ultra-high speed</div>
<div v-click="8">💻 <strong>Edge Computing</strong>: Local processing</div>
<div v-click="9">🤖 <strong>AI Networking</strong>: Smart automation</div>
<div v-click="10">🌐 <strong>SDN</strong>: Software-defined networks</div>
</div>
</div>

</div>

---
layout: default
---

# Statistik Menarik Jaringan Global

<div class="grid grid-cols-2 gap-8">

<div>
<div v-click="1">
<h2 class="text-xl font-bold mb-4">🇮🇩 Indonesia 2024</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="2">📱 <strong>212 juta</strong> pengguna internet</div>
<div v-click="3">📊 <strong>96%</strong> akses via mobile</div>
<div v-click="4">⏰ <strong>8+ jam</strong> online per hari</div>
<div v-click="5">💰 <strong>Rp 2.3T</strong> ekonomi digital</div>
</div>
</div>

<div>
<div v-click="6">
<h2 class="text-xl font-bold mb-4">🌍 Global</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="7">👥 <strong>5.16 miliar</strong> pengguna internet</div>
<div v-click="8">📈 <strong>59 zettabyte</strong> data per bulan</div>
<div v-click="9">🏠 <strong>50+ miliar</strong> perangkat IoT (2030)</div>
<div v-click="10">🚀 <strong>400%</strong> growth in 10 tahun</div>
</div>
</div>

</div>

<div v-click="11" class="text-center mt-6 italic text-gray-600">
Peluang besar di balik angka-angka ini!
</div>

---
layout: default
---

# Langkah Praktis Setelah Kuliah Ini

<div class="grid grid-cols-3 gap-6">

<div>
<div v-click="1">
<h2 class="text-lg font-bold mb-3">📅 Minggu Ini</h2>
</div>
<div class="text-xs space-y-1">
<div v-click="2">1. 💾 Install Packet Tracer</div>
<div v-click="3">2. 📝 Daftar Cisco NetAcad</div>
<div v-click="4">3. 🔬 Coba simulasi dasar</div>
<div v-click="5">4. 👥 Join komunitas networking</div>
</div>
</div>

<div>
<div v-click="6">
<h2 class="text-lg font-bold mb-3">🗓️ Bulan Ini</h2>
</div>
<div class="text-xs space-y-1">
<div v-click="7">• 💻 Pelajari Cisco CLI</div>
<div v-click="8">• 📖 Course "Intro to Networks"</div>
<div v-click="9">• 🎯 Practice lab scenarios</div>
<div v-click="10">• 📚 Baca networking blogs</div>
</div>
</div>

<div>
<div v-click="11">
<h2 class="text-lg font-bold mb-3">🎓 Semester Ini</h2>
</div>
<div class="text-xs space-y-1">
<div v-click="12">• 🏆 Target sertifikasi CCNA</div>
<div v-click="13">• 🔧 Lab dengan hardware</div>
<div v-click="14">• 💼 Cari magang IT/ISP</div>
<div v-click="15">• 🌟 Build networking portfolio</div>
</div>
</div>

</div>

---
layout: default
---

# Sumber Belajar Rekomendasi

<div class="grid grid-cols-2 gap-8">

<div>
<div v-click="1">
<h2 class="text-xl font-bold mb-4">🆓 Gratis</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="2">🎓 <strong>Cisco Networking Academy</strong></div>
<div v-click="3">📺 <strong>YouTube</strong>: NetworkChuck, David Bombal</div>
<div v-click="4">📝 <strong>Coursera</strong>: Computer Networks</div>
<div v-click="5">📖 <strong>Free books</strong>: Cisco Press samples</div>
</div>
</div>

<div>
<div v-click="6">
<h2 class="text-xl font-bold mb-4">💳 Berbayar (Worth it!)</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="7">🎯 <strong>Udemy</strong>: CCNA Complete Course</div>
<div v-click="8">📚 <strong>Pluralsight</strong>: Networking Path</div>
<div v-click="9">🏅 <strong>CBT Nuggets</strong>: Cisco Training</div>
<div v-click="10">🎪 <strong>Linux Academy</strong>: Cloud Networking</div>
</div>
</div>

</div>

<div class="mt-8">
<div v-click="11">
<h2 class="text-lg font-bold mb-3">💡 Pro Tips</h2>
</div>
<div class="text-sm space-y-2">
<div v-click="12">• Start with free resources, upgrade gradually</div>
<div v-click="13">• Practice > Theory (80/20 rule)</div>
<div v-click="14">• Join study groups dan forums</div>
</div>
</div>

---
layout: center
class: text-center
---

# Terima Kasih! 🙏

<div v-click="1">

## **Mari Mulai Perjalanan Networking Anda!** 🚀

</div>

<div v-click="2">

### Pertanyaan? 💬

</div>

<div class="mt-8">

<div v-click="3">

> *"The internet is becoming the town square for the global village of tomorrow."* 

</div>

<div v-click="4">

> **- Bill Gates**

</div>

</div>

<div v-click="5">

**Next Week**: Hands-on Packet Tracer Lab Session! 🔧

</div>