# Pengindeksan website resmi Dentiva

Website publik: https://dentiva.id/ . Aplikasi klinik, akun staf, dan data pasien tidak termasuk sitemap website ini.

## Kondisi teknis

- Beranda dan `/unduh` berupa HTML statis sehingga konten utama tersedia tanpa menjalankan JavaScript.
- Halaman publik mempunyai title, description, canonical dan `index,follow`.
- `robots.txt` mengizinkan crawling dan menunjuk `https://dentiva.id/sitemap.xml`.
- Sitemap hanya berisi halaman publik yang tersedia. `lastmod` harus mengikuti perubahan konten nyata.
- `www.dentiva.id` diarahkan permanen ke `dentiva.id`, sambil mempertahankan path dan query.
- Structured data WebSite/Organization memakai nama Dentiva dan URL resmi. Jangan menambahkan nama badan usaha, alamat, rating, atau testimoni yang belum terverifikasi.
- Halaman 404 tetap berstatus 404 dan `noindex`.

## Google Search Console: langkah pemilik akun

1. Buka https://search.google.com/search-console dengan akun Google pemilik.
2. Tambahkan properti **Awalan URL** `https://dentiva.id/`.
3. Pilih **Tag HTML** dan salin tag `google-site-verification` yang diberikan Google. Tag tersebut adalah bukti verifikasi publik, bukan kata sandi. Pasang di `<head>` beranda, deploy, lalu tekan **Verifikasi**. Pertahankan tag setelah berhasil.
4. Buka **Peta situs / Sitemaps**, kirim `https://dentiva.id/sitemap.xml`.
5. Di **Inspeksi URL**, periksa `https://dentiva.id/`, jalankan **Uji URL aktif**, lalu **Minta pengindeksan**. Ulangi untuk `/unduh`.
6. Pantau laporan **Pengindeksan halaman** dan alasan halaman belum diindeks. Jangan menganggap pencarian `site:` sebagai pengganti laporan properti Search Console.

Alternatif: properti **Domain** `dentiva.id` dengan TXT DNS dari Google. Ini mencakup semua protokol/subdomain, tetapi memerlukan akses DNS Hostinger. Tambahkan TXT verifikasi yang diberikan Google tanpa mengubah A/CNAME/MX; jangan mengarang token atau menghapus TXT lain. Verifikasi kepemilikan domain tidak berarti halaman private perlu diindeks.

## Harapan yang realistis

Membeli domain tidak otomatis mengindeks situs. Google menentukan jadwal crawl, pengindeksan dan peringkat. Sitemap, metadata atau permintaan indeks tidak menjamin tanggal muncul maupun posisi pertama. Nama Dentiva juga dipakai situs lain; identitas Indonesia, konten produk yang jelas, dan tautan dari kanal resmi membantu pengguna membedakan situs ini.

Tambahkan tautan ke `https://dentiva.id/` pada profil bisnis/media sosial resmi yang benar-benar dimiliki. Hindari backlink berbayar/spam dan rating palsu. Lengkapi placeholder identitas/kontak pada konten situs dengan data nyata dari pemilik; perubahan SEO tidak menggantikan data tersebut.

Referensi: [Google: minta crawling ulang](https://developers.google.com/search/docs/crawling-indexing/ask-google-to-recrawl), [Google: sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap), [Google: site names](https://developers.google.com/search/docs/appearance/site-names).
