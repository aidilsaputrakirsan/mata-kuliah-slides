---
theme: default
background: https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80
class: text-center
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
title: React Native Week 2 - Core Components & Styling
mdc: true
---

# React Native Week 2
## Core Components & Styling

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Let's Start! <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: center
class: text-center
---

# 🎯 Apa yang akan dipelajari?

<div class="grid grid-cols-2 gap-12 mt-16">
<div>
  <div class="text-6xl mb-4">📱</div>
  <h2 class="text-2xl font-bold">Core Components</h2>
  <p class="text-lg text-gray-600 mt-2">Building blocks aplikasi mobile</p>
</div>

<div>
  <div class="text-6xl mb-4">🎨</div>
  <h2 class="text-2xl font-bold">Styling</h2>
  <p class="text-lg text-gray-600 mt-2">Membuat tampilan yang menarik</p>
</div>
</div>

---
layout: center
class: text-center
---

# 🧱 4 Komponen Utama React Native

<div class="grid grid-cols-2 gap-8 mt-12">
<div class="bg-blue-50 p-8 rounded-xl">
  <div class="text-4xl mb-4">📦</div>
  <h3 class="font-bold text-xl">View</h3>
  <p class="text-gray-600">Container / pembungkus</p>
  <p class="text-sm mt-2 text-blue-600">Seperti &lt;div&gt; di web</p>
</div>

<div class="bg-green-50 p-8 rounded-xl">
  <div class="text-4xl mb-4">📝</div>
  <h3 class="font-bold text-xl">Text</h3>
  <p class="text-gray-600">Menampilkan teks</p>
  <p class="text-sm mt-2 text-green-600">Seperti &lt;p&gt; di web</p>
</div>

<div class="bg-purple-50 p-8 rounded-xl">
  <div class="text-4xl mb-4">🖼️</div>
  <h3 class="font-bold text-xl">Image</h3>
  <p class="text-gray-600">Menampilkan gambar</p>
  <p class="text-sm mt-2 text-purple-600">Seperti &lt;img&gt; di web</p>
</div>

<div class="bg-orange-50 p-8 rounded-xl">
  <div class="text-4xl mb-4">📜</div>
  <h3 class="font-bold text-xl">ScrollView</h3>
  <p class="text-gray-600">Area yang bisa di-scroll</p>
  <p class="text-sm mt-2 text-orange-600">Untuk konten panjang</p>
</div>
</div>

---
layout: two-cols
---

# Contoh Penggunaan View

```typescript {all|1|4|5|6|8|all}
// Import komponen yang diperlukan
import { View, Text, StyleSheet } from 'react-native';

export default function App() {
  return ( // Mulai return JSX
    <View style={styles.container}>
      <Text style={styles.title}>Hello World!</Text>
    </View> // Tutup container utama
  );
}
```

::right::

# StyleSheet untuk Styling

```typescript {all|2|3|4|5|8|9|10|all}
const styles = StyleSheet.create({
  container: { // Style untuk View container
    flex: 1, // Ambil seluruh ruang yang tersedia
    backgroundColor: 'lightblue', // Warna background
    justifyContent: 'center', // Posisi vertikal tengah
    alignItems: 'center', // Posisi horizontal tengah
  },
  title: { // Style untuk Text
    fontSize: 24, // Ukuran font 24dp
    fontWeight: 'bold', // Font tebal
  },
});
```

---
layout: center
class: text-center
---

# 🎨 Styling di React Native

<div class="text-xl mt-8 text-blue-600">
Mirip CSS, tapi ada perbedaannya!
</div>

---
layout: two-cols
class: px-8
---

# 🌐 CSS (Web)
```css
.container {
  /* Warna background dengan dash */
  background-color: blue;
  /* Arah flex dengan dash */
  flex-direction: row;
  /* Margin dengan dash */
  margin-top: 10px;
}
```

<div class="mt-8 space-y-3 text-lg">
<div>• <code>background-color</code></div>
<div>• <code>flex-direction</code></div>
<div>• <code>margin-top</code></div>
<div class="text-sm text-blue-600">↑ pakai dash (-)</div>
</div>

::right::

# 📱 React Native
```javascript
const styles = StyleSheet.create({
  container: {
    // Warna background dengan camelCase
    backgroundColor: 'blue',
    // Arah flex dengan camelCase
    flexDirection: 'column',
    // Margin dengan camelCase (tanpa px)
    marginTop: 10,
  }
});
```

<div class="mt-8 space-y-3 text-lg">
<div>• <code>backgroundColor</code></div>
<div>• <code>flexDirection</code></div>
<div>• <code>marginTop</code></div>
<div class="text-sm text-green-600">↑ pakai camelCase</div>
</div>

---
layout: center
class: text-center
---

# 📐 Flexbox: Perbedaan Utama

<div class="grid grid-cols-2 gap-12 mt-16">
<div class="bg-red-50 p-8 rounded-xl">
  <h3 class="font-bold text-2xl mb-6">🌐 Web</h3>
  <div class="flex justify-center space-x-2 mb-4">
    <div class="w-12 h-12 bg-red-400 rounded flex items-center justify-center text-white font-bold">1</div>
    <div class="w-12 h-12 bg-red-400 rounded flex items-center justify-center text-white font-bold">2</div>
    <div class="w-12 h-12 bg-red-400 rounded flex items-center justify-center text-white font-bold">3</div>
  </div>
  <p class="text-lg">Default: <strong>row</strong> →</p>
</div>

<div class="bg-blue-50 p-8 rounded-xl">
  <h3 class="font-bold text-2xl mb-6">📱 React Native</h3>
  <div class="flex flex-col items-center space-y-2 mb-4">
    <div class="w-12 h-12 bg-blue-400 rounded flex items-center justify-center text-white font-bold">1</div>
    <div class="w-12 h-12 bg-blue-400 rounded flex items-center justify-center text-white font-bold">2</div>
    <div class="w-12 h-12 bg-blue-400 rounded flex items-center justify-center text-white font-bold">3</div>
  </div>
  <p class="text-lg">Default: <strong>column</strong> ↓</p>
</div>
</div>

---
layout: two-cols
---

# ScrollView untuk Konten

```typescript {all|1|4|5|7|8|10|11|13|14|all}
// Import ScrollView untuk scroll
import { ScrollView, View, Text } from 'react-native';

export default function App() {
  return ( // Container yang bisa di-scroll
    <ScrollView style={styles.container}>
      {/* Section pertama */}
      <View style={styles.section}>
        <Text style={styles.text}>Section 1...</Text>
      </View>
      {/* Section kedua */}
      <View style={styles.section}>
        <Text style={styles.text}>Section 2...</Text>
      </View>
      {/* Section ketiga */}
      <View style={styles.section}>
        <Text style={styles.text}>Section 3...</Text>
      </View>
      {/* Bisa tambah banyak konten */}
    </ScrollView>
  );
}
```

::right::

# Styling untuk ScrollView

```typescript {all|2|3|4|6|7|8|9|11|12|13|all}
const styles = StyleSheet.create({
  container: { // Container ScrollView
    flex: 1, // Ambil seluruh layar
    backgroundColor: '#f5f5f5', // Background abu-abu terang
  },
  section: { // Style untuk setiap section
    padding: 20, // Jarak dalam 20dp
    borderBottomWidth: 1, // Garis bawah 1dp
    borderBottomColor: '#ddd', // Warna garis abu-abu
  },
  text: { // Style untuk text
    fontSize: 16, // Ukuran font 16dp
    color: '#333', // Warna text abu gelap
  },
});
```

<div class="mt-4 text-center text-sm text-gray-600">
📱 User bisa scroll ke atas/bawah untuk melihat semua konten
</div>

---
layout: center
class: text-center
---

# 💡 Tips Penting

<div class="grid grid-cols-3 gap-8 mt-12">
<div class="bg-yellow-50 p-6 rounded-xl">
  <div class="text-3xl mb-3">⚡</div>
  <h3 class="font-bold">Performance</h3>
  <p class="text-sm mt-2">Gunakan StyleSheet.create() bukan inline styles</p>
</div>

<div class="bg-green-50 p-6 rounded-xl">
  <div class="text-3xl mb-3">📏</div>
  <h3 class="font-bold">Units</h3>
  <p class="text-sm mt-2">Tidak perlu 'px', langsung angka saja: fontSize: 16</p>
</div>

<div class="bg-blue-50 p-6 rounded-xl">
  <div class="text-3xl mb-3">🔧</div>
  <h3 class="font-bold">Debugging</h3>
  <p class="text-sm mt-2">Pakai backgroundColor untuk lihat layout</p>
</div>
</div>

---
layout: center
class: text-center
---

# 🛠️ Praktik Hari Ini

<div class="grid grid-cols-2 gap-12 mt-16">
<div class="bg-gradient-to-br from-purple-100 to-purple-200 p-8 rounded-xl">
  <div class="text-5xl mb-4">👤</div>
  <h2 class="text-2xl font-bold">Profile Card</h2>
  <p class="text-gray-700 mt-2">Membuat kartu profil dengan foto, nama, dan info lainnya</p>
</div>

<div class="bg-gradient-to-br from-orange-100 to-orange-200 p-8 rounded-xl">
  <div class="text-5xl mb-4">🔢</div>
  <h2 class="text-2xl font-bold">Calculator UI</h2>
  <p class="text-gray-700 mt-2">Layout kalkulator dengan button dan display</p>
</div>
</div>

---
layout: center
class: text-center
---

# 📱 Contoh Profile Card

<div class="flex justify-center">
  <img src="./profile-card-example.png" alt="Profile Card Example" class="max-w-sm rounded-xl shadow-lg" />
</div>

<p class="text-center text-gray-600 mt-4">Menggunakan View, Text, dan Flexbox</p>

---
layout: two-cols
---

# Profile Card - Structure

```typescript {all|1|4|5|7|8|9|11|12|13|14|16|all}
// Import komponen yang diperlukan
import { ScrollView, View, Text } from 'react-native';

export default function ProfileCard() {
  return ( // Container utama
    <ScrollView style={styles.container}>
      {/* Card utama dengan shadow */}
      <View style={styles.profileCard}>
        {/* Container untuk avatar */}
        <View style={styles.avatarContainer}>
          <View style={styles.avatar}>
            {/* Inisial nama sebagai avatar */}
            <Text style={styles.avatarText}>AS</Text>
          </View>
        </View>
        
        {/* Informasi profil */}
        <View style={styles.profileInfo}>
          <Text style={styles.name}>Aidil Saputra</Text>
          <Text style={styles.title}>Mobile Developer</Text>
        </View>
      </View>
    </ScrollView>
  );
}
```

::right::

# Profile Card - Styling

```typescript {all|2|3|4|5|6|8|9|10|11|12|14|15|16|17|all}
const styles = StyleSheet.create({
  profileCard: { // Card utama
    backgroundColor: 'white', // Background putih
    margin: 20, // Margin luar 20dp
    borderRadius: 15, // Sudut melengkung 15dp
    padding: 20, // Padding dalam 20dp
    elevation: 5, // Shadow untuk Android
  },
  avatar: { // Avatar bulat
    width: 100, // Lebar 100dp
    height: 100, // Tinggi 100dp
    borderRadius: 50, // Bulat sempurna (50% dari width/height)
    backgroundColor: '#3498db', // Warna biru
  },
  name: { // Style nama
    fontSize: 28, // Font besar untuk nama
    fontWeight: 'bold', // Font tebal
    color: '#2c3e50', // Warna gelap
    marginBottom: 5, // Jarak bawah 5dp
  },
});
```

---
layout: center
class: text-center
---

# 🔢 Contoh Calculator UI

<div class="flex justify-center">
  <img src="./calculator-example.png" alt="Calculator UI Example" class="max-w-xs rounded-xl shadow-lg" />
</div>

<p class="text-center text-gray-600 mt-4">Layout dengan Flexbox dan Grid</p>

---
layout: two-cols
---

# Calculator - Structure

```typescript {all|1|4|5|7|8|10|11|13|14|15|16|18|all}
// Import komponen yang diperlukan
import { View, Text, StyleSheet } from 'react-native';

export default function Calculator() {
  return ( // Container utama hitam
    <View style={styles.container}>
      {/* Area calculator */}
      <View style={styles.calculator}>
        {/* Display untuk angka */}
        <View style={styles.display}>
          <Text style={styles.displayText}>0</Text>
        </View>
        
        {/* Container untuk semua button */}
        <View style={styles.buttonContainer}>
          {/* Baris pertama button */}
          <View style={styles.buttonRow}>
            <View style={styles.button}>
              <Text style={styles.buttonText}>C</Text>
            </View>
            {/* Button lainnya... */}
          </View>
        </View>
      </View>
    </View>
  );
}
```

::right::

# Calculator - Styling

```typescript {all|2|3|4|5|7|8|9|10|12|13|14|15|17|18|19|20|all}
const styles = StyleSheet.create({
  container: { // Container utama
    flex: 1, // Ambil seluruh layar
    backgroundColor: '#000', // Background hitam
    justifyContent: 'center', // Tengah vertikal
  },
  display: { // Area display angka
    paddingHorizontal: 20, // Padding kiri-kanan
    paddingVertical: 40, // Padding atas-bawah
    alignItems: 'flex-end', // Rata kanan
    minHeight: 120, // Tinggi minimum
  },
  buttonRow: { // Baris button
    flexDirection: 'row', // Susunan horizontal
    justifyContent: 'space-between', // Rata kiri-kanan
    marginBottom: 15, // Jarak antar baris
  },
  button: { // Style setiap button
    width: 70, // Lebar 70dp
    height: 70, // Tinggi 70dp
    borderRadius: 35, // Bulat (50% dari width/height)
    backgroundColor: '#333', // Warna abu gelap
  },
});
```

---
layout: center
class: text-center
---

# 📝 Yang Perlu Dikerjakan

<div class="grid grid-cols-1 gap-6 mt-12 max-w-2xl mx-auto">
<div class="bg-blue-50 p-6 rounded-xl">
  <div class="text-3xl mb-3">✅</div>
  <h3 class="font-bold text-xl">Tugas Utama</h3>
  <p class="text-gray-700 mt-2">Buat Profile Card dengan data pribadi kamu</p>
  <p class="text-sm text-blue-600 mt-1">• Nama, NIM, jurusan • Avatar dengan inisial • Stats personal</p>
</div>

<div class="bg-green-50 p-6 rounded-xl">
  <div class="text-3xl mb-3">🏆</div>
  <h3 class="font-bold text-xl">Bonus</h3>
  <p class="text-gray-700 mt-2">Calculator UI yang lebih lengkap dan menarik</p>
  <p class="text-sm text-green-600 mt-1">• Semua button angka • Operator lengkap • Design yang bagus</p>
</div>
</div>

---
layout: center
class: text-center
---

# 🚀 Next Week Preview

<div class="text-3xl mt-16 text-blue-600 font-bold">
State Management & User Input
</div>

<div class="mt-8 text-xl text-gray-600">
Membuat aplikasi yang bisa berinteraksi dengan user!
</div>

<div class="grid grid-cols-3 gap-8 mt-12">
<div class="bg-purple-50 p-4 rounded-lg">
  <div class="text-2xl mb-2">🔄</div>
  <p class="text-sm font-bold">useState</p>
  <p class="text-xs text-gray-600">Menyimpan data</p>
</div>
<div class="bg-green-50 p-4 rounded-lg">
  <div class="text-2xl mb-2">⌨️</div>
  <p class="text-sm font-bold">TextInput</p>
  <p class="text-xs text-gray-600">Input dari user</p>
</div>
<div class="bg-blue-50 p-4 rounded-lg">
  <div class="text-2xl mb-2">👆</div>
  <p class="text-sm font-bold">Button Press</p>
  <p class="text-xs text-gray-600">Aksi saat ditekan</p>
</div>
</div>

---
layout: center
class: text-center
---

# 🎉 Selamat Belajar!

<div class="text-2xl mt-16">
<strong>Happy Coding! 💻✨</strong>
</div>

<div class="mt-8 text-lg text-gray-600">
Jangan ragu bertanya jika ada kesulitan!
</div>

<div class="mt-12 text-6xl">
📱 🚀 💙
</div>

---