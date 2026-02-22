# 🚀 Panduan Deploy ContentAI ke Vercel
### Untuk pemula — tidak perlu coding!

---

## 📦 Apa yang Kamu Butuhkan

Sebelum mulai, siapkan ini:

| Yang Dibutuhkan | Keterangan | Harga |
|---|---|---|
| Akun GitHub | Untuk menyimpan kode | Gratis |
| Akun Vercel | Untuk hosting website | Gratis |
| Anthropic API Key | Untuk fitur AI | Berbayar (ada free trial) |
| Akun RunwayML *(opsional)* | Untuk video AI premium | Berbayar |

---

## LANGKAH 1 — Buat Akun GitHub

1. Buka **github.com**
2. Klik tombol **"Sign up"** (pojok kanan atas)
3. Isi email, password, dan username
4. Verifikasi email
5. Pilih plan **Free**
6. ✅ Selesai! Kamu sudah punya akun GitHub

---

## LANGKAH 2 — Upload Kode ke GitHub

1. Login ke GitHub
2. Klik tombol **"+"** (pojok kanan atas) → **"New repository"**
3. Isi:
   - **Repository name:** `contentai` (atau nama lain bebas)
   - Pilih **Public**
4. Klik **"Create repository"**
5. Di halaman repository yang baru dibuat, klik **"uploading an existing file"**
6. **Drag & drop semua file berikut ke browser:**
   ```
   📁 contentai/
   ├── 📁 api/
   │   └── claude.js
   ├── 📁 public/
   │   └── index.html
   ├── package.json
   └── vercel.json
   ```
   > ⚠️ **Penting:** Pertahankan struktur folder! Upload folder `api` dan `public` sesuai strukturnya.
7. Scroll ke bawah, klik **"Commit changes"**
8. ✅ Kode sudah tersimpan di GitHub!

---

## LANGKAH 3 — Buat Akun Vercel

1. Buka **vercel.com**
2. Klik **"Sign Up"**
3. Pilih **"Continue with GitHub"**
4. Authorize Vercel untuk mengakses GitHub kamu
5. ✅ Akun Vercel sudah terhubung ke GitHub!

---

## LANGKAH 4 — Deploy ke Vercel

1. Di dashboard Vercel, klik **"Add New..."** → **"Project"**
2. Di bagian **"Import Git Repository"**, cari repository **"contentai"** yang tadi dibuat
3. Klik **"Import"**
4. Di halaman konfigurasi:
   - **Framework Preset:** Other
   - Biarkan setting lainnya default
5. Klik **"Deploy"**
6. Tunggu 1-2 menit sampai proses selesai
7. Vercel akan memberi kamu URL seperti: `https://contentai-xxxx.vercel.app`
8. ✅ Website sudah online! Tapi belum bisa dipakai — kita perlu tambahkan API Key dulu.

---

## LANGKAH 5 — Dapatkan Anthropic API Key

1. Buka **console.anthropic.com**
2. Daftar atau login
3. Masuk ke menu **"API Keys"**
4. Klik **"Create Key"**
5. Beri nama key-nya (contoh: "ContentAI")
6. **Copy API key** yang muncul — simpan di tempat aman! (hanya ditampilkan sekali)
   > Key terlihat seperti: `sk-ant-api03-xxxxxxxxxxxxxxxxxx`
7. ✅ API Key siap!

> 💡 **Soal Biaya:** Anthropic memberi $5 free credit untuk akun baru. Untuk penggunaan normal, biaya per konten yang di-generate sekitar $0.001-0.01 (sangat murah).

---

## LANGKAH 6 — Tambahkan API Key ke Vercel

1. Buka **vercel.com** dan masuk ke project **contentai** kamu
2. Klik tab **"Settings"**
3. Klik **"Environment Variables"** di menu kiri
4. Klik **"Add New"**
5. Isi:
   - **Key:** `ANTHROPIC_API_KEY`
   - **Value:** paste API key yang tadi kamu copy (dimulai dengan `sk-ant-...`)
6. Centang semua environment: **Production**, **Preview**, **Development**
7. Klik **"Save"**
8. Sekarang **re-deploy**: klik tab **"Deployments"** → klik titik tiga (...) di deployment terbaru → **"Redeploy"**
9. ✅ API Key sudah terpasang!

---

## LANGKAH 7 — Test Aplikasi

1. Buka URL Vercel kamu: `https://contentai-xxxx.vercel.app`
2. Isi topik konten
3. Klik **"Generate Konten"**
4. Jika muncul hasil konten → 🎉 **BERHASIL!**

---

## 🎬 (OPSIONAL) Setup RunwayML untuk Video AI

Jika kamu ingin fitur generate video AI premium:

1. Buka **runwayml.com**
2. Daftar akun (gratis, dapat beberapa kredit percobaan)
3. Masuk ke **Settings** → **API Keys**
4. Buat API key baru
5. Di aplikasi ContentAI kamu:
   - Masuk ke tab **"Generate Video"**
   - Pilih mode **"AI Video (RunwayML)"**
   - Masukkan API key di kolom yang tersedia
6. ✅ Sekarang bisa generate video AI!

> 💡 **Harga RunwayML:** $0.05 per detik video. Video 15 detik ≈ $0.75

---

## 🔧 Cara Update Aplikasi

Kalau kamu mau mengupdate/edit aplikasi di kemudian hari:

1. Edit file di GitHub (klik file → klik ikon pensil)
2. Simpan perubahan (klik "Commit changes")
3. Vercel akan **otomatis** re-deploy dalam 1-2 menit
4. Tidak perlu melakukan apapun lagi!

---

## ❓ Masalah Umum & Solusinya

| Masalah | Penyebab | Solusi |
|---|---|---|
| Muncul "API error" | API Key salah atau belum di-set | Cek environment variable di Vercel |
| Konten tidak muncul | Limit API tercapai | Cek saldo di console.anthropic.com |
| Website tidak bisa dibuka | Deploy gagal | Cek tab "Deployments" di Vercel untuk error |
| Tombol generate tidak berfungsi | JavaScript error | Coba buka di Chrome, tekan F12 → Console |

---

## 📞 Butuh Bantuan?

Jika ada masalah saat deploy, kamu bisa:
- Screenshot error yang muncul
- Tanya di ChatGPT atau Claude dengan paste error-nya
- Cek dokumentasi Vercel di **vercel.com/docs**

---

*Panduan ini dibuat untuk ContentAI — AI Content Generator untuk YouTube & TikTok*
