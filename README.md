# Laporan Panduan dasar Git & Github

Selamat datang di dokumentasi Git & GitHub saya! Panduan ini dirancang untuk membantumu menguasai dasar-dasar Git serta sebagai laporan tugas matakuliah saya, mulai dari instalasi hingga berkolaborasi dengan tim menggunakan GitHub.

Disusun oleh:

Nama: Bryan Ananda Saputra Hulu

NPM: 4524210020

## Bagian 1: Instalasi & Konfigurasi Awal Git 

### 1. Instalasi Git

#### untuk Pengguna Windows 

1. Unduh Installer (Untuk Windows) : https://git-scm.com/download/win
2. jalankan File, .exe yang telah di unduh
3. Biarkan pengaturan default lalu klik next lalu tunggu install nya selesai
4. lakukan verifikasi Dengan Menggunakan CMD :
   bash
   git --version
   

#### Untuk Pengguna MacOS

1. Install Homebrew
   bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   
2. Install Git nya
   bash
   brew install git
   
3. Lalu lakukan verifikasi
   bash
   git --version
   

#### untuk pengguna Ubuntu/Debian 
1. Jalankan
   bash
   sudo apt update
   sudo apt install git
   
2. Lalu Verifikasi
   bash
    git --version
   

### 2. Konfigurasi Awal (Wajib)

Buka terminal/Command Prompt, lalu konfigurasikan nama dan email (terekam pada setiap commit):
bash
git config --global user.name "nama kamu"
git config --global user.email "email@kamu.com"


## Bagian 2: Alur Kerja Dasar Git (Lokal)
1. Buat Folder & Inisialisasi Git
   bash
   mkdir proyek-web
   cd proyek-web
   git init
   

2. Buat Beberapa File
   bash
   echo "<h1>Selamat Datang</h1>" > index.html
   mkdir css
   echo "body { font-family: sans-serif; }" > css/style.css
   

3. Cek Status & Masuk ke Staging Area
bash
  git status
  git add .


4. Simpan Perubahan (Commit)
   bash
   git commit -m "feat: Inisialisasi proyek dengan file index dan css"
   

5. Buat Branch Baru
   bash
   git checkout -b fitur-kontak
   

6. Buat File Baru di Branch
   bash
   echo "<h1>Halaman Kontak</h1>" > kontak.html
   
7. Staging & Commit di Branch
   bash
   git add .
   git commit -m "feat: Menambahkan halaman kontak"
   
8. Gabungkan Branch (Merge)
   bash
   git checkout main
   git merge fitur-kontak
   


## Bagian 3: Integrasi dengan GitHub

1. Buat Akun & Repository
   - Masuk ke Github
   - Klik + → New repository
   - Beri nama (misal: proyek-web-pertama) 
   - Jangan centang “Add a README file” (Penting) 
   - Klik Create repository

2. Hubungkan & Push Proyek Lokal ke GitHub
   bash
   git remote add origin https://github.com/NamaUserKamu/proyek-web-pertama.git
   git branch -M main
   git push -u origin main
   

## Bagian 4: Workflow Kerja Kelompok di GitHub (Feature Branch Workflow)

1. Clone Repository (sekali di awal)
   bash
   git clone <URL_REPOSITORY>
   
   
2. Selalu Mulai dari main Terbaru
   bash
   git checkout main
   git pull origin main
   

3. Buat Branch Baru untuk Setiap Fitur
   bash
   git checkout -b nama-fitur-baru
   

4. Kerjakan, Add, dan Commit di Branch Masing-masing
   bash
   git add .
   git commit -m "pesan commit yang jelas"
   

5. Push Branch Fitur ke GitHub
bash
git push origin nama-fitur-baru

6. Buat Pull Request (PR)
    - buka halaman repository di GitHub
    - Klik Compare & pull request
    - Isi judul, deskripsi, tetapkan Reviewers
    - Klik Create pull request

7. Review, Diskusi, dan Merge
    - Reviewer meninjau perubahan
    - Setelah disetujui, ketua tim menekan Merge pull request

8. Sinkronisasi Ulang Setelah Merge
  bash
  git checkout main
  git pull origin main
