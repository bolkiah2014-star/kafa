# Sistem Pengurusan KAFA — Pautan Pendek (GitHub Pages)

Folder ini ialah "pintu masuk" kepada Sistem Pengurusan KAFA (Google Apps Script).
Pengguna membuka pautan pendek, contohnya **https://bolkiah2014-star.github.io/kafa/**.
URL Apps Script yang panjang tidak dipaparkan dalam bar alamat.

## Isi folder
| Fail | Fungsi |
|---|---|
| `index.html` | Halaman utama: memaparkan sistem dalam skrin penuh, skrin pembuka berikon dan perangkap butang **Back** |
| `config.js` | **Satu-satunya fail yang perlu diubah**: tampal URL Web App Apps Script |
| `manifest.webmanifest`, `sw.js` | Membolehkan sistem **dipasang seperti aplikasi** di telefon (PWA) |
| `icons/` | Ikon sistem (favicon, ikon skrin utama telefon) |

## Langkah pemasangan (±10 minit)
1. **Apps Script:** Deploy → Manage deployments → salin **Web app URL** (berakhir dengan `/exec`).
   Pastikan *Who has access* = **Anyone**.
2. **GitHub:** log masuk → **New repository** → nama `kafa` → **Public** → *Create repository*.
3. Klik **uploading an existing file** → seret **semua isi** folder ini (termasuk folder `icons`) → **Commit changes**.
4. Buka `config.js` dalam GitHub → ikon ✏️ (Edit) → tampal URL tadi pada `GAS_URL` → **Commit changes**.
5. **Settings → Pages** → *Source*: **Deploy from a branch** → Branch **main** / **(root)** → **Save**.
   Selepas 1–2 minit, pautan dipaparkan: `https://bolkiah2014-star.github.io/kafa/`
6. Dalam helaian **TETAPAN**, isi **URL_APLIKASI** dengan pautan tersebut.
   Kod QR kehadiran guru dan ikon tab akan menggunakan pautan pendek ini.

## Pasang di telefon (seperti aplikasi)
- **Android (Chrome):** buka pautan → menu ⋮ → **Install app / Tambah ke skrin utama**.
- **iPhone (Safari):** buka pautan → butang Kongsi → **Add to Home Screen**.

## Butang Back
Butang Back telefon atau pelayar **tidak menutup aplikasi**. Ia akan:
1. menutup tetingkap yang terbuka, kemudian
2. menutup menu sisi, kemudian
3. kembali ke skrin sebelumnya, sehingga ke Dashboard.

Aplikasi hanya ditutup apabila pengguna menekan **✖️ Tutup Aplikasi** (menu sisi atau Menu).

## Jika sistem lambat dibuka atau tidak terbuka
Selepas 20 saat, butang **Buka Terus Sistem** akan dipaparkan. Butang ini membuka sistem terus tanpa pautan pendek.
Ini mungkin berlaku jika akses deployment ditetapkan *"Anyone within moe-dl.edu.my"* dan telefon menyekat log masuk Google di dalam bingkai.
Penyelesaian terbaik: tetapkan akses kepada **Anyone**.

> Nota: URL Apps Script disembunyikan daripada bar alamat sahaja. Ia masih kelihatan dalam `config.js` kepada sesiapa yang memeriksa kod halaman. Semua akses tetap memerlukan ID log masuk sistem.

## Kemas kini kemudian
Kemas kini kod sistem dibuat dalam Apps Script seperti biasa: **Deploy → Manage deployments → Edit → New version**.
URL `/exec` tidak berubah, jadi folder ini **tidak perlu diubah lagi**.
