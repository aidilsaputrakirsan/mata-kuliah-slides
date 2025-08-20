---
theme: default
title: SIM Tugas Akhir
mdc: true
---

# SIM Tugas Akhir / SITASI 
by Prodi Sistem Informasi

---
layout: center
---

# Masalah Tanpa SIM TA / Sitasi

```mermaid {theme: 'base', scale: 0.5}
flowchart LR
   A[📝 Mahasiswa Perlu Form TA] --> B[🖨️ Print Formulir Manual]
   B --> C{🔍 Mengisi Form}
   
   C --> D[❌ MASALAH 1:<br/>Ada Typo]
   C --> E[❌ MASALAH 2:<br/>Form Hilang]
   C --> F[❌ MASALAH 3:<br/>Waktu Tidak Efisien]
   C --> I[❌ MASALAH 4:<br/>Kecurangan/<br/>Pemalsuan TTD]
   C --> J[❌ MASALAH 5:<br/>Lupa Deadline<br/>Revisi 20 Hari]
   
   D --> G[😤 Mahasiswa Frustasi]
   E --> G
   F --> G
   I --> G
   J --> G
   
   G --> H[🎓 Terhambat Kelulusan]
   
   style A fill:#e1f5fe
   style B fill:#fff3e0
   style D fill:#ffebee
   style E fill:#ffebee
   style F fill:#ffebee
   style I fill:#ffebee
   style J fill:#ffebee
   style G fill:#fce4ec
   style H fill:#f3e5f5
```

<div 
  v-click="1" 
  v-motion
  :initial="{ y: 50, opacity: 0 }"
  :enter="{ y: 1, opacity: 1 }"
  class="mt-8 text-center"
>
</div>

---
layout: center
---

# Solusi dengan SIM TA / SITASI

```mermaid {theme: 'base', scale: 0.5}
flowchart LR
    A[📝 Mahasiswa Perlu Form TA] --> B[💻 Akses Sistem Digital]
    B --> C[📋 Isi Form Online]
    
    C --> D[✅ SOLUSI 1:<br/>Auto Validation<br/>Tidak Ada Typo]
    C --> E[✅ SOLUSI 2:<br/>Data Tersimpan Aman<br/>Tidak Hilang]
    C --> F[✅ SOLUSI 3:<br/>Proses Cepat<br/>Waktu Efisien]
    C --> I[✅ SOLUSI 4:<br/>TTD Digital by Sistem<br/>Tidak Bisa Dipalsukan]
    C --> J[✅ SOLUSI 5:<br/>Auto Hitung Deadline<br/>Notifikasi Otomatis]
    
    D --> G[🎯 Fokus Progress]
    E --> G
    F --> G
    I --> G
    J --> G
    
    G --> H[📈 Bimbingan Optimal]
    
    style A fill:#e1f5fe
    style B fill:#e8f5e8
    style C fill:#fff3e0
    style D fill:#e8f5e8
    style E fill:#e8f5e8
    style F fill:#e8f5e8
    style I fill:#e8f5e8
    style J fill:#e8f5e8
    style G fill:#f0f8ff
    style H fill:#e6ffe6
```

<div 
  v-click="1" 
  v-motion
  :initial="{ y: 50, opacity: 0 }"
  :enter="{ y: 0, opacity: 1 }"
  class="mt-8 text-center"
>

</div>  

---
layout: center
---

<img
  v-motion
  :initial="{ x: -200, opacity: 0 }"
  :enter="{ x: 0, opacity: 1 }"
  :click-1="{ scale: 1.2 }"
  :click-2="{ x: 100 }"
  :leave="{ x: 300, opacity: 0 }"
  src="/gambar1.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<img
  v-motion
  :initial="{ y: -150, opacity: 0 }"
  :enter="{ y: 0, opacity: 1 }"
  :click-1="{ rotate: 5, scale: 1.1 }"
  :click-2="{ rotate: -5, scale: 1.2 }"
  :click-3="{ rotate: 0, scale: 1 }"
  :leave="{ y: 200, opacity: 0 }"
  src="/gambar2.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<img
  v-motion
  :initial="{ scale: 0.5, opacity: 0 }"
  :enter="{ scale: 1, opacity: 1 }"
  :click-1="{ x: -100, y: -50 }"
  :click-2="{ x: 100, y: 50 }"
  :click-3="{ x: 0, y: 0, scale: 1.3 }"
  :leave="{ scale: 0, opacity: 0 }"
  src="/gambar3.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<img
  v-motion
  :initial="{ x: 300, opacity: 0 }"
  :enter="{ x: 0, opacity: 1 }"
  :click-1="{ scale: 1.1, rotate: 3 }"
  :click-2="{ scale: 1, rotate: 0 }"
  :leave="{ x: -300, opacity: 0 }"
  src="/gambar4.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<img
  v-motion
  :initial="{ y: 200, opacity: 0 }"
  :enter="{ y: 0, opacity: 1 }"
  :click-1="{ y: -50, scale: 1.15 }"
  :click-2="{ y: 0, scale: 1 }"
  :leave="{ y: -200, opacity: 0 }"
  src="/gambar5.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---
<div class="relative">
<img
  v-motion
  :initial="{ scale: 0, rotate: 180, opacity: 0 }"
  :enter="{ scale: 1, rotate: 0, opacity: 1 }"
  :click-1="{ scale: 1.2 }"
  :click-2="{ rotate: 10, scale: 1.1 }"
  :click-3="{ rotate: 0, scale: 1 }"
  :leave="{ scale: 0, rotate: -180, opacity: 0 }"
  src="/gambar6.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>
 <!-- Satu marker besar di tengah -->
 <div
    v-click="1"
    v-mark.circle.red
    class="absolute w-105 h-35 bg-opacity-30"
    style="top: 240px; left: 150px;"
    ></div>
  </div>

---
layout: center
---

<img
  v-motion
  :initial="{ x: -400, y: -200, opacity: 0 }"
  :enter="{ x: 0, y: 0, opacity: 1 }"
  :click-1="{ x: 150, y: -100 }"
  :click-2="{ x: -150, y: 100 }"
  :click-3="{ x: 0, y: 0, scale: 1.25 }"
  :leave="{ x: 400, y: 200, opacity: 0 }"
  src="/gambar7.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<img
  v-motion
  :initial="{ scale: 2, opacity: 0 }"
  :enter="{ scale: 1, opacity: 1 }"
  :click-1="{ rotate: -5, scale: 1.1 }"
  :click-2="{ rotate: 5, scale: 1.1 }"
  :click-3="{ rotate: 0, scale: 1 }"
  :leave="{ scale: 0.3, opacity: 0 }"
  src="/gambar8.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<img
  v-motion
  :initial="{ y: -300, x: 200, opacity: 0 }"
  :enter="{ y: 0, x: 0, opacity: 1 }"
  :click-1="{ scale: 1.3, rotate: 2 }"
  :click-2="{ scale: 1, rotate: 0, y: 50 }"
  :click-3="{ y: 0 }"
  :leave="{ y: 300, x: -200, opacity: 0 }"
  src="/gambar9.png"
  class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
/>

---
layout: center
---

<div class="relative">
 <img
   v-motion
   :initial="{ scale: 0.3, rotate: 90, opacity: 0 }"
   :enter="{ scale: 1, rotate: 0, opacity: 1 }"
   :click-1="{ x: -100, scale: 1.15 }"
   :click-2="{ x: 100, scale: 1.15 }"
   :click-3="{ x: 0, scale: 1.4 }"
   :leave="{ scale: 0.3, rotate: -90, opacity: 0 }"
   src="/gambar10.png"
   class="w-full h-full object-contain max-h-screen rounded-lg shadow-xl"
 />
 
 <!-- Satu marker besar di tengah -->
 <div
    v-click="1"
    v-mark.circle.red
    class="absolute w-55 h-35 bg-opacity-30"
    style="top: 220px; left: 100px;"
    ></div>
</div>

