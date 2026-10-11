# Website Resmi Dentiva

Landing page resmi **dentiva.id**: rekam medis elektronik untuk klinik gigi.

Situs statis murni (HTML, CSS, dan JavaScript dalam satu file). Tidak perlu `npm install` atau proses build.

## Isi folder

| File | Fungsi |
|------|--------|
| `index.html` | Halaman utama, termasuk Kebijakan Privasi (`#kebijakan-privasi`) dan Syarat & Ketentuan (`#syarat-ketentuan`) |
| `unduh.html` | Halaman unduhan aplikasi desktop Windows & macOS (`/unduh`) |
| `dentiva-app-icon.png` | Ikon aplikasi desktop (dipakai di halaman unduhan) |
| `404.html` | Halaman "tidak ditemukan" |
| `og-image.png` | Gambar preview saat link dibagikan (WhatsApp, Facebook, LinkedIn) |
| `dentiva-logo.png`, `favicon.ico`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` | Logo dan ikon |
| `site.webmanifest` | Info ikon untuk perangkat mobile |
| `robots.txt`, `sitemap.xml` | Untuk mesin pencari |
| `vercel.json` | Pengaturan header keamanan dan cache di Vercel |

## Melihat di komputer

Klik dua kali `index.html` untuk membukanya di browser. Semua fitur berjalan tanpa server.

## Deploy ke Vercel (disarankan)

1. Buat repo baru di GitHub, misalnya `dentiva-website`, lalu upload semua file di folder ini.
2. Di [vercel.com](https://vercel.com), pilih **Add New → Project**, lalu import repo tersebut.
3. Framework Preset: **Other**. Kosongkan Build Command dan Output Directory, lalu klik **Deploy**.
4. Di **Settings → Domains**, tambahkan `dentiva.id` dan `www.dentiva.id`, lalu ikuti instruksi DNS dari Vercel.

> Repo aplikasi Dentiva (proyek Vite) sebaiknya dipindah ke subdomain, misalnya `app.dentiva.id`. Jangan gabungkan website ini ke root repo aplikasi karena `index.html` keduanya akan bentrok.

## Alternatif: GitHub Pages

Buka **Settings → Pages** di repo, pilih branch `main` dan folder `/ (root)`, lalu simpan. `vercel.json` akan diabaikan dan situs tetap berjalan normal.

## Wajib diisi sebelum dipublikasikan

Cari teks dalam `[kurung siku]` di `index.html` dan ganti dengan data asli:

- `[NAMA BADAN USAHA]`, `[Alamat lengkap kantor]`, `[nomor NIB]`
- `[nomor]` pada kontak WhatsApp di footer
- Di Kebijakan Privasi & Syarat Ketentuan: `[tanggal berlaku]`, `[lokasi server/region]`, jangka waktu `[jumlah]`, kebijakan refund, dan lembaga penyelesaian sengketa

Ganti juga nomor WhatsApp di bagian awal script (cari `WA_NUMBER`), gunakan format `62...` tanpa tanda `+` atau spasi:

```js
var WA_NUMBER = "6281234567890";
```

Jika aplikasi sudah pindah ke subdomain, ganti semua `https://dentiva-main.vercel.app` dengan alamat barunya (misalnya `https://app.dentiva.id`).

> Dokumen Kebijakan Privasi dan Syarat & Ketentuan masih berupa draf. Mintalah konsultan hukum meninjaunya sebelum dipublikasikan.

## Setelah online

- Daftarkan `https://dentiva.id/sitemap.xml` di [Google Search Console](https://search.google.com/search-console).
- Cek tampilan preview link di [opengraph.xyz](https://www.opengraph.xyz) atau dengan mengirim link ke WhatsApp sendiri.
- Perbarui `<lastmod>` di `sitemap.xml` setiap ada perubahan besar.

## Merilis versi baru aplikasi desktop

1. Unggah installer hasil build ke Storage server Dentiva di Indonesia (`https://api.dentiva.id`, bucket
   `downloads`) dengan nama aslinya (`Dentiva_<versi>_x64-setup.exe`, `Dentiva_<versi>_universal.dmg`) —
   di server: `/opt/dentiva/bin/unggah-installer.sh <berkas>…` (lihat repo dentiva-main, `infra/vps/README.md`).
2. Di `unduh.html`, ubah `var VERSION = "…";` menjadi versi baru, lalu commit & deploy.
   Ukuran dan tanggal berkas tampil otomatis.
