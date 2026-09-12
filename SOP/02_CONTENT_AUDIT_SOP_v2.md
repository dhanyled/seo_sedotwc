# SOP Master Audit Mutu Konten & Quality Gate (Versi 2.0)

> **Status Dokumen:** Master SOP Quality Assurance & Audit Konten (V2.0 - Active).  
> **Website Target:** https://sedotwcdijakarta.com/  
> **Target Pengguna:** Auditor Konten, SEO Specialist, Technical Reviewer.  
> **Posisi dalam Siklus:** Tahap 3 — Quality Control Gate Sebelum Publikasi.  
> 
> **🔗 DOKUMEN TERKAIT & HUBUNGAN FUNGSIONAL (RECIPROCAL GRAPH):**  
> - **Upstream Subject (Konten yang Diaudit):** [`SOP/01_CONTENT_WRITER_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/01_CONTENT_WRITER_SOP_v2.md)  
>   *(Standar gaya penulisan, human-first, bahasa awam, dynamic word count, dan struktur AIDA/PAS yang wajib diuji).*  
> - **Roadmap & Slug Validation:** [`Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md)  
>   *(Auditor memvalidasi apakah artikel yang diaudit sesuai dengan Kode Silo, Slug URL, dan Fokus Keyword resmi di Roadmap).*  
> - **Verifikasi Passage Chunks & AI Search:** [`SOP/03_AI_SEARCH_&_FAN_OUT_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/03_AI_SEARCH_&_FAN_OUT_SOP_v2.md)  
>   *(Auditor memvalidasi keberadaan passage chunks mandiri 40–80 kata yang mengikat brand dan WhatsApp).*  
> - **Verifikasi Widget Gamifikasi:** [`Silo/03_GAMIFIKASI_DWELL_TIME_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/03_GAMIFIKASI_DWELL_TIME_v2.md)  
>   *(Auditor memastikan kuis diagnosa mandiri atau kalkulator selang telah terpasang rapi di paruh artikel).*  
> - **Verifikasi Media & Visual WebP:** [`SOP/06_IMAGE_&_MEDIA_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/06_IMAGE_&_MEDIA_SOP_v2.md)  
>   *(Auditor memeriksa Two-Way Media Protocol, 2N media unik, Zero Distortion biner, dan Anti-Rename Bypass).*  
> - **Master Rules & Guardrails:** [`.agents/AGENTS.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/AGENTS.md)  

---

## 🛡️ 1. Mindset Auditor & 4 Status Verifikasi Bukti

Auditor bertindak sebagai **pemeriksa independen yang kritis (*skeptical quality reviewer*)**. Konten tidak boleh diloloskan hanya karena terlihat panjang atau terdengar bagus jika tidak memenuhi pembuktian lapangan dan kepatuhan teknis.

Setiap butir pemeriksaan wajib diberi salah satu dari 4 status verifikasi:
* **`PASS`:** Terbukti memenuhi standar secara faktual dan teknis berdasarkan bukti nyata.
* **`PARTIAL`:** Memiliki komponen yang diminta namun eksekusinya masih lemah, dangkal, atau belum tuntas.
* **`FAIL`:** Ditemukan pelanggaran standar yang nyata terhadap aturan operasional atau guardrail.
* **`UNVERIFIED` (Verification Hold):** Persyaratan belum bisa dibuktikan karena membutuhkan pengecekan server live WordPress, respon API REST, atau konfirmasi tim lapangan. **Status UNVERIFIED dilarang dianggap PASS.** Draf berstatus ini wajib ditahan (*hold*) sampai verifikasi tuntas.

---

## 🚪 2. Sembilan Gerbang Mutu Mutlak (9 Hard Gates)

Draf konten **wajib lolos 9 Hard Gates** berikut dengan status `PASS` sebelum diizinkan terbit:

### ⛔ Hard Gate 1: Integritas Kontak & Tombol WhatsApp
* [ ] Tautan WhatsApp menggunakan format resmi yang valid (`https://wa.me/62...` atau shortcode Click-to-Chat).
* [ ] Teks pesan pembuka WhatsApp otomatis (*prefilled text*) mencantumkan nama layanan dan lokasi asal pembaca (misal: *"Halo admin Sedot WC, saya mau konsultasi kloset mampet di daerah..."*).
* [ ] Tombol CTA mudah disentuh di ponsel dengan target sentuh minimal **44 × 44 px**.

### ⛔ Hard Gate 2: Proteksi Halaman Sakral 749 & Isolasi MU-Plugin
* [ ] Tidak memodifikasi layout, grid, atau struktur kontainer Elementor di Halaman 749 (`/landing-page-google-ads/`).
* [ ] Tidak menghapus atau merusak shortcode `[ifso_bulks]` dan `[if_so_dki]`.
* [ ] Kode CSS/JS tidak bertabrakan dengan MU-Plugin `ab-testing-wa-master.php`.
* [ ] **Zero Linking to 749:** Memastikan **TIDAK ADA** internal link dari artikel blog yang mengarah ke Halaman 749.

### ⛔ Hard Gate 3: Variasi Sintaksis, Burstiness & Anti-AI Tell
* [ ] **Zero Parallel Triads:** Tidak ada pola 3 klausa berurutan ("X, Y, dan Z" atau 3 kalimat berstruktur subjek-predikat identik berturut-turut).
* [ ] **Variasi Ritme Kalimat (*Burstiness*):** Terdapat perpaduan kalimat pendek (< 8 kata) yang tegas dan kalimat penjelas majemuk (> 25 kata).
* [ ] **Pembersihan Kosakata Arkais:** Bebas dari kata kaku hasil terjemahan mesin (*galibnya, rerata, sekonyong-konyong, saban, asa, memboyong*).
* [ ] Bebas dari kata pembuka AI klise (*"Dalam era modern...", "Menjaga kebersihan...", "Kesimpulannya..."*).
* [ ] Istilah teknis (*septic tank, grease trap, STP, vakum high-pressure, drain snake*) selalu disertai padanan bahasa awam yang mudah dipahami.
* [ ] Tidak ada paragraf dinding teks (> 3 baris kalimat per paragraf).

### ⛔ Hard Gate 4: Realisme Operasional Lapangan & Wilayah Jabodetabek
* [ ] Informasi jangkauan armada akurat mencakup 5 kotamadya DKI Jakarta, Depok, Tangerang, dan Bekasi.
* [ ] Mencantumkan solusi riil kendala pemukiman padat (kapasitas selang panjang 50–100 meter dan armada truk engkel untuk masuk gang sempit).
* [ ] Pembuangan limbah disebutkan secara resmi ke Instalasi Pengolahan Lumpur Tinja (IPLT) Pemda DKI Jakarta: **IPLT Duri Kosambi** (Jakarta Barat) dan **IPLT Pulo Gebang** (Jakarta Timur).

### ⛔ Hard Gate 5: Integritas SEO, SEOPress & Evidence-Grade Verification
* [ ] **Exact Match Fokus Keyword pada Judul H1:** Tag `<h1>` memuat Fokus Keyword secara utuh dan alami.
* [ ] **Struktur URL Bersih:** Permalink slug memuat Fokus Keyword secara utuh (`/fokus-keyword/`).
* [ ] **Distribusi Keyword Turunan pada H2/H3:** Seluruh kata kunci turunan dari tabel Silo/04 terpasang sebagai sub-heading H2/H3 dan dijawab tuntas minimal 150 kata per heading.
* [ ] **Cakupan LSI & Entitas Semantik Wajib:** Memuat entitas teknis sanitasi wajib dari tabel Silo/04 (*bakteri anaerob, pipa hawa, resapan tanah, IPLT Duri Kosambi/Pulo Gebang, truk engkel, dll.*) secara ko-okurensi alami tanpa keyword stuffing.
* [ ] **Uji Diferensiasi Intensi (Anti-Kanibalisasi):** Sudut pandang artikel terbukti unik dan tidak tumpang tindih (*zero cannibalization*) dengan artikel tetangga seklaster sesuai batasan intensi di Silo/01.
* [ ] **Taksonomi:** Tepat memilih **1 Kategori Silo** resmi (ID 20–24), dan **Tag berjumlah 0 (NOL - 0 Tag Policy)**.
* [ ] **Metadata SEOPress:** `_seopress_titles_title` terpasang exact match, `_seopress_titles_desc` terisi 140–160 karakter dengan ajakan bertindak (tidak kosong), dan `_seopress_analysis_target_kw` terisi fokus keyword resmi.
* [ ] **Evidence-Grade External Link Test:** Rujukan ke regulasi sanitasi (SNI 2398:2017, Permen LHK No. P.68/2016, Perda DKI No. 3/2013) terverifikasi lolos uji 4-Object: `[Kalimat Klaim] <-> [Anchor Text] <-> [Final URL] <-> [Isi Sumber]`. Wajib live HTTP 200 deep-link (bukan broken, bukan soft-404, dan bukan root homepage).
* [ ] **Zero Front-End Code Leaks:** Tidak ada kode JSON-LD mentah, tag `<script>`, kode CSS mentah, atau komentar HTML yang bocor di layar pembaca akibat filter sanitasi `wp_kses`.
* [ ] **Zero Frontmatter & Editorial Leaks:** Memastikan `post_content` bersih 100% dari header YAML markdown (`--- code: S... ---`) dan blok catatan internal redaksi (`[REKOMENDASI INBOUND LINK - ANTI-ORPHAN]`).

### ⛔ Hard Gate 6: Anti-Orphan Post (Alur Operasional 3 Langkah)
* [ ] Draf penulis memuat blok `[REKOMENDASI INBOUND LINK]` yang jelas menunjuk 1–2 artikel seklaster eksisting (khusus dokumen draf lokal).
* [ ] Publisher telah mengeksekusi pembaruan pada 1–2 artikel lama tersebut di WordPress dan membersihkan blok rekomendasi dari `post_content`.
* [ ] Auditor memverifikasi bahwa link masuk (*inbound link*) menuju artikel baru sudah live berstatus HTTP 200 (Status 0 orphan post).

### ⛔ Hard Gate 7: Manajemen Media, Format WebP & Zero Distortion
* [ ] Mengikuti standar penuh [`SOP/06_IMAGE_&_MEDIA_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/06_IMAGE_&_MEDIA_SOP_v2.md).
* [ ] **Two-Way Media Protocol:** Memiliki `featured_media > 0` DAN minimal 1 gambar konten independen di badan teks ($N$ artikel = $2N$ media unik di database).
* [ ] **Core Business & Content Alignment:** Visual 100% selaras dengan industri sanitasi Jabodetabek (truk tangki vakum, seragam teknisi, diagram 3D septic tank SNI / spiral drain cleaner / grease trap FOG / STP aerasi). DILARANG foto pertukangan (bor, palu) atau stock photo asing.
* [ ] **Cache-Busting Compliance:** Jika merupakan gambar revisi/pengganti, wajib menggunakan *versioned filename* atau query string `?v=N` agar tidak tertahan di cache CDN/browser pengunjung.
* [ ] **Anti-Self & Cross Duplicate:** Featured Image berbeda dengan In-Content Image, serta tidak mendaur ulang gambar dari artikel lain.
* [ ] **Zero Distortion:** Atribut HTML `width` dan `height` pada tag `<img>` mencerminkan rasio asli biner file (misal 1200 × 675 px), bukan dipaksa ukuran yang menggepengkan gambar.
* [ ] **Anti-Rename Bypass & Larangan Comot Cache:** Bukan hasil rename dari gambar lama dan bukan comot dari folder cache lokal tanpa izin.
* [ ] **Format Berkas:** 100% `.webp` terkompresi (< 100 KB untuk Featured, < 80 KB untuk Content) dengan atribut `alt` deskriptif.

### ⛔ Hard Gate 8: Aksesibilitas WCAG 2.1 AA Mobile & Isolasi Floating Button
* [ ] Rasio kontras teks reguler minimal **4.5 : 1** terhadap latar belakang (WCAG AA).
* [ ] Rasio kontras teks besar / tombol CTA minimal **3.0 : 1**.
* [ ] **Isolasi Floating CTA:** TIDAK ADA tombol floating buatan manual di dalam tubuh artikel yang bertabrakan dengan floating CTA global MU-Plugin (`#manual-floating-wa` / `#ht-ctc-chat`).
* [ ] Tampilan halaman responsif tanpa pergeseran tata letak kumulatif (*CLS*) pada layar selebar 320 px.

### ⛔ Hard Gate 9: Jalur Konversi Ganda, Gamifikasi & Garansi Tuntas
* [ ] Terdapat CTA WhatsApp cepat di bagian atas (*above the fold*) untuk kebutuhan darurat.
* [ ] Terdapat internal link kontekstual ke Artikel Pilar Silo-nya atau Landing Page Wilayah Organik (`/jakarta-selatan/`, `/sedot-wc-terdekat/`). Maksimal 2–3 link per artikel.
* [ ] **Gamifikasi via Shortcode:** Modul interaktif (Kuis Diagnosa / Kalkulator Selang) terpasang melalui shortcode resmi (`[kuis_diagnosa_septic]`) via MU-Plugin `sanitasi-gamifikasi.php`, BUKAN raw form HTML/inline script yang rawan rusak oleh `wp_filter_post_kses` dan `wpautop`.
* [ ] Menyertakan komitmen keterbukaan biaya di awal (*zero hidden cost*) dan garansi pengerjaan ulang jika saluran masih mampet.

---

## 📋 3. Format Laporan Hasil Audit (Audit Output Template)

```markdown
### Laporan Hasil Audit Mutu Konten: [Judul Artikel / Halaman]
- **Kode Silo / Roadmap:** [Contoh: S1-P / S2-01]
- **Fokus Keyword:** [Keyword Resmi]
- **Auditor:** [Nama AI / Quality Auditor]
- **Tanggal Audit:** [YYYY-MM-DD]
- **Status Akhir:** [🟢 PASSED / 🔴 REVISION NEEDED / 🟡 VERIFICATION HOLD]

| Hard Gate | Status | Catatan Temuan Bukti & Rekomendasi |
| :--- | :---: | :--- |
| HG 1: Kontak & CTA WA | PASS | Tautan wa.me aktif & prefilled text sesuai wilayah (touch 48x48px) |
| HG 2: Proteksi Halaman 749 | PASS | Nol link ke 749, Elementor steril, CSS/JS aman |
| HG 3: Burstiness & Anti-AI | PASS | Zero parallel triads, ritme kalimat bervariasi, bebas kata arkais |
| HG 4: Realisme Jabodetabek | PASS | Disebutkan selang 100m, truk engkel gang sempit, IPLT Duri Kosambi |
| HG 5: SEO, SEOPress & Evidence Link | PASS | H1 Exact Match, 0 Tag, 1 Silo, rujukan SNI 2398:2017 HTTP 200 deep-link, 0 code leaks |
| HG 6: Anti-Orphan Post (3 Langkah) | PASS | Inbound link dari [Slug Artikel Lama] terverifikasi aktif HTTP 200 |
| HG 7: Visual WebP & Zero Distortion | PASS | Two-way media terpenuhi, WebP HD, rasio 16:9 proporsional, usage count === 1 |
| HG 8: WCAG 2.1 Mobile AA | PASS | Touch target valid, kontras 5.1:1, floating CTA steril |
| HG 9: Jalur Ganda & Gamifikasi | PASS | Top CTA + link Pilar Silo, Kuis Diagnosa terpasang, garansi tuntas jelas |
```
