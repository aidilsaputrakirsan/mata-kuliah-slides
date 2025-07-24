---
theme: seriph
background: https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=1920
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Pemrograman Mobile - Week 1
  Introduction to Mobile Development dengan React Native
drawings:
  persist: false
transition: slide-left
title: Introduction to Mobile Development
mdc: true
layout: cover
---

# Introduction to Mobile Development 📱

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Pemrograman Mobile - Week 1 <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
transition: fade-out
layout: center
---

# Selamat Datang! 👋

<div v-motion
  :initial="{ x: -80, opacity: 0}"
  :enter="{ x: 0, opacity: 1, transition: { delay: 500, duration: 1000 } }">
  
## Mari Berkenalan

<br>

<div class="grid grid-cols-2 gap-8 pt-4">
  <div v-click class="border-2 border-blue-400 rounded-lg p-6 hover:bg-blue-900/20 transition-all">
    <mdi-account-circle class="text-5xl text-blue-400 mb-2"/>
    <h3>Tentang Saya</h3>
    <p class="text-sm opacity-75">Dosen Pemrograman Mobile</p>
  </div>
  
  <div v-click class="border-2 border-green-400 rounded-lg p-6 hover:bg-green-900/20 transition-all">
    <mdi-school class="text-5xl text-green-400 mb-2"/>
    <h3>Tentang Kalian</h3>
    <p class="text-sm opacity-75">Mahasiswa Semester 5-6</p>
  </div>
</div>

</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: center
class: text-center
---

# Quick Poll 🤔

<div class="text-6xl mb-8" v-motion
  :initial="{ scale: 0 }"
  :enter="{ scale: 1, transition: { duration: 500 } }">
  📱
</div>

<div v-click="1" class="mb-6">
  <h2>Siapa yang pakai Android?</h2>
</div>

<div v-click="2" class="mb-6">
  <h2>Siapa yang pakai iPhone?</h2>
</div>

<div v-click="3">
  <h2 class="text-yellow-400">Aplikasi favorit kalian apa?</h2>
</div>

<div v-click="4" class="mt-8 text-2xl text-green-400">
  ✨ Semester ini kita akan belajar membuat aplikasi seperti itu! ✨
</div>

---
transition: slide-up
---

# Why Mobile Development? 🚀

<div class="grid grid-cols-2 gap-8">
  <div>
    <h2 v-motion
      :initial="{ x: -100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1 }">
      📊 Fakta Menarik Indonesia
    </h2>
    
    <div v-click="1" v-motion
      :initial="{ x: -100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1, transition: { delay: 200 } }">
      <div class="text-4xl text-blue-400">170+ Juta</div>
      <p class="text-sm">Pengguna Smartphone</p>
    </div>

    <div v-click="2" v-motion
      :initial="{ x: -100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1, transition: { delay: 400 } }">
      <div class="text-4xl text-green-400 mt-4">96x/hari</div>
      <p class="text-sm">Rata-rata cek HP</p>
    </div>

    <div v-click="3" v-motion
      :initial="{ x: -100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1, transition: { delay: 600 } }">
      <div class="text-4xl text-yellow-400 mt-4">$935 Billion</div>
      <p class="text-sm">Mobile Apps Industry (2023)</p>
    </div>
  </div>

  <div v-click="4">
    <h2 v-motion
      :initial="{ x: 100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1 }">
      💼 Peluang Karir
    </h2>
    
    <div class="space-y-4 mt-6">
      <div v-for="i in 3" :key="i" v-motion
        :initial="{ x: 100, opacity: 0 }"
        :enter="{ x: 0, opacity: 1, transition: { delay: 400 + i * 200 } }"
        class="flex items-center space-x-3 bg-gradient-to-r from-blue-500/20 to-transparent p-3 rounded-lg">
        <span class="text-2xl">{{ ['🎯', '💰', '🌟'][i-1] }}</span>
        <span>{{ ['Selalu dibutuhkan', 'Gaji kompetitif', 'Portfolio bernilai'][i-1] }}</span>
      </div>
    </div>
  </div>
</div>

---
layout: two-cols
transition: fade
---

# Web vs Mobile App 🌐📱

<v-clicks>

<div class="pr-8">
  <h3 class="text-blue-400 mb-4">🌐 Web Application</h3>
  
  <div class="space-y-3">
    <div class="flex items-start">
      <mdi-numeric-1-circle class="text-xl mr-2 text-gray-400"/>
      <span>Buka browser</span>
    </div>
    <div class="flex items-start">
      <mdi-numeric-2-circle class="text-xl mr-2 text-gray-400"/>
      <span>Ketik alamat website</span>
    </div>
    <div class="flex items-start">
      <mdi-numeric-3-circle class="text-xl mr-2 text-gray-400"/>
      <span>Gunakan aplikasi</span>
    </div>
  </div>
</div>

</v-clicks>

::right::

<v-clicks>

<div class="pl-8">
  <h3 class="text-green-400 mb-4">📱 Mobile Application</h3>
  
  <div class="space-y-3">
    <div class="flex items-start">
      <mdi-numeric-1-circle class="text-xl mr-2 text-gray-400"/>
      <span>Download dari Store</span>
    </div>
    <div class="flex items-start">
      <mdi-numeric-2-circle class="text-xl mr-2 text-gray-400"/>
      <span>Install di HP</span>
    </div>
    <div class="flex items-start">
      <mdi-numeric-3-circle class="text-xl mr-2 text-gray-400"/>
      <span>Tap icon, langsung jalan!</span>
    </div>
  </div>
</div>

</v-clicks>

---
layout: center
---

# Keunggulan Mobile App ⚡

<div class="grid grid-cols-2 gap-6 mt-8">
  <div v-for="(feature, i) in features" :key="i"
    v-motion
    :initial="{ scale: 0, rotate: -180 }"
    :enter="{ scale: 1, rotate: 0, transition: { delay: i * 100 } }"
    class="bg-gradient-to-br from-blue-500/20 to-purple-500/20 p-6 rounded-xl border border-blue-500/50 hover:scale-105 transition-transform cursor-pointer">
    <div class="text-4xl mb-2">{{ feature.icon }}</div>
    <h3 class="text-lg font-bold mb-1">{{ feature.title }}</h3>
    <p class="text-sm opacity-75">{{ feature.desc }}</p>
  </div>
</div>

<script setup>
const features = [
  { icon: '📴', title: 'Akses Offline', desc: 'Bekerja tanpa internet' },
  { icon: '🔔', title: 'Push Notification', desc: 'Kirim pesan langsung' },
  { icon: '📸', title: 'Hardware Access', desc: 'Kamera, GPS, Sensor' },
  { icon: '⚡', title: 'Performa Cepat', desc: 'Native performance' }
]
</script>

---
transition: slide-left
---

# Native vs Cross-Platform 🎯

<div class="mt-8">
  <div v-click class="mb-8 p-6 bg-blue-500/10 rounded-lg border-2 border-blue-500/50">
    <h3 class="text-2xl mb-4 text-blue-400">🏠 Native Development</h3>
    <p class="mb-4">Seperti berbicara bahasa lokal - setiap platform punya bahasanya sendiri</p>
    <div class="flex justify-around items-center">
      <div class="text-center">
        <mdi-android class="text-6xl text-green-500"/>
        <p>Java/Kotlin</p>
      </div>
      <mdi-arrow-right class="text-3xl"/>
      <div class="text-center">
        <mdi-android class="text-6xl text-green-500"/>
        <p>App Android</p>
      </div>
    </div>
  </div>

  <div v-click class="p-6 bg-purple-500/10 rounded-lg border-2 border-purple-500/50">
    <h3 class="text-2xl mb-4 text-purple-400">🌍 Cross-Platform</h3>
    <p class="mb-4">Seperti bahasa Inggris - satu bahasa untuk semua</p>
    <div class="flex justify-around items-center">
      <div class="text-center">
        <mdi-language-javascript class="text-6xl text-yellow-500"/>
        <p>JavaScript</p>
      </div>
      <mdi-arrow-right class="text-3xl"/>
      <div class="text-center space-x-4">
        <span>
          <mdi-android class="text-6xl text-green-500 inline"/>
          <mdi-apple class="text-6xl text-gray-400 inline"/>
        </span>
        <p>Android + iOS</p>
      </div>
    </div>
  </div>
</div>

---
layout: image-right
image: https://images.unsplash.com/photo-1551650975-87deedd944c3?w=1920
---

# Kenapa React Native? 🚀

<v-clicks depth="2">

- ### 📚 Sudah Kenal JavaScript
  Tidak perlu belajar bahasa baru!

- ### 🏢 Perusahaan Besar Pakai
  - Facebook & Instagram
  - Airbnb & UberEats
  - Discord & Pinterest

- ### 🇮🇩 Komunitas Indonesia Aktif
  Mudah cari bantuan & tutorial

- ### ⚡ Satu Code, Dua Platform
  Hemat waktu development 50%!

</v-clicks>

<div v-click class="mt-8 p-4 bg-green-500/20 rounded-lg border border-green-500">
  <p class="text-center font-bold">Perfect untuk yang sudah belajar Web! 🎯</p>
</div>

---
transition: fade
---

# Apa yang Akan Kita Buat? 🛠️

<div class="grid grid-cols-2 gap-6">
  <div v-for="(project, i) in projects" :key="i"
    v-click
    v-motion
    :initial="{ y: 100, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: i * 200 } }"
    class="relative overflow-hidden rounded-xl bg-gradient-to-br from-blue-600/20 to-purple-600/20 p-6 border border-blue-500/50 hover:scale-105 transition-all">
    <div class="text-5xl mb-3">{{ project.icon }}</div>
    <h3 class="text-xl font-bold mb-2">{{ project.title }}</h3>
    <p class="text-sm opacity-75">{{ project.desc }}</p>
    <span class="absolute top-2 right-2 text-xs bg-blue-500/50 px-2 py-1 rounded">{{ project.week }}</span>
  </div>
</div>

<script setup>
const projects = [
  { 
    icon: '✅', 
    title: 'Todo List App', 
    desc: 'CRUD operations, state management',
    week: 'Week 2-3'
  },
  { 
    icon: '🌤️', 
    title: 'Weather App', 
    desc: 'API integration, real-time data',
    week: 'Week 4-5'
  },
  { 
    icon: '📸', 
    title: 'Mini Instagram', 
    desc: 'Image handling, social features',
    week: 'Week 6-7'
  },
  { 
    icon: '🚀', 
    title: 'Final Project', 
    desc: 'Tim project, aplikasi lengkap!',
    week: 'Week 9-15'
  }
]
</script>

---
layout: center
---

# Tools yang Dibutuhkan 🧰

<div class="text-center mb-8">
  <p class="text-2xl text-yellow-400">Ibaratkan seperti memasak! 👨‍🍳</p>
</div>

<div class="grid grid-cols-2 gap-8 max-w-4xl mx-auto">
  <div v-for="(tool, i) in tools" :key="i"
    v-click
    v-motion
    :initial="{ scale: 0 }"
    :enter="{ scale: 1, transition: { type: 'spring', delay: i * 200 } }"
    class="flex items-center space-x-4 bg-gradient-to-r from-indigo-500/20 to-purple-500/20 p-6 rounded-xl hover:from-indigo-500/30 hover:to-purple-500/30 transition-all">
    <div class="text-5xl">{{ tool.icon }}</div>
    <div>
      <h3 class="text-xl font-bold">{{ tool.name }}</h3>
      <p class="text-sm opacity-75">{{ tool.analogy }}</p>
    </div>
  </div>
</div>

<div v-click class="mt-12 text-center">
  <p class="text-xl text-green-400 animate-pulse">
    🎉 Jangan khawatir, kita install bareng-bareng! 🎉
  </p>
</div>

<script setup>
const tools = [
  { icon: '🔥', name: 'Node.js', analogy: 'Kompor (runtime)' },
  { icon: '📝', name: 'VS Code', analogy: 'Pisau & talenan (editor)' },
  { icon: '📦', name: 'Expo', analogy: 'Rice cooker (tools)' },
  { icon: '📱', name: 'Smartphone', analogy: 'Piring untuk testing' }
]
</script>

---
transition: slide-up
layout: center
---

# Live Demo Time! 🎪

<div class="text-center">
  <div v-motion
    :initial="{ scale: 0 }"
    :enter="{ scale: 1 }"
    class="text-8xl mb-8">
    🎭
  </div>

  <div class="space-y-6">
    <div v-click v-motion
      :initial="{ x: -100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1 }">
      <h2 class="text-3xl text-blue-400">Step 1: Buka aplikasi yang sudah jadi</h2>
    </div>

    <div v-click v-motion
      :initial="{ x: 100, opacity: 0 }"
      :enter="{ x: 0, opacity: 1 }">
      <h2 class="text-3xl text-green-400">Step 2: Ubah "Hello" → "Halo Mahasiswa"</h2>
    </div>

    <div v-click v-motion
      :initial="{ scale: 0, rotate: 360 }"
      :enter="{ scale: 1, rotate: 0 }">
      <h2 class="text-3xl text-yellow-400">Step 3: Save & Refresh</h2>
    </div>

    <div v-click class="pt-8">
      <div v-motion
        :initial="{ scale: 0 }"
        :enter="{ scale: 1, transition: { type: 'spring' } }"
        class="inline-block p-6 bg-gradient-to-r from-pink-500 to-violet-500 rounded-xl text-white">
        <p class="text-2xl font-bold">✨ Langsung berubah! ✨</p>
        <p class="text-lg mt-2">Hot Reload = Developer Happy 😊</p>
      </div>
    </div>
  </div>
</div>

---
layout: default
---

# Ekspektasi Mata Kuliah 📋

<div class="grid grid-cols-2 gap-8 mt-8">
  <div v-click v-for="(item, i) in expectations" :key="i"
    v-motion
    :initial="{ x: i % 2 === 0 ? -100 : 100, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: i * 100 } }"
    class="bg-gradient-to-br from-cyan-500/20 to-blue-500/20 p-6 rounded-xl border border-cyan-500/50 hover:from-cyan-500/30 hover:to-blue-500/30 transition-all">
    <div class="text-4xl mb-3">{{ item.icon }}</div>
    <h3 class="text-xl font-bold mb-2 text-cyan-400">{{ item.title }}</h3>
    <p class="text-sm">{{ item.desc }}</p>
  </div>
</div>

<script setup>
const expectations = [
  { 
    icon: '🧮', 
    title: 'Tidak perlu jago matematika', 
    desc: 'Logic thinking > Mathematical formulas' 
  },
  { 
    icon: '🏃', 
    title: 'Learning by Doing', 
    desc: '70% praktek, 30% teori' 
  },
  { 
    icon: '💪', 
    title: 'Mistakes are OK', 
    desc: 'Salah itu wajar, yang penting coba!' 
  },
  { 
    icon: '👥', 
    title: 'Team Work', 
    desc: 'Final project berkelompok 3-4 orang' 
  }
]
</script>

---
transition: fade
---

# Assessment Overview 📊

<div class="mt-8">
  <div v-for="(item, i) in assessments" :key="i"
    v-click
    class="mb-4">
    <div class="flex items-center mb-2">
      <span class="text-2xl mr-3">{{ item.icon }}</span>
      <span class="text-xl font-bold">{{ item.name }}</span>
      <span class="ml-auto text-2xl font-bold text-yellow-400">{{ item.percentage }}%</span>
    </div>
    <div class="w-full bg-gray-700 rounded-full h-6 overflow-hidden">
      <div 
        class="h-full rounded-full transition-all duration-1000 bg-gradient-to-r"
        :class="item.color"
        v-motion
        :initial="{ width: '0%' }"
        :enter="{ width: item.percentage + '%', transition: { delay: 500 + i * 200 } }">
      </div>
    </div>
  </div>
</div>

<div v-click class="mt-8 p-6 bg-green-500/20 rounded-xl border border-green-500">
  <p class="text-center text-xl">
    <mdi-lightbulb class="text-2xl text-yellow-400"/> 
    Tips: Konsisten mengerjakan tugas mingguan = 20% nilai sudah aman! 
  </p>
</div>

<script setup>
const assessments = [
  { icon: '📝', name: 'Tugas Mingguan', percentage: 20, color: 'from-blue-500 to-cyan-500' },
  { icon: '📊', name: 'UTS', percentage: 25, color: 'from-green-500 to-emerald-500' },
  { icon: '👥', name: 'Progress Project', percentage: 15, color: 'from-purple-500 to-pink-500' },
  { icon: '📱', name: 'Final Project', percentage: 30, color: 'from-orange-500 to-red-500' },
  { icon: '🎤', name: 'Presentasi', percentage: 10, color: 'from-indigo-500 to-purple-500' }
]
</script>

---
layout: center
class: text-center
---

# Let's Start Coding! 🚀

<div v-motion
  :initial="{ scale: 0 }"
  :enter="{ scale: 1, transition: { type: 'spring' } }"
  class="text-8xl mb-8 animate-bounce">
  💻
</div>

<div class="space-y-4">
  <h2 class="text-3xl">Praktikum Hari Ini:</h2>
  
  <div v-click v-for="(step, i) in steps" :key="i"
    v-motion
    :initial="{ x: -50, opacity: 0 }"
    :enter="{ x: 0, opacity: 1, transition: { delay: i * 200 } }"
    class="text-xl">
    <span class="text-green-400 font-bold">{{ i + 1 }}.</span> {{ step }}
  </div>
</div>

<div v-click class="mt-12 p-6 bg-gradient-to-r from-purple-500/20 to-pink-500/20 rounded-xl">
  <h3 class="text-2xl mb-2 text-yellow-400">📚 Homework:</h3>
  <p>Download 3 aplikasi React Native dari Play Store</p>
  <p class="text-sm opacity-75">(Instagram, Discord, Pinterest, dll)</p>
</div>

<script setup>
const steps = [
  'Install Node.js (bareng-bareng)',
  'Install VS Code',
  'Install Expo Go di HP',
  'Buat "Hello World" pertama',
  'Jalankan di HP masing-masing!'
]
</script>

---
layout: end
class: text-center
---

# Ready to Build Amazing Apps? 🎯

<div class="text-6xl mb-8" v-motion
  :initial="{ scale: 0, rotate: -360 }"
  :enter="{ scale: 1, rotate: 0, transition: { duration: 1000 } }">
  🏆
</div>

<div class="text-2xl mb-8" v-motion
  :initial="{ y: 50, opacity: 0 }"
  :enter="{ y: 0, opacity: 1, transition: { delay: 500 } }">
  <p class="mb-4">Semester ini kita akan berubah</p>
  <p class="text-3xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 to-pink-500">
    dari USER menjadi CREATOR!
  </p>
</div>

<div v-click class="mt-12">
  <p class="text-xl text-green-400 animate-pulse">
    See you next week! 👋
  </p>
</div>

<style>
@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}
</style>

---
layout: none
class: flex items-center justify-center h-full
---

<div class="text-center">
  <h1 class="text-6xl font-bold mb-8 text-transparent bg-clip-text bg-gradient-to-r from-purple-400 to-pink-600 animate-pulse">
    Q&A Time! 🤔
  </h1>
  
  <div class="text-2xl space-y-4" v-motion
    :initial="{ scale: 0 }"
    :enter="{ scale: 1, transition: { delay: 500 } }">
    <p>Ada pertanyaan?</p>
    <p class="text-yellow-400">Jangan malu bertanya!</p>
  </div>
  
  <div class="mt-12 text-8xl animate-bounce">
    💬
  </div>
</div>

<style>
@keyframes gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.animate-gradient {
  background-size: 200% 200%;
  animation: gradient 3s ease infinite;
}
</style>