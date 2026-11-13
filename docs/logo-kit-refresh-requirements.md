# MDigital — pembaruan visual berdasarkan logo kit

Status: cakupan visual REQ-38–41 disetujui pengguna pada 2026-11-14 (pilihan: Setujui visual saja). Menunggu pointer desain Palette sebelum dirilis untuk implementasi. Belum ada izin deploy.

## Tujuan dan sumber

Pengunjung mdigital.biz.id melihat identitas MDigital yang konsisten dengan logo kit terbaru, tetap dapat membaca isi dan memakai navigasi di ponsel maupun desktop.

- S1: permintaan pengguna, 2026-11-14, pesan `2385b1c4-e0f2-491a-ace4-0a4d56258022`: memperbaiki website mengikuti style logo kit.
- S2: `mdigital-logo-kit.zip`, attachment `489aac56-34af-46c7-8158-45b507ad31e0`, terutama `README.txt` dan daftar aset SVG/PNG/favicon.
- S3: repo `elhak/mdigital`, commit `e5ad6709fc1b232fa84c5b2ee96d4d886836795d`, `index.html`. Pemeriksaan source, bukan verifikasi tampilan live.
- S4: klarifikasi pengguna, pesan `ce22911c-7d92-4f2d-b572-cdd79a822ee1`: mdigital juga situs pribadi pengguna.

Panduan kit: Midnight #0A1D3B, Cyan #2BF5E3, Blue #3B82F6, Light blue #2F7BF5, Mist #E8EFFA. Wordmark Sora SemiBold; Sora atau Inter untuk teks halaman. Varian for-dark-bg/for-light-bg sesuai latar. Ruang bebas minimal selebar dot matahari; minimum mark 24 px, logo horizontal 120 px.

## Batas dan asumsi

Empat kebutuhan di bawah mencakup visual halaman utama dan identitas browser. Tidak menetapkan susunan layout baru; Palette menyiapkan acuan desain, pengguna meninjau, baru developer membangun. Prioritas 2–3 bersifat usulan (1 tertinggi).

Asumsi sementara: isi, urutan section dan tujuan tautan dipertahankan pada tahap visual. Ini belum persetujuan untuk mempertahankan klaim agency atau contoh konten saat publikasi. Tidak mencakup backend form, blog, migrasi teknologi, perubahan my.mdigital.biz.id atau deploy. Perubahan konten dan publikasi membutuhkan cakupan yang disepakati.

## REQ-38 — Logo resmi pada halaman (prioritas 2)

Sebagai pengunjung, saya mengenali MDigital dari logo kit resmi.

AC1: Logo generik pada navigasi dan footer diganti aset dari kit; daftar file yang digunakan dicatat pada handoff.
AC2: Varian for-dark-bg dipakai pada latar gelap dan for-light-bg pada latar terang; bentuk, proporsi dan warna aset tidak diubah.
AC3: Logo horizontal lebarnya minimal 120 CSS px; mark yang tampil mandiri minimal 24 CSS px; ruang bebas di setiap sisi minimal selebar dot matahari pada skala tampilnya.
AC4: Nama MDigital tersedia bagi pembaca layar; logo sebagai tautan memiliki nama aksesibel dan membawa pengguna ke awal halaman.

Sumber: S1, S2, S3. Bergantung pada pointer desain Palette.

## REQ-39 — Warna dan tipografi mengikuti kit (prioritas 2)

Sebagai pengunjung, saya melihat gaya yang konsisten antara logo dan seluruh halaman.

AC1: Navigasi, hero, Services, Process, Work, testimoni, Contact dan footer memakai pemetaan warna dan tipografi dalam acuan desain yang disetujui; handoff mencatat pemetaan per section.
AC2: Aksen merek ungu lama (#6366F1, #818CF8, #4F46E5) diganti palet kit; warna ilustrasi konten dapat tetap jika dicatat sebagai pengecualian pada acuan desain.
AC3: Teks judul dan isi memakai Sora atau Inter sesuai acuan desain. Wordmark menggunakan aset kit. Teks contoh kode boleh mempertahankan monospace sebagai pengecualian yang tercatat.
AC4: QA membandingkan halaman pada 360, 768 dan 1440 CSS px dengan acuan desain pada ukuran yang sama; tidak ada section yang tertinggal memakai gaya merek lama.

Sumber: S1, S2, S3. Penempatan warna/layout diputuskan dalam desain, bukan spesifikasi ini.

## REQ-40 — Identitas tab dan perangkat dari kit (prioritas 3)

Sebagai pengunjung, saya mengenali situs dari ikon browser dan shortcut perangkat.

AC1: Tab browser menampilkan favicon dari direktori favicon pada kit, menggantikan ikon lama/default.
AC2: Apple touch icon memakai aset 180 px yang disediakan kit; referensi favicon dan touch icon berhasil dimuat dengan HTTP 200 pada preview.
AC3: Ikon tidak terpotong atau terdistorsi; pada ukuran tab kecil menggunakan badge sederhana kit, bukan wordmark horizontal.

Sumber: S2; inferensi pendukung konsistensi identitas dari S1. Tidak mencakup pembuatan aplikasi/PWA.

## REQ-41 — Keterbacaan dan interaksi setelah perubahan visual (prioritas 2)

Sebagai pengunjung ponsel atau pengguna keyboard, saya tetap dapat membaca dan menavigasi halaman.

AC1: Pada 360, 768 dan 1440 CSS px tidak ada scroll horizontal, teks terpotong atau kontrol saling menutupi; section dan konten tetap dapat diakses.
AC2: Kontras teks biasa minimal 4.5:1, teks besar minimal 3:1; fokus keyboard dan batas kontrol yang diperlukan untuk mengenali kontrol minimal 3:1 terhadap latar bersebelahan. Palet kit bukan alasan memakai pasangan warna yang gagal.
AC3: Navigasi desktop dan menu mobile menuju section yang sesuai; menu dapat dibuka, ditutup dan dipakai dengan keyboard, dengan penanda fokus terlihat.
AC4: Konten tetap terbaca saat zoom 200% di viewport 1440 CSS px dan saat preferensi reduced motion aktif; animasi tidak menyembunyikan isi permanen.
AC5: Tidak ada error console baru dibanding baseline sebelum perubahan. Error baseline dicatat terpisah dan tidak dinyatakan lulus tanpa bukti.

Sumber: usulan nonfungsional untuk S1, perlu persetujuan pengguna.

## Temuan yang perlu keputusan sebelum cakupan konten dirilis

1. Source menyebut MDigital sebagai agency di metadata. Apakah hanya visual yang diperbarui, atau narasi juga diarahkan sebagai personal brand Hakim? Status kepemilikan pribadi tidak otomatis menentukan model layanan.
2. Ada proyek ShopStream/FitPulse/DataFlow dan testimoni yang belum diverifikasi, tautan `#`, serta email `hello@mdigital.dev`. Belum ada bukti bahwa ini konten final. Jangan mengganti atau menerbitkan klaim baru tanpa sumber pengguna.
3. Handler form mencegah submit dan menampilkan pesan sukses; pengiriman pesan belum terlihat di source. Pengiriman kontak bukan bagian dari refresh visual. Jika publikasi diminta, perilaku dan alamat kontak harus diputuskan dahulu.

Tidak ada kode aplikasi, git history, server atau situs live yang diubah oleh penyusunan dokumen ini.

## Keputusan pengguna — 2026-11-14

Pengguna menyetujui visual saja. Narasi dan urutan konten dipertahankan; perubahan menjadi narasi personal tidak masuk cakupan. Temuan konten contoh, tautan dan form tetap tercatat untuk diputuskan sebelum publikasi. Persetujuan ini tidak menyatakan konten tersebut telah diverifikasi.
