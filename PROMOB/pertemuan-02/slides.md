---
theme: default
background: '#ffffff'
title: React Native Fundamentals - Week 2
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## React Native Fundamentals - Week 2
  Pemrograman Mobile - Aidil Saputra Kirsan, M.Tr.Kom
drawings:
  persist: false
transition: slide-left
mdc: true
---

# React Native Fundamentals
## Pemrograman Mobile - Week 2

<div class="pt-8">
  <div class="text-gray-600">Mata Kuliah: Pemrograman Mobile</div>
  <div class="text-gray-600">Materi: Core Components & Styling</div>
  <div class="text-gray-600">Durasi: 3 jam praktikum</div>
</div>

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-4 py-2 rounded cursor-pointer border border-gray-300 hover:border-gray-500">
    Mari Pelajari Fundamental React Native →
  </span>
</div>

---

# Tujuan Pembelajaran Week 2

Setelah praktikum ini, mahasiswa mampu:

<v-clicks>

- **Memahami** core components React Native (View, Text, Image, ScrollView)
- **Menerapkan** styling dengan StyleSheet secara efektif
- **Membuat** layout responsive dengan Flexbox
- **Membangun** UI profile card yang profesional
- **Membuat** layout kalkulator sederhana
- **Memahami** perbedaan styling React Native vs CSS web

</v-clicks>

<div class="absolute bottom-4 left-4 text-xs text-gray-500">
Prerequisites: Hasil Week 1 (environment setup & project HelloWorld)
</div>

---

# Ringkasan Week 1

<div class="grid grid-cols-2 gap-8 pt-6">

<div>
<h3 class="font-bold mb-4">Yang Sudah Dikuasai:</h3>
<ul class="text-sm space-y-2">
<li>✅ Environment React Native dengan Expo</li>
<li>✅ Project structure dengan Expo Router</li>
<li>✅ Aplikasi Hello World pertama</li>
<li>✅ Testing di smartphone dan browser</li>
<li>✅ Konsep dasar mobile development</li>
</ul>
</div>

<div>
<h3 class="font-bold mb-4">Siap untuk Week 2:</h3>
<ul class="text-sm space-y-2">
<li>📱 Mempelajari komponen React Native</li>
<li>🎨 Menguasai sistem styling</li>
<li>📐 Memahami layout dengan Flexbox</li>
<li>🏗️ Membangun UI yang kompleks</li>
<li>⚡ Optimasi performa styling</li>
</ul>
</div>

</div>

<div class="pt-8 text-center">

<v-click>
<div class="border border-gray-300 inline-block px-6 py-3 rounded">
<span class="font-medium">Foundation sudah siap. Mari bangun UI yang menarik!</span>
</div>
</v-click>

</div>

---

# Komponen Web vs React Native

<div class="pt-4">

<div class="bg-gray-100 p-4 rounded text-sm font-mono mb-6">
```
WEB HTML                    REACT NATIVE
┌─────────────────┐        ┌─────────────────┐
│ <div>           │   →    │ <View>          │
│ <p>, <span>     │   →    │ <Text>          │
│ <img>           │   →    │ <Image>         │
│ <button>        │   →    │ <TouchableOpacity>│
│ <input>         │   →    │ <TextInput>     │
│ <div overflow>  │   →    │ <ScrollView>    │
└─────────────────┘        └─────────────────┘
```
</div>

<div class="grid grid-cols-3 gap-6 text-sm">

<v-click>
<div>
<h4 class="font-bold mb-2">Mengapa Berbeda?</h4>
<ul class="space-y-1">
<li>• Optimasi untuk mobile</li>
<li>• Interaksi sentuh native</li>
<li>• Akses API platform</li>
<li>• Performa lebih baik</li>
</ul>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-2">Keuntungan:</h4>
<ul class="space-y-1">
<li>• Native look & feel</li>
<li>• Touch gestures</li>
<li>• Smooth animations</li>
<li>• Platform consistency</li>
</ul>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-2">Learning Curve:</h4>
<ul class="space-y-1">
<li>• Konsep sama dengan React</li>
<li>• Nama komponen berbeda</li>
<li>• Props dan events serupa</li>
<li>• Mudah beradaptasi</li>
</ul>
</div>
</v-click>

</div>

</div>

---

# 6 Komponen Inti React Native

<div class="space-y-6 pt-4">

<v-click>
<div class="grid grid-cols-3 gap-4 text-sm">
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">View</h4>
<p class="text-gray-600">Container dasar, seperti div di HTML</p>
</div>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Text</h4>
<p class="text-gray-600">Menampilkan teks, support styling</p>
</div>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Image</h4>
<p class="text-gray-600">Menampilkan gambar lokal/remote</p>
</div>
</div>
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-4 text-sm">
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">ScrollView</h4>
<p class="text-gray-600">Container scrollable untuk konten panjang</p>
</div>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">TextInput</h4>
<p class="text-gray-600">Input field untuk user input</p>
</div>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">TouchableOpacity</h4>
<p class="text-gray-600">Button dengan opacity feedback</p>
</div>
</div>
</v-click>

</div>

<div class="pt-8">

<v-click>
<div class="bg-gray-100 p-4 rounded text-xs font-mono">
```jsx
import { View, Text, Image, ScrollView, TextInput, TouchableOpacity } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.title}>Komponen React Native</Text>
      <Image source={{uri: 'https://example.com/image.jpg'}} style={styles.image} />
      <TextInput placeholder="Ketik sesuatu..." style={styles.input} />
      <TouchableOpacity style={styles.button}>
        <Text>Tekan Saya</Text>
      </TouchableOpacity>
    </View>
  );
}
```
</div>
</v-click>

</div>

---

# StyleSheet vs CSS: Perbedaan Penting

<div class="grid grid-cols-2 gap-8 pt-4">

<v-click>
<div>
<h4 class="font-bold mb-3">CSS Web</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```css
.container {
  display: flex;
  justify-content: center;
  background-color: #ffffff;
  margin-top: 20px;
  border-radius: 8px;
}

.title {
  font-size: 18px;
  font-weight: bold;
  color: #333333;
}
```
</div>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-3">React Native StyleSheet</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```javascript
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    backgroundColor: '#ffffff',
    marginTop: 20,
    borderRadius: 8,
  },
  title: {
    fontSize: 18,
    fontWeight: 'bold',
    color: '#333333',
  }
});
```
</div>
</div>
</v-click>

</div>

<div class="pt-6">

<v-click>
<div class="grid grid-cols-3 gap-4 text-sm">
<div class="text-center">
<h5 class="font-bold">Sintaks</h5>
<p class="text-gray-600">Objek JavaScript vs CSS rules</p>
</div>
<div class="text-center">
<h5 class="font-bold">Properties</h5>
<p class="text-gray-600">camelCase vs kebab-case</p>
</div>
<div class="text-center">
<h5 class="font-bold">Units</h5>
<p class="text-gray-600">Unitless numbers vs px, em, rem</p>
</div>
</div>
</v-click>

</div>

---

# Flexbox di React Native

<div class="pt-4">

<div class="bg-gray-100 p-4 rounded text-sm font-mono mb-6">
```
WEB (flex-direction: row)      REACT NATIVE (flexDirection: 'column')
┌─────────────────────────┐    ┌─────────────────────────┐
│ [Item 1] [Item 2] [Item 3] │    │ [Item 1]              │
│                           │    │ [Item 2]              │
│                           │    │ [Item 3]              │
└─────────────────────────┘    └─────────────────────────┘
       DEFAULT WEB                    DEFAULT MOBILE
```
</div>

<div class="grid grid-cols-2 gap-8">

<v-click>
<div>
<h4 class="font-bold mb-3">Perbedaan Kritis:</h4>
<ul class="text-sm space-y-2">
<li>• <strong>Default direction:</strong> column (bukan row)</li>
<li>• <strong>Main axis:</strong> vertikal secara default</li>
<li>• <strong>Cross axis:</strong> horizontal secara default</li>
<li>• <strong>flex: 1</strong> mengisi ruang tersedia</li>
</ul>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-3">Properti Penting:</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```javascript
flexDirection: 'row' | 'column'
justifyContent: 'center' | 'flex-start'
alignItems: 'center' | 'stretch'
flex: 1 // mengisi ruang tersedia
flexWrap: 'wrap' | 'nowrap'
```
</div>
</div>
</v-click>

</div>

</div>

---

# Contoh Layout Patterns

<div class="pt-4">

<div class="bg-gray-100 p-4 rounded text-sm font-mono mb-6">
```
justifyContent: 'center'       alignItems: 'center'
┌─────────────────────────┐    ┌─────────────────────────┐
│                         │    │            [X]          │
│           [X]           │    │                         │
│                         │    │                         │
└─────────────────────────┘    └─────────────────────────┘

flexDirection: 'row'           flex: 1 (mengisi ruang)
┌─────────────────────────┐    ┌─────────────────────────┐
│ [1]    [2]    [3]       │    │ [Header]                │
│                         │    │ [Content - flex: 1]     │
└─────────────────────────┘    │ [Footer]                │
                               └─────────────────────────┘
```
</div>

<div class="grid grid-cols-2 gap-8 text-sm">

<v-click>
<div>
<h4 class="font-bold mb-3">Pattern Center Content:</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```javascript
container: {
  flex: 1,
  justifyContent: 'center',
  alignItems: 'center',
}
```
</div>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-3">Pattern Header-Content-Footer:</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```javascript
container: { flex: 1 },
header: { height: 60 },
content: { flex: 1 },
footer: { height: 50 },
```
</div>
</div>
</v-click>

</div>

</div>

---

# Pola Layout Industri

<div class="grid grid-cols-2 gap-8 pt-6">

<v-click>
<div>
<h4 class="font-bold mb-4">Desain Card-based</h4>
<div class="bg-gray-100 p-4 rounded text-sm font-mono">
```
Instagram Feed Style:
┌─────────────────────┐
│ Avatar | Name       │ ← Header
├─────────────────────┤
│                     │
│      Image/Post     │ ← Content
│                     │
├─────────────────────┤
│ ♡ 💬 📤  | 🔖      │ ← Actions
└─────────────────────┘
```
</div>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-4">Profile Interface</h4>
<div class="bg-gray-100 p-4 rounded text-sm font-mono">
```
LinkedIn Profile Style:
┌─────────────────────┐
│    ┌─────────┐      │
│    │   JD    │      │ ← Avatar
│    └─────────┘      │
│   John Doe          │ ← Name & Title
│   Mobile Developer  │
├─────────────────────┤
│ 150 | 2.5k | 180    │ ← Stats
│ Projects|Followers   │
├─────────────────────┤
│ About: Lorem ipsum  │ ← Bio
│ Skills: [React][JS] │ ← Skills
└─────────────────────┘
```
</div>
</div>
</v-click>

</div>

---

# Desain Responsif untuk Mobile

<div class="space-y-6 pt-4">

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Layout Fleksibel</h4>
<p class="text-sm text-gray-600">Gunakan flex properties dan percentage untuk adaptasi ukuran layar</p>
</div>
</v-click>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Touch-friendly Sizing</h4>
<p class="text-sm text-gray-600">Minimum 44pt untuk target sentuh (Apple HIG), 48dp (Material Design)</p>
</div>
</v-click>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Pertimbangan Perangkat</h4>
<p class="text-sm text-gray-600">iPhone SE (320pt) sampai iPad Pro (1024pt) - test di berbagai ukuran</p>
</div>
</v-click>

</div>

<div class="pt-8">

<v-click>
<div class="bg-gray-100 p-4 rounded text-sm">
<h4 class="font-bold mb-2">Statistik Ukuran Layar Mobile 2024:</h4>
<div class="grid grid-cols-3 gap-4 text-xs">
<div>• 375x667pt: 28% (iPhone 6-8)</div>
<div>• 390x844pt: 24% (iPhone 12-14)</div>
<div>• 360x640dp: 22% (Android mid-range)</div>
</div>
</div>
</v-click>

</div>

---

# Performa & Best Practices

<div class="grid grid-cols-2 gap-8 pt-6">

<v-click>
<div>
<h4 class="font-bold mb-4">❌ Hindari Inline Styles</h4>
<div class="bg-red-50 p-3 rounded text-xs font-mono">
```jsx
// Buruk untuk performa
<View style={{
  flex: 1,
  backgroundColor: '#ffffff',
  padding: 20,
  marginTop: 10
}}>
  <Text style={{fontSize: 16}}>
    Text
  </Text>
</View>
```
</div>
<p class="text-xs text-red-600 mt-2">Objek style dibuat ulang setiap render</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-4">✅ Gunakan StyleSheet</h4>
<div class="bg-green-50 p-3 rounded text-xs font-mono">
```jsx
// Baik untuk performa
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#ffffff',
    padding: 20,
    marginTop: 10
  },
  text: { fontSize: 16 }
});

<View style={styles.container}>
  <Text style={styles.text}>Text</Text>
</View>
```
</div>
<p class="text-xs text-green-600 mt-2">Style object di-cache untuk performa optimal</p>
</div>
</v-click>

</div>

<div class="pt-6">

<v-click>
<div class="text-center">
<strong>Performance Impact:</strong> StyleSheet.create() 35% lebih cepat dibanding inline styles
</div>
</v-click>

</div>

---

# Keuntungan StyleSheet.create()

<div class="space-y-6 pt-4">

<v-click>
<div class="grid grid-cols-3 gap-6 text-sm">
<div class="text-center">
<h5 class="font-bold">Cache Optimization</h5>
<p class="text-gray-600">Style objects disimpan di memori, tidak dibuat ulang</p>
</div>
<div class="text-center">
<h5 class="font-bold">Validation</h5>
<p class="text-gray-600">Error checking untuk properti yang tidak valid</p>
</div>
<div class="text-center">
<h5 class="font-bold">Immutability</h5>
<p class="text-gray-600">Style objects immutable, mencegah bugs</p>
</div>
</div>
</v-click>

</div>

<div class="pt-8">

<v-click>
<div class="bg-gray-100 p-4 rounded text-sm">
<h4 class="font-bold mb-3">Best Practices untuk Styling:</h4>
<div class="grid grid-cols-2 gap-4">
<ul class="space-y-1">
<li>• Gunakan StyleSheet.create() selalu</li>
<li>• Organisir styles berdasarkan komponen</li>
<li>• Buat style guide untuk konsistensi</li>
</ul>
<ul class="space-y-1">
<li>• Test di real device, bukan emulator</li>
<li>• Gunakan flexbox untuk responsive layout</li>
<li>• Hindari nested styling yang berlebihan</li>
</ul>
</div>
</div>
</v-click>

</div>

---

# Project Hands-on Preview

<div class="grid grid-cols-2 gap-8 pt-6">

<v-click>
<div>
<h4 class="font-bold mb-4">Project 1: Profile Card</h4>
<div class="bg-gray-100 p-4 rounded text-sm font-mono">
```
┌─────────────────────┐
│    ┌─────────┐      │
│    │   AS    │      │ ← Avatar
│    └─────────┘      │
│                     │
│  Aidil S. Kirsan    │ ← Nama
│  Mobile Developer   │ ← Title
│  Tech Company       │ ← Company
│                     │
│ 150 │ 2.5k │ 180    │ ← Stats
│ Projects|Followers   │
│                     │
│ About: Passionate   │ ← Bio
│ mobile developer... │
│                     │
│ [React] [JS] [TS]   │ ← Skills
│ [Node] [MongoDB]    │
└─────────────────────┘
```
</div>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-4">Project 2: Calculator Layout</h4>
<div class="bg-gray-100 p-4 rounded text-sm font-mono">
```
┌─────────────────────┐
│                   0 │ ← Display
├─────────────────────┤
│ C  │ ±  │ %  │ ÷  │ ← Row 1
├─────────────────────┤
│ 7  │ 8  │ 9  │ ×  │ ← Row 2
├─────────────────────┤
│ 4  │ 5  │ 6  │ -  │ ← Row 3
├─────────────────────┤
│ 1  │ 2  │ 3  │ +  │ ← Row 4
├─────────────────────┤
│    0     │ .  │ =  │ ← Row 5
└─────────────────────┘
```
</div>
</div>
</v-click>

</div>

<div class="pt-6">

<v-click>
<div class="text-center">
<strong>Skills yang Akan Dikuasai:</strong> Layout kompleks, styling profesional, responsive design
</div>
</v-click>

</div>

---

# Verifikasi Setup & Persiapan

<div class="space-y-6 pt-6">

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Checklist Sebelum Praktikum:</h4>
<ul class="text-sm mt-2 space-y-1">
<li>✅ Project HelloWorld dari Week 1 berjalan</li>
<li>✅ Expo CLI dapat menjalankan npx expo start</li>
<li>✅ Testing di smartphone atau browser berhasil</li>
<li>✅ VS Code siap dengan project terbuka</li>
</ul>
</div>
</v-click>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Strategi Backup Code:</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono mt-2">
```bash
# Backup hasil Week 1 sebelum mulai Week 2
cp "app/(tabs)/index.tsx" "app/(tabs)/index_week1.tsx"

# Mulai coding Week 2 di index.tsx
# Screenshot hasil akhir untuk dokumentasi
```
</div>
</div>
</v-click>

</div>

<div class="pt-8">

<v-click>
<div class="text-center">
<strong>Efisiensi:</strong> Satu project untuk semua week, tracking progress dengan backup files
</div>
</v-click>

</div>

---

# Target Pembelajaran Hari Ini

<div class="text-center pt-4">

<v-click>
<div class="text-2xl font-bold mb-8">
Menguasai Fundamental React Native!
</div>
</v-click>

<div class="grid grid-cols-3 gap-8 mb-8">

<v-click>
<div class="text-center">
<h4 class="font-bold">Komponen Inti</h4>
<p class="text-sm text-gray-600 mt-2">View, Text, ScrollView, StyleSheet</p>
</div>
</v-click>

<v-click>
<div class="text-center">
<h4 class="font-bold">Layout Flexbox</h4>
<p class="text-sm text-gray-600 mt-2">Responsive design patterns</p>
</div>
</v-click>

<v-click>
<div class="text-center">
<h4 class="font-bold">UI Praktis</h4>
<p class="text-sm text-gray-600 mt-2">Profile card & calculator layout</p>
</div>
</v-click>

</div>

<v-click>
<div class="border-2 border-black p-6 max-w-2xl mx-auto">
<h4 class="font-bold mb-2">Hasil Akhir</h4>
<p class="text-sm">
Profile card profesional dengan avatar, stats, bio, dan skills tags. 
Plus layout kalkulator dengan styling yang menarik!
</p>
</div>
</v-click>

</div>

<div class="text-xs text-gray-500 mt-6 text-center">
Duration: 3 jam | Dokumentasi: Screenshot progress setiap tahap
</div>

---
layout: end
class: text-center
---

# Mari Mulai Praktikum!

<v-click>
<div class="text-xl mb-6">
Saatnya membangun UI yang menakjubkan dengan React Native
</div>
</v-click>

<v-click>
<div class="border-2 border-black px-8 py-4 inline-block mb-6">
<span class="font-bold">Let's Code Beautiful Mobile Interfaces!</span>
</div>
</v-click>

<v-click>
<div class="text-sm text-gray-500">
Next Week: State Management & User Input<br/>
Happy Coding! 🚀
</div>
</v-click>