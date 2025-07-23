---
theme: seriph
title: 'Cloud Computing - Week 1'
class: text-center
highlighter: shiki
lineNumbers: true
background: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80'
info: |
  ## Cloud Computing Week 1
  Environment Setup & GitHub Integration
  
  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Cloud Computing
## Week 1: Environment Setup & GitHub Integration

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/aidilsaputrakirsan" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
transition: fade-out
---

# Learning Objectives
*Tujuan Pembelajaran*

<v-clicks>

- **Setup Development Environment** 🛠️
  - Cloud Shell configuration dan akses
- **Master Git Workflow** 🔄
  - Git commands dan best practices
- **GitHub Integration** 🐙
  - Repository management dan collaboration
- **SSH Key Management** 🔐
  - Secure authentication setup
- **Environment Verification** ✅
  - Testing dan validation procedures

</v-clicks>

<br>
<br>

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
layout: default
---

# Course Overview
*Gambaran Mata Kuliah*

<div class="grid grid-cols-2 gap-4">

<div v-click="1">

## 🎯 **Focus Areas**
- Cloud Infrastructure
- DevOps Practices  
- Containerization
- CI/CD Pipelines
- Monitoring & Security

</div>

<div v-click="2">

## 📚 **Prerequisites**
- Basic Linux commands
- Programming fundamentals
- Network concepts
- Version control basics

</div>

</div>

<v-click at="3">

## 🏆 **Week 1 Deliverables**

```mermaid
graph LR
    A[Cloud Shell] --> B[Git Setup]
    B --> C[GitHub Repo]
    C --> D[SSH Keys]
    D --> E[Verification]
    
    style A fill:#e1f5fe
    style B fill:#f3e5f5
    style C fill:#e8f5e8
    style D fill:#fff3e0
    style E fill:#ffebee
```

</v-click>

---
layout: two-cols
layoutClass: gap-16
---

# What is Cloud Computing?
*Apa itu Cloud Computing?*

<v-click>

Cloud Computing adalah **delivery of computing services** melalui Internet dengan model **pay-as-you-go**.

</v-click>

<v-clicks>

## ✨ **Key Benefits**
- **💰 Cost-effective** - No upfront investment
- **⚡ Fast deployment** - Resources in minutes
- **📈 Scalable** - Grow with your needs
- **🌍 Global access** - Available anywhere
- **🔧 Managed** - Provider handles maintenance

</v-clicks>

::right::

<v-click>

```mermaid
graph TB
    A[Your Business] --> B[Internet]
    B --> C[Cloud Provider]
    C --> D[Computing Power]
    C --> E[Storage]
    C --> F[Applications]
    C --> G[Databases]
    
    style A fill:#e3f2fd
    style C fill:#e8f5e8
    style D fill:#fff3e0
    style E fill:#fff3e0
    style F fill:#fff3e0
    style G fill:#fff3e0
```

</v-click>

---
layout: default
---

# Cloud Service Models
*Model Layanan Cloud*

<div class="grid grid-cols-3 gap-6 mt-8">

<v-click>
<div class="text-center p-4 border rounded-lg bg-blue-50">
  <div class="text-4xl mb-2">🏗️</div>
  <h3 class="font-bold text-blue-600">IaaS</h3>
  <p class="text-sm font-semibold">Infrastructure as a Service</p>
  <ul class="text-xs mt-2">
    <li>Virtual machines</li>
    <li>Storage & networking</li>
    <li>**You manage**: OS, apps</li>
  </ul>
  <div class="mt-2 text-xs font-bold">AWS EC2, Google Compute</div>
</div>
</v-click>

<v-click>
<div class="text-center p-4 border rounded-lg bg-green-50">
  <div class="text-4xl mb-2">🔧</div>
  <h3 class="font-bold text-green-600">PaaS</h3>
  <p class="text-sm font-semibold">Platform as a Service</p>
  <ul class="text-xs mt-2">
    <li>Development platform</li>
    <li>Database management</li>
    <li>**You manage**: Applications</li>
  </ul>
  <div class="mt-2 text-xs font-bold">Heroku, Google App Engine</div>
</div>
</v-click>

<v-click>
<div class="text-center p-4 border rounded-lg bg-purple-50">
  <div class="text-4xl mb-2">📱</div>
  <h3 class="font-bold text-purple-600">SaaS</h3>
  <p class="text-sm font-semibold">Software as a Service</p>
  <ul class="text-xs mt-2">
    <li>Ready-to-use software</li>
    <li>Web-based access</li>
    <li>**You manage**: Data only</li>
  </ul>
  <div class="mt-2 text-xs font-bold">Gmail, Office 365</div>
</div>
</v-click>

</div>

<v-click at="4">

## 🎯 **Which One to Choose?**

<div class="grid grid-cols-3 gap-4 mt-6">
<div class="p-3 bg-blue-100 rounded text-center">
<strong class="text-blue-800">Maximum Control</strong><br>
<span class="text-xs">Choose IaaS</span>
</div>
<div class="p-3 bg-green-100 rounded text-center">
<strong class="text-green-800">Focus on Code</strong><br>
<span class="text-xs">Choose PaaS</span>
</div>
<div class="p-3 bg-purple-100 rounded text-center">
<strong class="text-purple-800">Just Use It</strong><br>
<span class="text-xs">Choose SaaS</span>
</div>
</div>

</v-click>

---
layout: default
---

# Cloud Deployment Models
*Model Deployment Cloud*

<div class="grid grid-cols-2 gap-8 mt-6">

<div v-click="1">

## 🌐 **Public Cloud**
- **Shared** infrastructure
- **Cost-effective** for most workloads
- **High availability** & scalability
- **Examples**: AWS, Google Cloud, Azure

</div>

<div v-click="2">

## 🏢 **Private Cloud**
- **Dedicated** infrastructure
- **Enhanced security** & control
- **Higher cost** but more customization
- **Examples**: On-premises, hosted private

</div>

<div v-click="3">

## 🔄 **Hybrid Cloud**
- **Best of both worlds**
- **Flexible** workload placement
- **Gradual** migration strategy
- **Examples**: AWS Outposts, Azure Stack

</div>

<div v-click="4">

## 🌍 **Multi-Cloud**
- **Multiple** cloud providers
- **Avoid** vendor lock-in
- **Best-of-breed** services
- **Complex** management

</div>

</div>

---
layout: default
---

# Major Cloud Providers
*Provider Cloud Utama*

<div class="grid grid-cols-3 gap-6 mt-8">

<v-click>
<div class="text-center p-4 border rounded-lg">
  <div class="text-4xl mb-2">🟠</div>
  <h3 class="font-bold text-orange-600">Amazon AWS</h3>
  <div class="text-sm mt-2">
    <div class="font-semibold">Market Leader • 32%</div>
    <ul class="text-xs mt-2">
      <li>• **Largest** service catalog</li>
      <li>• **Mature** ecosystem</li>
      <li>• **Great for**: Startups, enterprises</li>
    </ul>
  </div>
</div>
</v-click>

<v-click>
<div class="text-center p-4 border rounded-lg">
  <div class="text-4xl mb-2">🔵</div>
  <h3 class="font-bold text-blue-600">Microsoft Azure</h3>
  <div class="text-sm mt-2">
    <div class="font-semibold">Enterprise Focus • 21%</div>
    <ul class="text-xs mt-2">
      <li>• **Strong** in enterprise</li>
      <li>• **Excellent** Microsoft integration</li>
      <li>• **Great for**: .NET, Office 365 users</li>
    </ul>
  </div>
</div>
</v-click>

<v-click>
<div class="text-center p-4 border rounded-lg">
  <div class="text-4xl mb-2">🟡</div>
  <h3 class="font-bold text-yellow-600">Google Cloud</h3>
  <div class="text-sm mt-2">
    <div class="font-semibold">Innovation Leader • 10%</div>
    <ul class="text-xs mt-2">
      <li>• **Advanced** AI/ML capabilities</li>
      <li>• **Strong** in data analytics</li>
      <li>• **Great for**: Data science, AI</li>
    </ul>
  </div>
</div>
</v-click>

</div>

<v-click at="4">

## 🎯 **For This Course**

<div class="text-center p-4 bg-yellow-50 rounded-lg mt-6">
<h3 class="font-bold text-yellow-800">We'll Use Google Cloud Platform</h3>
<p class="text-sm">Free tier, excellent tools, and great for learning</p>
</div>

</v-click>

---
layout: default
---

# Cloud Computing Benefits
*Manfaat Cloud Computing*

<div class="grid grid-cols-5 gap-6">

<div class="col-span-2">

<v-click>

## ✅ **Top 4 Benefits**

</v-click>

<v-clicks>

- **💰 Cost Savings** - Pay only what you use
- **⚡ Speed & Agility** - Deploy in minutes
- **📈 Auto-Scaling** - Handle traffic spikes
- **🌍 Global Reach** - Worldwide deployment

</v-clicks>

</div>

<div class="col-span-3">

<v-click>

```mermaid
graph TD
    A[Traditional IT] --> A1[High CAPEX]
    A --> A2[Slow Deployment]
    A --> A3[Fixed Capacity]
    

    style A fill:#ffebee
    style A1 fill:#ffebee
    style A2 fill:#ffebee
    style A3 fill:#ffebee

```

```mermaid
graph TD
     
    B[Cloud Computing] --> B1[Pay-as-you-go]
    B --> B2[Instant Resources]
    B --> B3[Elastic Scaling]
    
  
    style B fill:#e8f5e8
    style B1 fill:#e8f5e8
    style B2 fill:#e8f5e8
    style B3 fill:#e8f5e8
```

</v-click>

</div>

</div>

---
layout: default
---

# Cloud Computing Challenges
*Tantangan & Solusi*

<div class="grid grid-cols-2 gap-8">

<div v-click="1">

## ⚠️ **Key Challenges**

<v-clicks>

- **🔒 Security Concerns**
- **🔗 Vendor Lock-in** 
- **📶 Internet Dependency**
- **💸 Cost Management**

</v-clicks>

</div>

<div v-click="6">

## 🎯 **Best Practices**

<v-clicks>

- **📋 Plan Strategy** first
- **🛡️ Security First** approach
- **📊 Monitor Costs** regularly
- **🎓 Train Teams** continuously

</v-clicks>

</div>

</div>

<v-click at="11">

## 💡 **Success Formula**

<div class="text-center p-4 bg-blue-50 rounded-lg mt-6">
<h3 class="font-bold text-blue-800">Start Small → Learn Fast → Scale Smart</h3>
<p class="text-sm mt-2">Begin with pilot projects, gather experience, then expand strategically</p>
</div>

</v-click>

---
transition: slide-up
level: 2
---

# Development Environment Options
*Pilihan Environment Development*

<div class="grid grid-cols-3 gap-4 mt-8">

<v-click>
<div class="text-center p-4 border rounded-lg">
  <div class="text-4xl mb-2">☁️</div>
  <h3 class="font-bold text-blue-600">Cloud Shell</h3>
  <ul class="text-sm mt-2">
    <li>✅ Pre-configured</li>
    <li>✅ No installation needed</li>
    <li>✅ 5GB persistent storage</li>
    <li>✅ Built-in editor</li>
  </ul>
</div>
</v-click>

<v-click>
<div class="text-center p-4 border rounded-lg">
  <div class="text-4xl mb-2">💻</div>
  <h3 class="font-bold text-green-600">Local Environment</h3>
  <ul class="text-sm mt-2">
    <li>✅ Full control</li>
    <li>✅ Offline access</li>
    <li>❌ Setup complexity</li>
    <li>❌ Compatibility issues</li>
  </ul>
</div>
</v-click>

<v-click>
<div class="text-center p-4 border rounded-lg">
  <div class="text-4xl mb-2">🐳</div>
  <h3 class="font-bold text-purple-600">Container-based</h3>
  <ul class="text-sm mt-2">
    <li>✅ Consistent environment</li>
    <li>✅ Easy deployment</li>
    <li>❌ Docker knowledge needed</li>
    <li>❌ Resource overhead</li>
  </ul>
</div>
</v-click>

</div>

<v-click>
<div class="mt-8 p-4 bg-blue-50 rounded-lg">
<h4 class="font-bold text-blue-800">💡 Recommendation for This Course</h4>
<p class="text-sm">We'll use <span class="font-bold text-blue-600">Cloud Shell</span> as primary environment with local setup as backup</p>
</div>
</v-click>

---
layout: two-cols
layoutClass: gap-16
---

# What is Cloud Shell?
*Apa itu Cloud Shell?*

<v-click>

Cloud Shell adalah **browser-based terminal** yang menyediakan akses ke environment Linux yang sudah dikonfigurasi dengan tools development yang lengkap.

</v-click>

<v-clicks>

## ✨ **Key Features**
- **5GB persistent storage** di `$HOME`
- **Pre-installed tools**: git, docker, kubectl, etc.
- **Built-in code editor** (VS Code-like)
- **Secure access** melalui browser
- **No setup required** - langsung pakai!

</v-clicks>

::right::

<v-click>

```mermaid
graph TD
    A[Browser] -->|HTTPS| B[Cloud Shell]
    B --> C[Linux VM]
    C --> D[Pre-installed Tools]
    C --> E[Persistent Storage]
    C --> F[Code Editor]
    
    D --> D1[Git]
    D --> D2[Docker]
    D --> D3[Node.js]
    D --> D4[Python]
    
    style A fill:#e3f2fd
    style B fill:#f3e5f5
    style C fill:#e8f5e8
    style D fill:#fff3e0
    style E fill:#ffebee
    style F fill:#f1f8e9
```

</v-click>

---
transition: slide-left
---

# Cloud Shell Access Methods
*Cara Mengakses Cloud Shell*

<div class="grid grid-cols-2 gap-8 mt-4">

<div v-click="1">

## 🌐 **Method 1: Web Console**

```bash
# Navigate to
https://console.cloud.google.com
# Click "Activate Cloud Shell" icon
```

<div class="mt-4 p-3 bg-gray-100 rounded">
<h4 class="text-sm font-bold">Steps:</h4>
<ol class="text-xs">
<li>Open Google Cloud Console</li>
<li>Click terminal icon (>_)</li>
<li>Wait for initialization</li>
<li>Start coding!</li>
</ol>
</div>

</div>

<div v-click="2">

## 🚀 **Method 2: Direct URL**

```bash
# Direct access
https://shell.cloud.google.com
# Instant terminal access
```

<div class="mt-4 p-3 bg-blue-50 rounded">
<h4 class="text-sm font-bold text-blue-800">💡 Pro Tip:</h4>
<p class="text-xs">Bookmark direct URL untuk akses cepat!</p>
</div>

</div>

</div>

<v-click at="3">

## 🔧 **Initial Setup Commands**

````md magic-move
```bash
# Check environment
whoami
pwd
ls -la
```

```bash
# Verify pre-installed tools
git --version
docker --version
gcloud --version
```

```bash
# Setup workspace
mkdir ~/cloud-computing
cd ~/cloud-computing
echo "Welcome to Cloud Computing!" > README.md
```
````

</v-click>

---
layout: default
---

# Git Fundamentals Review
*Review Dasar-dasar Git*

<v-click>

Git adalah **distributed version control system** yang melacak perubahan dalam source code selama development.

</v-click>

<div class="grid grid-cols-2 gap-8 mt-6">

<div v-click="2">

## 🔄 **Git Workflow**

```mermaid
gitGraph
    commit id: "Initial"
    branch feature
    checkout feature
    commit id: "Add feature"
    commit id: "Fix bug"
    checkout main
    merge feature
    commit id: "Release"
```

</div>

<div v-click="3">

## 📈 **Git States**

```mermaid
graph LR
    A[Working Directory] -->|git add| B[Staging Area]
    B -->|git commit| C[Repository]
    C -->|git push| D[Remote Repository]
    
    style A fill:#ffebee
    style B fill:#fff3e0
    style C fill:#e8f5e8
    style D fill:#e3f2fd
```

</div>

</div>

---
layout: default
---

# Git Fundamentals Review II
*Review Dasar-dasar Git*

Git adalah **distributed version control system** yang melacak perubahan dalam source code selama development.

<v-click at="4">

## 🎯 **Essential Commands**

<div class="grid grid-cols-3 gap-4 mt-4">
<div class="p-3 bg-red-50 rounded text-center">
<strong class="text-red-600">Working Directory</strong><br>
<code class="text-xs">git status<br>git diff</code>
</div>
<div class="p-3 bg-yellow-50 rounded text-center">
<strong class="text-yellow-600">Staging Area</strong><br>
<code class="text-xs">git add<br>git reset</code>
</div>
<div class="p-3 bg-green-50 rounded text-center">
<strong class="text-green-600">Repository</strong><br>
<code class="text-xs">git commit<br>git log</code>
</div>
</div>

</v-click>

---
transition: fade
---

# Git Configuration Setup
*Konfigurasi Awal Git*

<v-click>

Sebelum menggunakan Git, kita perlu mengkonfigurasi **identity** dan **preferences**.

</v-click>

## 👤 **User Identity Configuration**

````md magic-move {at:2}
```bash
# Set your name and email
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```

```bash
# Example dengan data mahasiswa
git config --global user.name "Aidil Saputra Kirsan"
git config --global user.email "aidil@lecturer.itk.ac.id"

# Verify configuration
git config --list
```

```bash
# Additional useful configurations
git config --global init.defaultBranch main
git config --global core.editor "nano"
git config --global pull.rebase false

# Check all configurations
git config --global --list
```
````

<v-click at="5">

## ⚙️ **Advanced Settings**

<div class="grid grid-cols-2 gap-4 mt-4">
<div class="p-4 bg-blue-50 rounded">
<h4 class="font-bold text-blue-800">🎨 Output Formatting</h4>
<pre class="text-xs"><code>git config --global color.ui auto
git config --global alias.lg "log --oneline --graph"</code></pre>
</div>
<div class="p-4 bg-green-50 rounded">
<h4 class="font-bold text-green-800">🔒 Security Settings</h4>
<pre class="text-xs"><code>git config --global credential.helper store
git config --global push.default simple</code></pre>
</div>
</div>

</v-click>

---
layout: two-cols
layoutClass: gap-16
---

# GitHub Account Setup
*Setup Akun GitHub*

<v-click>

GitHub adalah **cloud-based Git repository hosting service** yang menyediakan platform untuk collaboration dan project management.

</v-click>

<v-clicks>

## 📝 **Account Creation Steps**
1. **Visit** [github.com](https://github.com)
2. **Click** "Sign up" 
3. **Choose** username (permanent!)
4. **Verify** email address
5. **Setup** profile information

</v-clicks>

::right::

<v-click>

## 📋 **Profile Best Practices**

```markdown
# README.md template
## Hi there 👋

- 🔭 I'm currently working on Cloud Computing
- 🌱 I'm currently learning DevOps
- 👯 I'm looking to collaborate on Open Source
- 💬 Ask me about Git & GitHub
- 📫 How to reach me: email@domain.com
- ⚡ Fun fact: Love automation!
```

</v-click>

<v-click>

## 🏷️ **Username Guidelines**
- **Professional** & memorable
- **Consistent** across platforms  
- **Avoid** numbers if possible
- **Examples**: 
  - `aidilsaputrakirsan`
  - `aidildev`
  - `aidil_coding`

</v-click>

---
transition: slide-up
---

# Creating Your First Repository
*Membuat Repository Pertama*

<div class="grid grid-cols-2 gap-8">

<div v-click="1">

## 🆕 **GitHub Web Interface**

<div class="space-y-2 text-sm">
<div class="p-2 bg-gray-100 rounded flex items-center">
<span class="w-6 h-6 bg-green-500 text-white rounded-full text-center text-xs mr-2">1</span>
Click "New repository" button
</div>
<div class="p-2 bg-gray-100 rounded flex items-center">
<span class="w-6 h-6 bg-green-500 text-white rounded-full text-center text-xs mr-2">2</span>
Repository name: <code>cloud-computing-week1</code>
</div>
<div class="p-2 bg-gray-100 rounded flex items-center">
<span class="w-6 h-6 bg-green-500 text-white rounded-full text-center text-xs mr-2">3</span>
Description: "Week 1 assignments"
</div>
<div class="p-2 bg-gray-100 rounded flex items-center">
<span class="w-6 h-6 bg-green-500 text-white rounded-full text-center text-xs mr-2">4</span>
✅ Initialize with README
</div>
<div class="p-2 bg-gray-100 rounded flex items-center">
<span class="w-6 h-6 bg-green-500 text-white rounded-full text-center text-xs mr-2">5</span>
Add .gitignore (optional)
</div>
</div>

</div>

<div v-click="2">

## 💻 **Command Line Alternative**

<v-click at="3">

```bash
# Create local directory
mkdir cloud-computing-week1
cd cloud-computing-week1
```

</v-click>

<v-click at="4">

```bash
# Initialize Git repository
git init
echo "# Cloud Computing Week 1" > README.md
git add README.md
git commit -m "Initial commit"
```

</v-click>

<v-click at="5">

```bash
# Connect to GitHub (create repo first)
git remote add origin https://github.com/username/cloud-computing-week1.git
git branch -M main
git push -u origin main
```

</v-click>

</div>

</div>

---
transition: slide-up
---

## 📁 **Repository Structure Recommendation**

```
cloud-computing-week1/
├── README.md
├── assignments/
├── labs/
├── notes/
└── resources/
```

---
layout: two-cols
layoutClass: gap-16
---

# SSH Key Authentication
*Autentikasi dengan SSH Key*

<v-click>

SSH keys provide **secure authentication** without passwords untuk akses repository.

</v-click>

<v-click>

## 🔐 **Benefits of SSH Keys**
- **No passwords** untuk Git operations
- **Enhanced security** dengan public-key cryptography  
- **Automation-friendly** untuk scripts & CI/CD
- **Multiple keys** untuk different services

</v-click>

::right::

<v-click>

```mermaid
sequenceDiagram
    participant C as Client (Cloud Shell)
    participant G as GitHub
    
    C->>C: Generate SSH Key Pair
    C->>G: Upload Public Key
    C->>G: Git operations with private key
    G->>G: Verify with public key
    G->>C: Access granted
    
    Note over C,G: Secure, passwordless authentication
```

</v-click>

---
transition: slide-left
---

# Generating SSH Keys
*Membuat SSH Key*

## 🔑 **Step-by-Step Process**

````md magic-move
```bash
# Generate new SSH key pair
ssh-keygen -t ed25519 -C "your.email@example.com"
```

```bash
# Full generation process
ssh-keygen -t ed25519 -C "aidil@lecturer.itk.ac.id"
# When prompted:
# - File location: Press Enter (default: ~/.ssh/id_ed25519)
# - Passphrase: Enter secure passphrase (recommended)
# - Confirm passphrase: Re-enter same passphrase
```

```bash
# Start SSH agent and add key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Verify keys are loaded
ssh-add -l
```

```bash
# Display public key for copying
cat ~/.ssh/id_ed25519.pub

# Example output:
# ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGqL... your.email@example.com
```
````

<v-click at="5">

## ⚠️ **Security Best Practices**
- **Always use passphrase** untuk private key
- **Never share** private key (`id_ed25519`)
- **Only share** public key (`id_ed25519.pub`)  
- **Use ed25519** algorithm (modern & secure)

</v-click>

---
layout: two-cols
layoutClass: gap-16
---

# Adding SSH Key to GitHub

<v-clicks>

### 📋 **Steps in GitHub**

1. **Navigate** to Settings → SSH and GPG keys
2. **Click** "New SSH key" 
3. **Title**: "Cloud Shell Key"
4. **Key type**: Authentication Key
5. **Paste** public key content
6. **Click** "Add SSH key"
7. **Confirm** with password

</v-clicks>

<v-click>

### 🧪 **Testing Connection**

```bash
# Test SSH connection
ssh -T git@github.com
# Expected output:
# Hi username! You've successfully authenticated,
# but GitHub does not provide shell access.
```

</v-click>

::right::

<v-click>

## 🔄 **Update Remote URL**

````md magic-move
```bash
# Check current remote
git remote -v
```

```bash
# Change from HTTPS to SSH
git remote set-url origin 
git@github.com:username/repo.git

# Verify change
git remote -v
```
````

</v-click>

<v-click>

## ✅ **Verification Test**

```bash
# Test with actual push
echo "SSH test" > test-ssh.txt
git add test-ssh.txt
git commit -m "Test SSH authentication"
git push

# Should work without password prompt!
```

</v-click>

<v-click>

## 🎯 **Common Issues**
- **Permission denied**: Check key format
- **Wrong passphrase**: Re-add key to agent
- **Host key verification**: Accept GitHub's fingerprint

</v-click>

---
transition: fade
---

# Basic Git Workflow
*Alur Kerja Dasar Git*

<v-click>

Mari praktek **complete workflow** dari development hingga deployment.

</v-click>

## 🔄 **The Standard Workflow**

````md magic-move {at:2}
```bash
# 1. Check status
git status
```

```bash
# 2. Create and edit files
echo "# Assignment 1" > assignment1.md
echo "This is my first assignment" >> assignment1.md

# Check what changed
git status
git diff
```

```bash
# 3. Stage changes
git add assignment1.md

# Or stage all changes
git add .

# Check staging area
git status
```

```bash
# 4. Commit changes
git commit -m "Add assignment 1 documentation"

# View commit history
git log --oneline
```

```bash
# 5. Push to remote
git push origin main

# Or just
git push
```
````

<v-click at="7">

## 📊 **Workflow Visualization**

```mermaid
graph LR
    A[Edit Files] --> B[git add]
    B --> C[git commit]
    C --> D[git push]
    D --> E[GitHub Repository]
    
    style A fill:#ffebee
    style B fill:#fff3e0  
    style C fill:#e8f5e8
    style D fill:#e3f2fd
    style E fill:#f3e5f5
```

</v-click>

---
layout: two-cols
layoutClass: gap-16
---

# Advanced Git Operations
*Operasi Git Lanjutan*

## 🌿 **Branching Strategy**

<v-click at="1">

```bash
# Create and switch to new branch
git checkout -b feature/assignment2
```

</v-click>

<v-click at="2">

```bash
# Work on the branch
echo "Assignment 2 content" > assignment2.md
git add assignment2.md
git commit -m "Add assignment 2"
```

</v-click>

<v-click at="3">

```bash
# Switch back to main and merge
git checkout main
git merge feature/assignment2
git push origin main
```

</v-click>

::right::

<v-click at="4">

## 🔍 **Inspection Commands**

```bash
# View commit history
git log --oneline --graph --all

# Show specific commit
git show <commit-hash>

# Compare branches
git diff main..feature/assignment2

# Check file history
git log --follow assignment1.md
```

</v-click>

---
transition: fade
---

# Git Productivity Tools
*Tools Produktivitas Git*

<div class="grid grid-cols-2 gap-8">

<div v-click="1">

## 🛠️ **Useful Git Aliases**

```bash
# Setup helpful aliases
git config --global alias.co checkout
git config --global alias.br branch  
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.lg "log --oneline --graph --all"

# Usage examples
git st  # Same as git status
git lg  # Pretty log output
```

</div>

<div v-click="2">

## 🔄 **Sync with Remote**

```bash
# Get latest changes
git fetch origin
git pull origin main

# Force sync (careful!)
git reset --hard origin/main

# Check remote status
git remote -v
git branch -r
```

</div>

</div>

<v-click at="3">

## 💡 **Pro Tips**

<div class="grid grid-cols-3 gap-4 mt-4">
<div class="p-3 bg-blue-50 rounded text-center">
<strong class="text-blue-600">Branching</strong><br>
<code class="text-xs">git branch -d feature-name</code>
</div>
<div class="p-3 bg-green-50 rounded text-center">
<strong class="text-green-600">Stashing</strong><br>
<code class="text-xs">git stash / git stash pop</code>
</div>
<div class="p-3 bg-purple-50 rounded text-center">
<strong class="text-purple-600">Tagging</strong><br>
<code class="text-xs">git tag v1.0 / git push --tags</code>
</div>
</div>

</v-click>

---
layout: end
class: text-center
---

# Questions & Discussion
*Pertanyaan & Diskusi*

<div class="grid grid-cols-2 gap-8 mt-8">

<div v-click="1">

## 💬 **Discussion Topics**
- Environment setup challenges?
- Git workflow questions?
- SSH authentication issues?
- Repository organization preferences?
- Cloud Shell vs local development?

</div>

<div v-click="2">

## 📧 **Get Help**
- **Office Hours**: Monday 14:00-16:00
- **Email**: aidil@lecturer.itk.ac.id
- **GitHub Issues**: For technical problems
- **Study Groups**: Form with classmates

</div>

</div>

<v-click at="3">

## 🎯 **Action Items**
1. Complete environment setup by **Friday**
2. Submit verification screenshots to **LMS**
3. Join course **studyverse.myst-tech.com**
4. Prepare for next week's

</v-click>

<div class="pt-12">
  <span class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Thank you! Happy coding! 🚀
  </span>
</div>

<style>
.end {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  color: white;
}
</style>
