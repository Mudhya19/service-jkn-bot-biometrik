
# 🚀 JKN Biometrik Bot Setup di PowerShell (Windows)

Panduan lengkap untuk menjadikan **Bot JKN Biometrik** berjalan otomatis sebagai **service di PowerShell CLI (Windows)**, tanpa harus menjalankan manual lagi.

---

## 📥 1. Download dan Ekstrak

Unduh file ZIP bot dari:
[https://basoro.id/downloads/jkn-biometrik-bot.zip](https://basoro.id/downloads/jkn-biometrik-bot.zip)

Ekstrak ke:
```
C:\laragon\www\jkn-biometrik-bot\node
```

---

## ⚙️ 2. Instalasi Prasyarat

### a. Install Node.js (LTS 18+)
Unduh dari [https://nodejs.org](https://nodejs.org) dan install.

### b. Verifikasi Instalasi
```powershell
node -v
npm -v
```

---

## 🔧 3. Install PM2 (Process Manager)

```powershell
npm install -g pm2
```

---

## 📦 4. Setup Project Bot

Masuk ke folder:
```powershell
cd "C:\laragon\www\jkn-biometrik-bot\node"
```

Install dependensi jika ada:
```powershell
npm install
```

---

## 🚀 5. Jalankan Bot via PM2

```powershell
pm2 start index.js --name jkn-bot
```

---

## 🔁 6. Jadikan Bot Otomatis Saat Boot

### a. Jalankan perintah berikut:
```powershell
pm2 startup
```

### b. Ikuti perintah yang muncul, contoh:
```powershell
pm2-startup install
```

Jika `pm2-startup` tidak dikenal:
```powershell
npm install -g pm2-windows-startup
pm2-startup install
```

### c. Simpan konfigurasi
```powershell
pm2 save
```

---

## 🔍 7. Verifikasi dan Cek

### Cek status:
```powershell
pm2 status
```

### Cek log:
```powershell
pm2 logs jkn-bot
```

### Akses di browser:
```
http://localhost:3000
```

---

## 🧾 Catatan Warning `assert`

Jika muncul warning seperti:
```
'assert' is deprecated in import statements...
```

Itu hanya peringatan, **tidak mempengaruhi fungsi bot**. Bisa diabaikan.

---

## 🧰 Perintah Tambahan PM2

| Fungsi        | Perintah                       |
|---------------|--------------------------------|
| Stop bot      | `pm2 stop jkn-bot`             |
| Restart bot   | `pm2 restart jkn-bot`          |
| Hapus bot     | `pm2 delete jkn-bot`           |
| Lihat log     | `pm2 logs jkn-bot`             |
| Simpan ulang  | `pm2 save`                     |

---

## ✅ Selesai!

Sekarang bot akan **selalu aktif otomatis** saat Windows boot tanpa perlu buka terminal atau klik apapun lagi!

---
