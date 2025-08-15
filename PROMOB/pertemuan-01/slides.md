---
theme: default
background: '#ffffff'
title: Introduction to React Native
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Introduction to React Native - Week 1
  Pemrograman Mobile - Aidil Saputra Kirsan, M.Tr.Kom
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Introduction to React Native
## Pemrograman Mobile - Week 1

<div class="pt-8">
  <div class="text-gray-600">Mata Kuliah: Pemrograman Mobile</div>
  <div class="text-gray-600">Durasi: 3 jam praktikum</div>
  <div class="text-gray-600">Target: Membangun aplikasi mobile pertama</div>
</div>

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-4 py-2 rounded cursor-pointer border border-gray-300 hover:border-gray-500">
    Mulai Perjalanan Mobile Development →
  </span>
</div>

---

# Capaian Pembelajaran

Setelah praktikum ini, mahasiswa mampu:

<v-clicks>

- **Memahami** perbedaan fundamental web vs mobile development
- **Menginstall** environment React Native dengan Expo
- **Membuat** aplikasi mobile pertama dengan Expo Router  
- **Menjalankan** aplikasi di smartphone dan browser
- **Memahami** struktur project React Native modern

</v-clicks>

<div class="absolute bottom-4 left-4 text-xs text-gray-500">
Prerequisites: JavaScript, HTML, CSS dari mata kuliah web programming
</div>

---

# Mobile Revolution: The Numbers

<div class="grid grid-cols-3 gap-8 pt-8">

<v-click>
<div class="text-center">
<div class="text-3xl font-bold">$753B</div>
<div class="text-sm text-gray-600">Global Market 2025</div>
<div class="text-xs text-gray-500">CAGR 12.1%</div>
</div>
</v-click>

<v-click>
<div class="text-center">
<div class="text-3xl font-bold">4-5 jam</div>
<div class="text-sm text-gray-600">Daily Usage</div>
<div class="text-xs text-gray-500">94.2% internet users</div>
</div>
</v-click>

<v-click>
<div class="text-center">
<div class="text-3xl font-bold">7.49B</div>
<div class="text-sm text-gray-600">Mobile Users 2025</div>
<div class="text-xs text-gray-500">257B apps downloaded 2023</div>
</div>
</v-click>

</div>

<div class="pt-12">

<v-click>
<div class="grid grid-cols-2 gap-8">
<div class="text-center">
<div class="text-xl font-bold">97%</div>
<div class="text-sm text-gray-600">Apps are free to download</div>
</div>
<div class="text-center">
<div class="text-xl font-bold">32%</div>
<div class="text-sm text-gray-600">Apps dibuat dengan React Native</div>
</div>
</div>
</v-click>

</div>

<div class="text-xs mt-8 text-gray-400 text-center">
Sources: Straits Research, Grand View Research, Statista 2024
</div>

---

<div class="grid grid-cols-2 gap-8 pt-4">

<!-- Kolom Kiri: Gaji -->
<div>
  <h3>Rata-rata Gaji Mobile Developer (2024):</h3>

  <v-clicks>
    <ul class="list-disc pl-5 mt-2">
      <li><strong>Fresh Graduate (0-2 tahun):</strong> Rp 78-108 juta/tahun</li>
      <li><strong>Mid Level (5-10 tahun):</strong> Rp 153-187 juta/tahun</li>
      <li><strong>Senior Level (10+ tahun):</strong> Rp 200+ juta/tahun</li>
    </ul>
  </v-clicks>
</div>

<!-- Kolom Kanan: Growth & Industry Facts -->
<div class="space-y-6">
  <div>
    <v-click at="1">
      <h3>Growth Opportunities:</h3>
      <ul class="list-disc pl-5 mt-2">
        <li>Demand tinggi di e-commerce, fintech, gaming</li>
        <li>Remote work opportunities global</li>
        <li>Digital economy Indonesia target $124B by 2025</li>
        <li>Gaji mobile developer 2x lipat dibanding web developer</li>
      </ul>
    </v-click>
  </div>

  <div>
    <v-click at="2">
      <h3>Industry Facts:</h3>
      <ul class="list-disc pl-5 mt-2">
        <li>14.85% dari top 500 US apps menggunakan React Native</li>
        <li>Startup ecosystem berkembang pesat</li>
        <li>Strong community support dan learning resources</li>
      </ul>
    </v-click>
  </div>
</div>

</div>

---

# Evolution of Mobile Development

<div class="space-y-8 pt-4">

<v-click>
<div class="flex justify-between items-center border-b pb-4">
<div class="w-1/4 text-right pr-4">
<div class="font-bold">2008-2012</div>
<div class="text-sm text-gray-600">Native Era</div>
</div>
<div class="w-3/4 pl-4">
iOS SDK, Android SDK - Dua codebase terpisah
</div>
</div>
</v-click>

<v-click>
<div class="flex justify-between items-center border-b pb-4">
<div class="w-1/4 text-right pr-4">
<div class="font-bold">2012-2015</div>
<div class="text-sm text-gray-600">Hybrid Era</div>
</div>
<div class="w-3/4 pl-4">
PhoneGap, Cordova, Ionic - Web dalam wrapper native
</div>
</div>
</v-click>

<v-click>
<div class="flex justify-between items-center border-b pb-4">
<div class="w-1/4 text-right pr-4">
<div class="font-bold">2015-Now</div>
<div class="text-sm text-gray-600">Cross-Platform</div>
</div>
<div class="w-3/4 pl-4">
React Native, Flutter - Native performance + code reuse
</div>
</div>
</v-click>

<v-click>
<div class="flex justify-between items-center">
<div class="w-1/4 text-right pr-4">
<div class="font-bold">2025</div>
<div class="text-sm text-gray-600">AI-Powered</div>
</div>
<div class="w-3/4 pl-4">
5G, AR/VR, AI Integration - Next-gen mobile experiences
</div>
</div>
</v-click>

</div>

---

# Native vs Cross-Platform

<div class="grid grid-cols-2 gap-12 pt-4">

<div>
<h3 class="font-bold text-lg mb-4">Native Development</h3>

<div class="mb-4">
<div class="font-medium mb-2">Advantages:</div>
<ul class="text-sm space-y-1">
<li>• Performance maksimal</li>
<li>• Access penuh platform APIs</li>
<li>• UI/UX platform-specific</li>
</ul>
</div>

<div>
<div class="font-medium mb-2">Disadvantages:</div>
<ul class="text-sm space-y-1">
<li>• Dua tim development</li>
<li>• Cost 2x lipat</li>
<li>• Time to market lama</li>
</ul>
</div>

</div>

<div>
<h3 class="font-bold text-lg mb-4">Cross-Platform</h3>

<div class="mb-4">
<div class="font-medium mb-2">Advantages:</div>
<ul class="text-sm space-y-1">
<li>• Satu codebase, dua platform</li>
<li>• Cost 40-60% lebih murah</li>
<li>• Faster time to market</li>
</ul>
</div>

<div>
<div class="font-medium mb-2">Trade-offs:</div>
<ul class="text-sm space-y-1">
<li>• Slight performance trade-off</li>
<li>• Platform limitations</li>
<li>• Learning curve baru</li>
</ul>
</div>

</div>

</div>

---

# Cross-Platform Market Share 2024

<div class="pt-8">

<div class="space-y-4 mb-8">

<v-click>
<div class="flex items-center">
<div class="w-16 text-sm">Flutter:</div>
<div class="flex-1 bg-gray-200 h-6 rounded">
<div class="bg-black h-6 rounded" style="width: 42%"></div>
</div>
<div class="w-12 text-sm text-right">42%</div>
</div>
</v-click>

<v-click>
<div class="flex items-center">
<div class="w-16 text-sm">React Native:</div>
<div class="flex-1 bg-gray-200 h-6 rounded">
<div class="bg-gray-600 h-6 rounded" style="width: 38%"></div>
</div>
<div class="w-12 text-sm text-right">38%</div>
</div>
</v-click>

<v-click>
<div class="flex items-center">
<div class="w-16 text-sm">Others:</div>
<div class="flex-1 bg-gray-200 h-6 rounded">
<div class="bg-gray-400 h-6 rounded" style="width: 20%"></div>
</div>
<div class="w-12 text-sm text-right">20%</div>
</div>
</v-click>

</div>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<div class="font-medium">Industry Adoption:</div>
<div class="text-sm text-gray-600 mt-1">
<strong>React Native:</strong> Facebook, Instagram, Walmart, Bloomberg, Tesla<br/>
<strong>Flutter:</strong> Google Pay, BMW, Toyota, Alibaba
</div>
</div>
</v-click>

</div>

<div class="text-xs mt-6 text-gray-400 text-center">
Source: Statista Cross-Platform Development Survey 2024
</div>

---

# Why React Native?

<div class="grid grid-cols-2 gap-8 pt-6">

<v-click>
<div>
<h4 class="font-bold mb-2">Learn Once, Write Anywhere</h4>
<p class="text-sm text-gray-600">JavaScript & React familiar. 96% code reuse iOS & Android.</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-2">Hot Reload</h4>
<p class="text-sm text-gray-600">Instant feedback. Development 50% lebih cepat.</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-2">Enterprise Ready</h4>
<p class="text-sm text-gray-600">Trusted by Fortune 500: Meta, Microsoft, Shopify.</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-2">Rich Ecosystem</h4>
<p class="text-sm text-gray-600">1.8M+ NPM packages. Strong community support.</p>
</div>
</v-click>

</div>

<div class="pt-12 text-center">

<v-click>
<div class="border border-gray-300 inline-block px-6 py-3 rounded">
<span class="font-medium">32% of all cross-platform apps globally</span>
</div>
</v-click>

</div>

---

# Web vs Mobile: Key Differences

<div class="pt-4">

<div class="grid grid-cols-3 gap-4 text-sm font-bold border-b-2 pb-2 mb-4">
<div>Aspect</div>
<div>Web Development</div>
<div>Mobile Development</div>
</div>

<div class="space-y-3 text-sm">

<v-click>
<div class="grid grid-cols-3 gap-4">
<div class="font-medium">Platform</div>
<div>Browser (Chrome, Firefox)</div>
<div>OS Specific (Android, iOS)</div>
</div>
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-4">
<div class="font-medium">UI Components</div>
<div>&lt;div&gt;, &lt;p&gt;, &lt;button&gt;</div>
<div>&lt;View&gt;, &lt;Text&gt;, &lt;TouchableOpacity&gt;</div>
</div>
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-4">
<div class="font-medium">Styling</div>
<div>CSS Files</div>
<div>StyleSheet Objects</div>
</div>
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-4">
<div class="font-medium">Navigation</div>
<div>URL-based routing</div>
<div>Stack/Tab navigation</div>
</div>
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-4">
<div class="font-medium">Storage</div>
<div>localStorage, cookies</div>
<div>AsyncStorage, SQLite</div>
</div>
</v-click>

</div>

</div>

<div class="pt-6">

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<strong>Good News:</strong> React Native menggunakan konsep yang sama dengan React web, 
jadi learning curve tidak terlalu steep!
</div>
</v-click>

</div>

---

# React Native Core Concepts

<div class="grid grid-cols-2 gap-8 pt-4">

<v-click>
<div>
<h4 class="font-bold mb-3">Components</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```jsx
// Web React
<div className="container">
  <p>Hello World</p>
  <button onClick={handlePress}>
    Click me
  </button>
</div>

// React Native  
<View style={styles.container}>
  <Text>Hello World</Text>
  <TouchableOpacity onPress={handlePress}>
    <Text>Click me</Text>
  </TouchableOpacity>
</View>
```
</div>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold mb-3">Styling</h4>
<div class="bg-gray-100 p-3 rounded text-xs font-mono">
```jsx
// CSS
.container {
  display: flex;
  justify-content: center;
  background-color: #f0f0f0;
}

// React Native StyleSheet
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    backgroundColor: '#f0f0f0',
  }
});
```
</div>
</div>
</v-click>

</div>

<div class="pt-6">

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<strong>Key Insight:</strong> React Native menggunakan Flexbox layout sama dengan web, 
tapi default <code>flexDirection: 'column'</code> bukan <code>'row'</code>.
</div>
</v-click>

</div>

---

# Expo Ecosystem

<div class="space-y-6 pt-4">

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Expo CLI</h4>
<p class="text-sm text-gray-600">Zero-config development environment. No Xcode/Android Studio required!</p>
</div>
</v-click>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Expo Go</h4>
<p class="text-sm text-gray-600">Test apps instantly di smartphone. Scan QR code dan langsung jalan!</p>
</div>
</v-click>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Expo Router</h4>
<p class="text-sm text-gray-600">File-based routing seperti Next.js. Modern navigation + TypeScript.</p>
</div>
</v-click>

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">EAS Services</h4>
<p class="text-sm text-gray-600">Cloud build & deployment. Push ke App Store/Play Store.</p>
</div>
</v-click>

</div>

<div class="pt-8 text-center">

<v-click>
<div class="border border-gray-300 inline-block px-6 py-3 rounded">
<span class="font-medium">Expo = React Native development 10x lebih mudah!</span>
</div>
</v-click>

</div>

---

# Modern Project Structure

<div class="grid grid-cols-2 gap-8 pt-4">

<v-click>
<div class="bg-gray-100 p-4 rounded text-xs font-mono">
```
HelloWorld/
├── app/                    # Main directory
│   ├── (tabs)/            # Tab navigation
│   │   ├── index.tsx      # Home screen  
│   │   ├── explore.tsx    # Second tab
│   │   └── _layout.tsx    # Tab config
│   ├── +html.tsx          # Web template
│   ├── +not-found.tsx     # 404 page
│   └── _layout.tsx        # Root layout
├── components/            # Reusable UI
├── constants/             # App constants  
├── assets/                # Images, fonts
└── package.json          # Dependencies
```
</div>
</v-click>

<v-click>
<div class="space-y-4">
<div>
<h4 class="font-bold">File-based Routing</h4>
<p class="text-sm text-gray-600">Seperti Next.js! File struktur = routing struktur.</p>
</div>

<div>
<h4 class="font-bold">TypeScript Ready</h4>
<p class="text-sm text-gray-600">Full TypeScript support out of the box.</p>
</div>

<div>
<h4 class="font-bold">Universal Apps</h4>
<p class="text-sm text-gray-600">Mobile, web, desktop dari satu kode!</p>
</div>
</div>
</v-click>

</div>

---

# Development Workflow

<div class="space-y-6 pt-6">

<v-click>
<div class="flex items-start space-x-4">
<div class="w-8 h-8 border-2 border-black rounded-full flex items-center justify-center font-bold text-sm">1</div>
<div>
<h4 class="font-bold">Development</h4>
<p class="text-sm text-gray-600">Code dengan VS Code + Expo CLI. Hot reload untuk instant feedback.</p>
</div>
</div>
</v-click>

<v-click>
<div class="flex items-start space-x-4">
<div class="w-8 h-8 border-2 border-black rounded-full flex items-center justify-center font-bold text-sm">2</div>
<div>
<h4 class="font-bold">Testing</h4>
<p class="text-sm text-gray-600">Test di Expo Go (smartphone) atau web browser. Real device testing.</p>
</div>
</div>
</v-click>

<v-click>
<div class="flex items-start space-x-4">
<div class="w-8 h-8 border-2 border-black rounded-full flex items-center justify-center font-bold text-sm">3</div>
<div>
<h4 class="font-bold">Build & Deploy</h4>
<p class="text-sm text-gray-600">EAS Build untuk production. Submit ke App Store & Play Store.</p>
</div>
</div>
</v-click>

</div>

<div class="pt-8 text-center">

<v-click>
<div class="border border-gray-300 inline-block px-6 py-3 rounded">
<span class="font-medium">Total development time: Hours, not weeks!</span>
</div>
</v-click>

</div>

---

# Industry Trends 2025

<div class="grid grid-cols-2 gap-8 pt-6">

<v-click>
<div>
<h4 class="font-bold">5G Integration</h4>
<p class="text-sm text-gray-600">3.6B connections by 2025. Enhanced AR/VR experiences.</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold">AI-Powered Apps</h4>
<p class="text-sm text-gray-600">$1.1B revenue in 2024. Growth 200% year-over-year.</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold">IoT Integration</h4>
<p class="text-sm text-gray-600">IoT market $1.387T by 2025. Smart home, wearables.</p>
</div>
</v-click>

<v-click>
<div>
<h4 class="font-bold">Gaming Dominance</h4>
<p class="text-sm text-gray-600">63% consumer spending. $132B revenue by 2029.</p>
</div>
</v-click>

</div>

<div class="pt-8">

<v-click>
<div class="text-center">
<strong>Future is Mobile:</strong> Super apps, voice interfaces, edge computing
</div>
</v-click>

</div>

---

# Real-World Challenges & Solutions

<div class="grid grid-cols-3 gap-8 pt-6">

<v-click>
<div class="text-center">
<h4 class="font-bold mb-3">Challenges</h4>
<ul class="text-sm space-y-1">
<li>• Platform differences</li>
<li>• Performance concerns</li>
<li>• Native module access</li>
</ul>
</div>
</v-click>

<v-click>
<div class="text-center">
<h4 class="font-bold mb-3">Solutions</h4>
<ul class="text-sm space-y-1">
<li>• Platform-specific code</li>
<li>• Optimization techniques</li>
<li>• Expo managed workflow</li>
</ul>
</div>
</v-click>

<v-click>
<div class="text-center">
<h4 class="font-bold mb-3">Results</h4>
<ul class="text-sm space-y-1">
<li>• 96% code reuse</li>
<li>• Native performance</li>
<li>• Faster development</li>
</ul>
</div>
</v-click>

</div>

<div class="pt-8">

<v-click>
<div class="border-l-4 border-gray-400 pl-4">
<h4 class="font-bold">Best Practices 2025</h4>
<div class="grid grid-cols-2 gap-4 text-sm mt-2">
<ul class="space-y-1">
<li>• Use TypeScript dari awal</li>
<li>• Implement proper state management</li>
<li>• Optimize images dan assets</li>
</ul>
<ul class="space-y-1">
<li>• Test di real devices</li>
<li>• Follow platform guidelines</li>
<li>• Monitor performance metrics</li>
</ul>
</div>
</div>
</v-click>

</div>

---

# Siap Memulai Praktikum?

<div class="text-center pt-4">

<v-click>
<div class="text-2xl font-bold mb-8">
Let's Build Your First Mobile App!
</div>
</v-click>

<div class="grid grid-cols-3 gap-8 mb-8">

<v-click>
<div class="text-center">
<h4 class="font-bold">Setup Environment</h4>
<p class="text-sm text-gray-600 mt-2">Node.js, Expo CLI, VS Code</p>
</div>
</v-click>

<v-click>
<div class="text-center">
<h4 class="font-bold">Create First App</h4>
<p class="text-sm text-gray-600 mt-2">Hello World dengan Expo Router</p>
</div>
</v-click>

<v-click>
<div class="text-center">
<h4 class="font-bold">Run & Test</h4>
<p class="text-sm text-gray-600 mt-2">Smartphone & web browser</p>
</div>
</v-click>

</div>

<v-click>
<div class="border-2 border-black p-6 max-w-2xl mx-auto">
<h4 class="font-bold mb-2">Target Hari Ini</h4>
<p class="text-sm">
Membuat aplikasi Hello World personal dengan info mahasiswa, styling menarik, 
dan berhasil running di 2 platform!
</p>
</div>
</v-click>

</div>

<div class="text-xs text-gray-500 mt-6 text-center">
Duration: 3 jam | Jangan lupa screenshot hasil akhir!
</div>

---
layout: end
class: text-center
---

# Thank You!

<v-click>
<div class="text-xl mb-6">
Mari mulai praktikum dan bangun masa depan mobile development!
</div>
</v-click>

<v-click>
<div class="border-2 border-black px-8 py-4 inline-block mb-6">
<span class="font-bold">Ready untuk menjadi Mobile Developer?</span>
</div>
</v-click>

<v-click>
<div class="text-sm text-gray-500">
Slides created with Aidil Saputra Kirsan<br/>
Let's code something amazing together!
</div>
</v-click>