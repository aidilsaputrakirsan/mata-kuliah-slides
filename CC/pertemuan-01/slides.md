---
theme: seriph
title: 'Week 1: Environment Setup & GitHub Integration'
info: |
  ## Cloud Computing - Week 1
  Environment Setup & GitHub Integration
  
  Sistem Informasi - Universitas [Nama Universitas]
  Semester Ganjil 2025/2026
  
  Dosen: Aidil Saputra Kirsan
author: Aidil Saputra Kirsan
keywords: cloud,computing,github,environment,setup
fonts:
  sans: 'Inter'
  mono: 'Fira Code'
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Cloud Computing
## Week 1: Environment Setup & GitHub Integration

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Sistem Informasi | Universitas <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/aidilsaputrakirsan/mata-kuliah-slides" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
layout: default
---

# 👨‍🏫 Course Information

<div class="grid grid-cols-2 gap-8">

<div>

## 📋 Course Details
- **Course**: Cloud Computing 
- **Credits**: 3 SKS
- **Semester**: Ganjil 2025/2026
- **Class**: SI-A
- **Time**: Selasa, 08:00-10:30

</div>

<div>

## 👨‍💼 Lecturer Info
- **Name**: Aidil Saputra Kirsan
- **Email**: aidil@university.ac.id
- **Office**: Ruang Dosen
- **Office Hours**: Senin-Jumat 10:00-12:00

</div>

</div>

---
layout: default
---

# 🎯 Learning Objectives

Setelah mengikuti pertemuan ini, mahasiswa mampu:

<v-clicks>

1. **Memahami** konsep dasar Cloud Computing dan pentingnya version control
2. **Mengonfigurasi** development environment untuk praktikum Cloud Computing
3. **Menggunakan** GitHub untuk manajemen kode dan kolaborasi
4. **Mengimplementasikan** basic Git workflow untuk project management
5. **Menyiapkan** tools dan platform yang akan digunakan sepanjang semester

</v-clicks>

<div class="mt-8 p-4 bg-blue-50 rounded-lg" v-click="6">
  <h3 class="text-blue-800">🎓 Expected Outcomes</h3>
  <p class="text-blue-700">Mahasiswa siap mengikuti praktikum Cloud Computing dengan environment yang proper dan memahami workflow development yang profesional.</p>
</div>

---
layout: two-cols
---

# 📚 Course Overview

<div>

## What is Cloud Computing?

<v-clicks>

- **Definition**: Delivery of computing services over the internet
- **Key Characteristics**:
  - On-demand self-service
  - Broad network access
  - Resource pooling
  - Rapid elasticity
  - Measured service

</v-clicks>

</div>

::right::

<div v-click="6">

## Why GitHub Integration?

- **Version Control**: Track changes, collaborate safely
- **Portfolio**: Showcase your cloud projects
- **Industry Standard**: Used in professional development
- **CI/CD**: Automate deployment pipelines
- **Documentation**: Maintain project documentation

</div>

---

# 🛠️ Development Environment Setup

<div class="grid grid-cols-2 gap-8">

<div>

## Essential Tools

<v-clicks>

1. **Git & GitHub**
   - Version control system
   - Account creation & setup

2. **Code Editor**
   - VS Code (Recommended)
   - Extensions for cloud development

3. **Terminal/Command Line**
   - Git Bash (Windows)
   - Terminal (macOS/Linux)

</v-clicks>

</div>

<div v-click="4">

## Cloud Platforms

1. **Google Cloud Platform (GCP)**
   - $300 free credits for students
   - Wide range of services

2. **Amazon Web Services (AWS)**
   - Free tier available
   - Industry leader

3. **Microsoft Azure**
   - Student benefits
   - Integration with Microsoft tools

</div>

</div>

---
layout: default
---

# 📱 GitHub Account Setup

<div class="grid grid-cols-2 gap-8">

<div>

## Step 1: Create Account

```bash
# Visit https://github.com
1. Click "Sign up"
2. Choose username wisely 
   (professional, permanent)
3. Use university email
4. Verify account
```

<div class="mt-4 p-4 bg-blue-50 rounded-lg">
  <h4 class="text-blue-800">💡 Pro Tips</h4>
  <ul class="text-sm text-blue-700">
    <li>Username akan jadi bagian dari portfolio</li>
    <li>Gunakan nama yang mudah diingat</li>
    <li>Hindari angka random</li>
  </ul>
</div>

</div>

<div>

## Step 2: Profile Setup

<v-clicks>

1. **Profile Picture**: Upload foto profesional
2. **Bio**: Tambahkan deskripsi singkat
3. **Location**: Kota/negara
4. **University**: Tambahkan ke education
5. **GitHub Student Pack**: Apply untuk benefits

</v-clicks>

<div v-click="6" class="mt-4 p-4 bg-green-50 rounded-lg">
  <h4 class="text-green-800">🎓 Student Benefits</h4>
  <p class="text-sm text-green-700">
    GitHub Pro, unlimited private repos, cloud credits
  </p>
</div>

</div>

</div>

---

# 💻 Git Installation & Configuration

## Windows - Download Git Bash
Visit: https://git-scm.com/download/win and follow installation wizard

## macOS - Using Homebrew
```bash
brew install git
# Or download from: https://git-scm.com/download/mac
```

## Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install git

# CentOS/RHEL
sudo yum install git
```

## Verify Installation
```bash
git --version
# Should show: git version 2.x.x
```

## Global Configuration
```bash
git config --global user.name "Nama Lengkap"
git config --global user.email "email@university.ac.id"
git config --global init.defaultBranch main
```

---
layout: two-cols
---

# 🔐 SSH Key Setup

<div>

## Generate SSH Key

```bash
# Generate new SSH key
ssh-keygen -t ed25519 -C "email@university.ac.id"

# Or use RSA if ed25519 not supported
ssh-keygen -t rsa -b 4096 -C "email@university.ac.id"

# Press Enter for default location
# Set passphrase (optional but recommended)
```

## Start SSH Agent

```bash
# Start ssh-agent
eval "$(ssh-agent -s)"

# Add SSH key to agent
ssh-add ~/.ssh/id_ed25519
```

</div>

::right::

<div>

## Add to GitHub

```bash
# Copy public key to clipboard

# macOS
pbcopy < ~/.ssh/id_ed25519.pub

# Linux
cat ~/.ssh/id_ed25519.pub

# Windows (Git Bash)
clip < ~/.ssh/id_ed25519.pub
```

**In GitHub:**
1. Settings → SSH and GPG keys
2. New SSH key
3. Paste & save

**Test Connection:**
```bash
ssh -T git@github.com
```

</div>

---

# 🚀 First Repository Creation

<div class="grid grid-cols-2 gap-8">

<div>

## Via GitHub Web

<v-clicks>

1. **Click "New repository"**
2. **Repository name**: `cc-week1-setup`
3. **Description**: "Week 1 - Environment Setup"
4. **Visibility**: Public
5. **Initialize**: ✅ README, ✅ .gitignore (Node)
6. **License**: MIT (optional)

</v-clicks>

</div>

<div v-click="7">

## Clone to Local

```bash
# Clone repository
git clone git@github.com:username/cc-week1-setup.git

# Navigate to folder
cd cc-week1-setup

# Check remote
git remote -v

# Check status
git status
```

</div>

</div>

<div v-click="8" class="mt-8 p-4 bg-yellow-50 rounded-lg">
  <h4 class="text-yellow-800">⚠️ Important</h4>
  <p class="text-yellow-700">Ganti 'username' dengan GitHub username kalian!</p>
</div>

---

# 📝 Basic Git Workflow

## Check current status
```bash
git status
```

## Create new file
```bash
echo "# Cloud Computing Environment Setup" > SETUP.md
echo "This is my development environment for CC course" >> SETUP.md
```

## Add file to staging
```bash
git add SETUP.md
git status
```

## Commit changes
```bash
git commit -m "Add initial setup documentation"
```

## Push to GitHub
```bash
git push origin main
```

## Complete workflow example
```bash
git add .
git commit -m "Update project documentation"
git push origin main
```

<div class="mt-4 p-4 bg-blue-50 rounded-lg">
  <h4 class="text-blue-800">🔄 Git Workflow</h4>
  <p class="text-blue-700"><strong>add</strong> → <strong>commit</strong> → <strong>push</strong></p>
</div>

---
layout: two-cols
---

# 🔧 VS Code Setup

<div>

## Essential Extensions

<v-clicks>

1. **Git History** - Visualize git log
2. **GitLens** - Enhanced git capabilities  
3. **GitHub Pull Requests** - GitHub integration
4. **Cloud Code** - Google Cloud development
5. **AWS Toolkit** - AWS integration
6. **Azure Tools** - Azure development
7. **Docker** - Container development
8. **YAML** - Cloud configuration files

</v-clicks>

</div>

::right::

<div v-click="9">

## Configuration

```json
{
  "git.enableSmartCommit": true,
  "git.confirmSync": false,
  "git.autofetch": true,
  "terminal.integrated.defaultProfile.windows": "Git Bash",
  "workbench.colorTheme": "GitHub Dark",
  "editor.fontSize": 14,
  "editor.tabSize": 2
}
```

## Integrated Terminal

- **Ctrl + `** (Windows/Linux)
- **Cmd + `** (macOS)
- Use Git Bash on Windows

</div>

---

# 🏗️ Project Structure Best Practices

```
cc-course-projects/
├── README.md
├── week-01-setup/
│   ├── environment-config/
│   ├── github-setup/
│   └── documentation/
├── week-02-basics/
├── week-03-deployment/
├── assignments/
│   ├── assignment-01/
│   └── assignment-02/
├── labs/
│   ├── lab-01-gcp/
│   ├── lab-02-aws/
│   └── lab-03-azure/
└── final-project/
    ├── frontend/
    ├── backend/
    └── deployment/
```

<div class="mt-4 p-4 bg-green-50 rounded-lg">
  <h4 class="text-green-800">✅ Good Practices</h4>
  <ul class="text-sm text-green-700">
    <li>Consistent naming conventions</li>
    <li>Clear folder structure</li>
    <li>Descriptive commit messages</li>
    <li>Regular commits</li>
  </ul>
</div>

---

# 📋 Hands-On Exercise

<div class="grid grid-cols-2 gap-8">

<div>

## Task 1: Environment Check

<v-clicks>

1. ✅ Create GitHub account
2. ✅ Install Git
3. ✅ Configure Git globally
4. ✅ Generate SSH key
5. ✅ Add SSH key to GitHub
6. ✅ Test SSH connection

</v-clicks>

</div>

<div v-click="7">

## Task 2: First Repository

1. Create repository: `cc-aidil-2025`
2. Clone to local machine
3. Create folder structure
4. Add README.md with:
   - Your name & student ID
   - Course information
   - Environment details
5. Commit and push changes

</div>

</div>

<div v-click="8" class="mt-8 p-4 bg-purple-50 rounded-lg">
  <h4 class="text-purple-800">🎯 Deliverable</h4>
  <p class="text-purple-700">
    Share your GitHub repository URL in the course LMS before next week!
  </p>
</div>

---
layout: two-cols
---

# 🛡️ Security Best Practices

<div>

## SSH Key Security

<v-clicks>

- **Use passphrase** for SSH keys
- **Store keys securely** (don't share)
- **Rotate keys** annually
- **Use different keys** for different services

</v-clicks>

## Git Security

<v-clicks>

- **Never commit** sensitive data
- **Use .gitignore** for secrets
- **Environment variables** for config
- **Review before pushing**

</v-clicks>

</div>

::right::

<div v-click="9">

## .gitignore Example

```bash
# Environment variables
.env
.env.local
.env.production

# Cloud credentials
gcp-key.json
aws-credentials
azure-config

# System files
.DS_Store
Thumbs.db

# IDE files
.vscode/settings.json
.idea/

# Dependencies
node_modules/
__pycache__/
```

</div>

---

# 🗓️ Next Week Preview

<div class="grid grid-cols-2 gap-8">

<div>

## Week 2: Cloud Fundamentals

<v-clicks>

- Cloud service models (IaaS, PaaS, SaaS)
- Deployment models
- Major cloud providers comparison
- Hands-on: First GCP project setup

</v-clicks>

</div>

<div v-click="5">

## Preparation

1. **Complete this week's tasks**
2. **Explore GitHub features**
3. **Read**: Chapter 1-2 from course textbook
4. **Sign up**: Google Cloud Free Tier
5. **Install**: Google Cloud SDK

</div>

</div>

<div v-click="6" class="mt-8 p-4 bg-orange-50 rounded-lg">
  <h4 class="text-orange-800">📚 Assignment</h4>
  <p class="text-orange-700">
    Create a markdown document comparing 3 major cloud providers (AWS, GCP, Azure) and commit to your repository.
  </p>
</div>

---

# ❓ Q&A Session

<div class="text-center pt-20">
  <h2 class="text-4xl">🙋‍♀️ Questions & Discussion</h2>
  <p class="text-xl mt-4 text-gray-600">
    Ada pertanyaan tentang setup environment atau GitHub?
  </p>
  
  <div class="grid grid-cols-2 gap-8 mt-12">
    <div class="p-6 bg-blue-50 rounded-lg">
      <h3 class="text-blue-800 text-lg font-semibold">💬 During Class</h3>
      <p class="text-blue-700">Raise your hand or use chat</p>
    </div>
    
    <div class="p-6 bg-green-50 rounded-lg">
      <h3 class="text-green-800 text-lg font-semibold">📧 After Class</h3>
      <p class="text-green-700">Email: aidil@university.ac.id</p>
    </div>
  </div>
</div>

---
layout: end
---

# Thank You! 🙏

<div class="text-center">
  <h2 class="text-2xl mb-4">See you next week!</h2>
  
  <div class="flex justify-center space-x-8 text-sm">
    <div>
      <h3 class="font-semibold">📱 Contact</h3>
      <p>aidil@university.ac.id</p>
    </div>
    
    <div>
      <h3 class="font-semibold">🔗 Resources</h3>
      <p>github.com/aidilsaputrakirsan/mata-kuliah-slides</p>
    </div>
    
    <div>
      <h3 class="font-semibold">💬 Office Hours</h3>
      <p>Senin-Jumat 10:00-12:00</p>
    </div>
  </div>
</div>

<div class="abs-br m-6 text-sm text-gray-500">
  Cloud Computing - Week 1 | Generated with ❤️ using Slidev
</div>