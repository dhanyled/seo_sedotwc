# SOP Master Penulis Konten & Copywriting Edukasi Sanitasi (Versi 2.0)

> **Status Dokumen:** Master SOP Penulisan Konten Blog & Edukasi Organik (V2.0 - Active).  
> **Website Target:** https://sedotwcdijakarta.com/  
> **Posisi dalam Siklus:** Tahap 2 — Eksekusi Penulisan Draf Konten.  
> 
> **🔗 DOKUMEN TERKAIT & HUBUNGAN FUNGSIONAL (RECIPROCAL GRAPH):**  
> - **Upstream Input (Sumber Judul & Keyword):** [`Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md)  
>   *(Penulis WAJIB mengambil judul H1, slug URL, dan fokus keyword dari daftar 30 rencana artikel di Roadmap ini).*  
> - **Struktur Otoritas Silo:** [`Silo/01_TOPICAL_AUTHORITY_&_5_SILO_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/01_TOPICAL_AUTHORITY_&_5_SILO_v2.md)  
>   *(Menentukan kategori WordPress artikel dan aturan isolasi internal link vertikal).*  
> - **Kesiapan AI Search & RAG:** [`SOP/03_AI_SEARCH_&_FAN_OUT_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/03_AI_SEARCH_&_FAN_OUT_SOP_v2.md)  
>   *(Wajib menyisipkan passage chunks 40–80 kata yang mengikat brand dan nomor WhatsApp).*  
> - **Aset Interaktif Penahan Dwell Time:** [`Silo/03_GAMIFIKASI_DWELL_TIME_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/03_GAMIFIKASI_DWELL_TIME_v2.md)  
>   *(Menyematkan Kuis Diagnosa Mampet vs Penuh atau Kalkulator Selang di paruh tengah artikel).*  
> - **Standar Visual & Manajemen Media:** [`SOP/06_IMAGE_&_MEDIA_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/06_IMAGE_&_MEDIA_SOP_v2.md)  
>   *(Protokol 2N media unik, format WebP HD, zero distortion, dan anti-rename bypass).*  
> - **Downstream Quality Gate (QC Auditor):** [`SOP/02_CONTENT_AUDIT_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/02_CONTENT_AUDIT_SOP_v2.md)  
>   *(Draf yang ditulis diuji terhadap Hard Gates sebelum diizinkan terbit).*  
> - **Master Rules & Guardrails:** [`.agents/AGENTS.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/AGENTS.md)  

---

## 🛑 GUARDRAIL MUTLAK: PROTEKSI HALAMAN SAKRAL 749 & ELEMENTOR
1. **DILARANG MENGARAHKAN INTERNAL LINK KE HALAMAN 749:**  
   Halaman 749 (`/landing-page-google-ads/`) adalah halaman kampanye berbayar Google Ads (GSN). **DILARANG KERAS** menyuntikkan internal link dari artikel blog ke Halaman 749 agar Quality Score dan tracking iklan tidak tercampur.
2. **ALIRAN MONEY TRAFFIC HANYA KE HALAMAN WILAYAH ATAU WHATSAPP:**  
   Internal link komersial artikel blog **HANYA BOLEH** diarahkan ke Landing Page Wilayah Organik terkait (misal: `/jakarta-selatan/`, `/jakarta-barat/`, `/sedot-wc-terdekat/`) atau langsung ke tombol chat WhatsApp resmi `0813-8888-4349`.

---

## 🎯 1. Filosofi Penulisan: Human-First, Anti-AI Tell & Skimmable

Konten artikel di `sedotwcdijakarta.com` ditulis untuk **pembaca nyata yang sedang menghadapi masalah darurat sanitasi** (WC mampet, septic tank meluap, wastafel mampet, grease trap berbau busuk). 

### 1.1 Standar Penghitungan Kata Resmi (`@wordpress/wordcount`), Riset Kompetitor SERP & Dynamic Word Count
* **Modul Resmi Penghitungan Kata:** Seluruh penghitungan jumlah kata wajib menggunakan algoritma resmi WordPress Block Editor (`@wordpress/wordcount`) mode `'words'`. DILARANG menggunakan metode `split(/\s+/)` mentah yang menghitung emoji (`📌`, `💬`) atau simbol tanda baca mandiri (`+`, `/`, `-`).
* **Pemisahan Judul H1:** Judul utama (`<h1>`) berada di luar tubuh postingan sehingga TIDAK dihitung ke dalam indikator jumlah kata badan artikel WordPress.
* **Protokol Riset Kompetitor SERP Top 3:**
  - **Analisis Kesenjangan Konten (*Content Gap Analysis*):** Sebelum menulis, telusuri kompetitor top 3 di Google Indonesia untuk fokus keyword. Temukan kelemahan umum kompetitor lokal (tulisan tipis/dangkal 400–600 kata, tanpa rujukan SNI 2398:2017, minim edukasi hukum Perda DKI No. 3/2013, tidak transparan tarif per tangki vs $m^3$, dan tidak memberi solusi gang sempit selang 100m).
  - **Penyuntikan Information Gain Riil:** Setiap artikel wajib mengisi kesenjangan tersebut dengan data teknis operasional nyata (biologi bakteri anaerob, tabel interval sedot, legalitas manifest IPLT Duri Kosambi / Pulo Gebang, dan kuis diagnosa mandiri).
* **Formula Dynamic Word Count Baseline:**
  $$\text{Target Minimal Kata} = \max(1.000\text{ kata},\; \text{Rata-rata Kata Kompetitor Top 3} \times 1.10\text{ s/d }1.20)$$
  - *Jika kompetitor rata-rata < 1.000 kata:* Draf wajib minimal **1.000 kata** front-end murni (*floor minimum*).
  - *Jika kompetitor rata-rata > 1.000 kata:* Draf wajib melampaui rata-rata kompetitor minimal +10% s/d +20% dengan menyuntikkan *Information Gain* nyata.

### 1.2 Distribusi Kata Kunci 3 Tingkat (Fokus, Turunan & LSI Semantik)

Penulis wajib menerapkan penyerapan kata kunci yang terstruktur mengacu pada daftar di [`Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md):

* **1. Fokus Keyword (Primary Query):**
  - **Rentang Baseline:** Densitas fokus keyword dijaga pada rentang **0,4% – 1,0%** dari total kata badan artikel.
  - **Penempatan Mutlak:** Wajib muncul di **Judul H1** (exact match), **100 kata pertama lead**, **1 sub-heading H2**, dan **paragraf penutup**.
  - **Prinsip Guardrail:** Densitas adalah batas aman agar tulisan tidak *under-optimized* atau *keyword-stuffed*, BUKAN target matematis kaku untuk memaksakan pengulangan kata yang canggung.
  - DILARANG mengulang fokus keyword dua kali dalam satu kalimat pendek atau kalimat yang langsung bersebelahan.

* **2. Keyword Turunan (Secondary / Long-Tail Queries):**
  - Diambil langsung dari kolom *Keyword Turunan (H2/H3)* pada tabel Silo/04.
  - **Penempatan Mutlak:** Wajib dijadikan sebagai judul sub-bagian **Heading 2 (`<h2>`) atau Heading 3 (`<h3>`)** secara terdistribusi.
  - Dilarang menumpuk semua keyword turunan di paragraf pembuka. Setiap heading turunan wajib dijawab tuntas dengan solusi teknis minimal 150–250 kata.

* **3. LSI & Entitas Semantik Sanitasi Wajib:**
  - Diambil dari kolom *LSI & Entitas Semantik Wajib* pada tabel Silo/04 (contoh: *bakteri anaerob, pipa hawa T, resapan tanah, truk engkel, selang 100m, IPLT Duri Kosambi/Pulo Gebang*).
  - **Penempatan Alami:** Disuntikkan secara ko-okurensi (*co-occurrence*) ke dalam kalimat penjelasan teknis untuk membuktikan kedalaman *Subject Matter Expertise* (SME) tanpa dipaksakan.

* **4. Protokol Batasan Intensi (Anti-Kanibalisasi Seklaster):**
  - Sebelum menulis, Penulis **WAJIB** mengecek kolom *Search Intent* di Silo/04 dan sudut pandang artikel tetangga seklaster.
  - Dilarang mengulang pengujian gejala kloset yang sama jika artikel tetangga sudah membahasnya (misal: bedakan secara tegas bahasan *Ciri Septic Tank Penuh [S1-01]* dengan *Resapan Tanah Jenuh Mampet [S1-05]*).

### 1.3 Variasi Sintaksis, Burstiness & Zero Parallel Triads
* **Tinggi Variasi Ritme Kalimat (*Burstiness*):** AI selalu menghasilkan panjang kalimat yang monoton (14–18 kata). Penulis WAJIB memadukan kalimat pendek tegas (< 8 kata) dengan kalimat penjelas majemuk (> 25 kata) di setiap bagian.
* **Zero Parallel Triads:** DILARANG KERAS menulis pola 3 klausa beruntun ("X, Y, dan Z" atau 3 kalimat berstruktur subjek-predikat identik berturut-turut). Variasikan dengan pola *K-S-P-O*, inversi, dan anak kalimat alami.
* **Pembersihan Kosakata Arkais (Anti-Baku Berlebihan):**
  - ❌ *Galibnya* ➔ ✅ *biasanya*, *pada umumnya*
  - ❌ *Rerata* ➔ ✅ *rata-rata*
  - ❌ *Sekonyong-konyong* ➔ ✅ *tiba-tiba*, *secara mendadak*
  - ❌ *Saban* ➔ ✅ *setiap*, *tiap kali*
  - ❌ *Kediaman* (jika berlebihan) ➔ ✅ *rumah*, *tempat tinggal*
  - ❌ *Asa* ➔ ✅ *harapan*
  - ❌ *Memboyong* ➔ ✅ *membawa*, *mengerahkan*
* **Larangan Alat Pseudo-Humanizer:** DILARANG KERAS memproses naskah menggunakan alat pemutar kata pihak ketiga (seperti Undetectable AI, HIX Bypass, atau spinner sinonim) karena memicu *Meaning Drift* (pergeseran makna teknis sanitasi) yang merusak kredibilitas profesional.

### 1.4 Pantangan Keras "AI Tell" & Dinding Teks:
* Hindari kata klise pembuka AI generik: *"Dalam era modern saat ini..."*, *"Pernahkah Anda membayangkan..."*, *"Menjaga kebersihan WC adalah hal yang sangat krusial..."*, *"Kesimpulannya..."*.
* Hindari paragraf "dinding teks" (*text wall*): Maksimal **2–3 baris kalimat per paragraf** agar nyaman dibaca di layar HP.

### 1.5 Penjelasan Istilah Teknis dalam Bahasa Awam (Wajib Disertai Padanan):
* **Septic Tank** ➔ Bak penampungan kotoran WC bawah tanah.
* **Grease Trap** ➔ Bak penangkap lemak cucian piring dapur.
* **STP (Sewage Treatment Plant)** ➔ Bak pengolahan air limbah domestik gedung/pabrik.
* **Mesin Vakum High-Pressure** ➔ Mesin sedot bertenaga hisap tinggi untuk lumpur tinja padat.
* **Spiral Cable / Drain Snake** ➔ Kawat spiral baja lentur pelancar pipa tanpa bongkar keramik lantai.
* **Water Jetting** ➔ Tembakan air bertekanan tinggi untuk mengikis kerak lemak pipa paralon.
* **Resapan / Rembesan** ➔ Ruang resapan air tanah di samping septic tank.

---

## 🏗️ 2. Anatomi Struktur Artikel & Tata Letak Template Single Post

Setiap artikel blog/edukasi wajib mengikuti urutan struktur dan hierarki tata letak berikut:

```
┌────────────────────────────────────────────────────────────────────────┐
│ [HEADER: Dark Slate #1E1E26, Logo & Menu Teks Putih #FFF (WCAG AAA)]   │
├────────────────────────────────────────────────────────────────────────┤
│ 1. JUDUL ARTIKEL (H1 - Exact Match Fokus Keyword dari Silo/04 Roadmap) │
├────────────────────────────────────────────────────────────────────────┤
│ 2. HOOK EMPATIK & PAS LEAD (80–120 Kata): Masalah Darurat Pembaca     │
├────────────────────────────────────────────────────────────────────────┤
│ 3. BOX DARURAT / MICRO-HOOK CTA (Above The Fold): Respon WA < 5 Menit  │
├────────────────────────────────────────────────────────────────────────┤
│ 4. INTI EDUKASI (H2 & H3): Solusi Praktis, Penyebab Riil & Tips        │
│    - Gunakan Bullet Points & Numbering agar mudah di-skim              │
│    - Sertakan 1 Tabel Komparasi (Misal: Biaya Sedot vs Bongkar Pipa)   │
│    - Sematkan 1 Modul Interaktif Gamifikasi (Kuis / Kalkulator Selang) │
│      merujuk ke Silo/03_GAMIFIKASI_DWELL_TIME_v2.md                    │
│    - Sisipkan 1 Passage Chunk Rujukan AI (SOP/03_AI_SEARCH_v2)         │
├────────────────────────────────────────────────────────────────────────┤
│ 5. FAQ INTERAKTIF (3–5 Pertanyaan Paling Sering Diajukan di SERP)     │
│    - Mengikat Brand + Nomor WhatsApp pada jawaban rekomendasi          │
├────────────────────────────────────────────────────────────────────────┤
│ 6. PENUTUP & FOOTER CTA CARD: Tawaran Cek Lokasi & Konsultasi Gratis   │
├────────────────────────────────────────────────────────────────────────┤
│ 7. REKOMENDASI ARTIKEL TERKAIT (3-Column Grid + Featured Image 16:9):  │
│    [WAJIB BERADA TEPAT DI ATAS COMMENTS AREA - BUKAN DI BAWAHNYA]      │
│    Menampilkan Featured Image, Silo Category, Judul & Tanggal Terbit.  │
├────────────────────────────────────────────────────────────────────────┤
│ 8. KOLOM KOMENTAR (Comments Area & Leave Reply Form)                   │
├────────────────────────────────────────────────────────────────────────┤
│ [FOOTER: Dark Slate #1E1E26, Identik dengan Header, Teks WCAG AAA]    │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 📱 3. Penempatan Tombol WhatsApp & Dual Conversion Path

1. **Jalur Konversi 1 (Direct Emergency CTA):**  
   Untuk pembaca yang butuh tukang segera datang:
   - Tombol CTA WhatsApp ramah di paruh atas (*above the fold*): *"Konsultasi Masalah WC / Cek Biaya via WhatsApp (Respon < 5 Menit)"*.
2. **Jalur Konversi 2 (Informative Internal Link Organik):**  
   Untuk pembaca yang ingin meneliti armada dan tarif wilayah:
   - Internal link diarahkan ke Landing Page Wilayah Organik terkait (misal: *"Lihat rincian armada dan pangkalan di [Sedot WC Jakarta Selatan](file:///D:/Dhany/Client/sedotwcdijakarta/)*") atau ke Artikel Pilar Silo-nya.
   - **INGAT:** Dilarang mengarahkan link ke Halaman 749 Google Ads.
3. **Peringatan Keras Tombol Melayang (*Floating Button*):**  
   - Tombol melayang (*Floating WhatsApp CTA*) telah diinjeksi secara otomatis ke seluruh halaman website oleh MU-Plugin (`wp-content/mu-plugins/ab-testing-wa-master.php`).  
   - **PENULIS DILARANG MEMBUAT TOMBOL FLOATING MANUAL DI ARTIKEL** agar tidak bertumpukan di layar handphone pengguna. Penulis hanya menyisipkan tombol statis di dalam teks (*in-content button*).

### 3.1 Standarisasi Desain, Ikon WA & Alignment Tombol Statis In-Content (`.wa-btn-static`)
Setiap tombol statis WhatsApp di dalam artikel (baik Hook Darurat paruh atas, penutup artikel, maupun tombol hasil diagnosa kuis) **WAJIB MENGIKUTI STANDAR BAKU BERIKUT**:
1. **Identitas Kelas Mutlak (`.wa-btn-static`):**  
   Seluruh tag anchor tombol statis wajib menyertakan kelas `wa-btn-static` agar terintegrasi dengan sakelar A/B testing dan CSS master global di MU-Plugin.
2. **Ikon Resmi WhatsApp (SVG / CSS Mask):**  
   - **DILARANG MENGGUNAKAN EMOJI TEKS** (seperti `💬`, `📱`, `📞`, `🟢`) karena memiliki ukuran, *baseline*, dan *line-height* yang tidak konsisten di berbagai sistem operasi (Android, iOS, Windows, macOS).
   - Wajib menggunakan ikon resmi WhatsApp (SVG putih dengan `width="20" height="20"` dan `margin-right: 8px`) yang diposisikan di sebelah kiri teks tombol, atau memanfaatkan otomatisasi pseudo-element mask CSS (`.wa-btn-static::before`) yang diinjeksi oleh MU-Plugin.
3. **Simetri Teks & Centering Sempurna (*Flex Centering*):**  
   - Tombol wajib menggunakan deklarasi `display: inline-flex; align-items: center; justify-content: center; text-align: center;`.
   - Teks di dalam tombol dilarang melenceng ke kiri atau ke kanan; teks wajib simetris tepat di tengah tombol baik secara horizontal maupun vertikal.
4. **Sudut Melengkung Konsisten (*Border Radius*):**  
   - Seluruh tombol statis wajib memiliki `border-radius: 8px` yang rapi dan konsisten (bukan persegi runcing dan bukan oval pill berlebihan).
5. **Container Pembungkus Terpusat:**  
   - Tombol statis wajib dibungkus dalam container ber-margin tengah:  
     `<div style="display: flex; justify-content: center; width: 100%; margin-top: 15px;">...</div>`  
     sehingga posisi tombol selalu terpusat sempurna di layar desktop maupun smartphone 320px.
6. **Anti-Nomor Telepon pada Teks Tombol (*Mobile Readability & Conversion Clarity*):**  
   - **DILARANG MENYERTAKAN NOMOR TELEPON PANJANG** (seperti `0813-8888-4349`) di dalam teks tombol CTA.  
   - Pengunjung sudah mengetahui bahwa tombol tersebut mengarah ke WhatsApp melalui warna hijau khas (`#16a34a` / `#22c55e`) dan ikon resmi WhatsApp.  
   - Teks tombol wajib ringkas (**maksimal 30–40 karakter**), berfokus murni pada ajakan bertindak (*action-oriented*) dan proposisi nilai (*value benefit*), seperti *"Konsultasi & Cek Lokasi Gratis"* atau *"Hubungi Teknisi (Respon WA < 5 Menit)"*.  
   - Menaruh nomor telepon di teks tombol memicu pembengkakan vertikal tombol (*line-wrapping* 3–4 baris dengan tinggi > 80px) pada layar smartphone sempit (320px–375px), merusak estetika dan menurunkan CTR.
7. **Contoh Markup Standar Resmi:**
   ```html
   <!-- Hook Darurat (Paragraf Atas / Emergency Box) -->
   <div style="display: flex; justify-content: center; width: 100%; margin-top: 15px;">
     <a href="https://wa.me/6281388884349?text=Halo%20Admin%20Sedot%20WC%20Jakarta,%20saya%20butuh%20layanan%20kuras%20septic%20tank%20hari%20ini." class="wa-btn-static" style="background: #16a34a; color: #ffffff; padding: 12px 28px; border-radius: 8px; font-weight: 700; text-decoration: none; display: inline-flex; align-items: center; justify-content: center; font-size: 1rem; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); text-align: center;">
       <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" width="20" height="20" fill="#ffffff" style="margin-right: 8px; flex-shrink: 0;"><path d="M380.9 97.1C339 55.1 283.2 32 223.9 32c-122.4 0-222 99.6-222 222 0 39.1 10.2 77.3 29.6 111L0 480l117.7-30.9c32.4 17.7 68.9 27 106.1 27h.1c122.3 0 224.1-99.6 224.1-222 0-59.3-25.2-115-67.1-157zm-157 341.6c-33.2 0-65.7-8.9-94-25.7l-6.7-4-69.8 18.3L72 359.2l-4.4-7c-18.5-29.4-28.2-63.3-28.2-98.2 0-101.7 82.8-184.5 184.6-184.5 49.3 0 95.6 19.2 130.4 54.1 34.8 34.9 56.2 81.2 56.1 130.5 0 101.8-84.9 184.6-186.6 184.6zm101.2-138.2c-5.5-2.8-32.8-16.2-37.9-18-5.1-1.9-8.8-2.8-12.5 2.8-3.7 5.6-14.3 18-17.6 21.8-3.2 3.7-6.5 4.2-12 1.4-32.6-16.3-54-29.1-75.5-66-5.7-9.8 5.7-9.1 16.3-30.3 1.8-3.7.9-6.9-.5-9.7-1.4-2.8-12.5-30.1-17.1-41.2-4.5-10.8-9.1-9.3-12.5-9.5-3.2-.2-6.9-.2-10.6-.2-3.7 0-9.7 1.4-14.8 6.9-5.1 5.6-19.4 19-19.4 46.3 0 27.3 19.9 53.7 22.6 57.4 2.8 3.7 39.1 59.7 94.8 83.8 35.2 15.2 49 16.5 66.6 13.9 10.7-1.6 32.8-13.4 37.4-26.4 4.6-13 4.6-24.1 3.2-26.4-1.3-2.5-5-3.9-10.5-6.6z"/></svg>
       Hubungi Teknisi (Respon WA &lt; 5 Menit)
     </a>
   </div>

   <!-- Footer Closing CTA (Paragraf Bawah / Card CTA) -->
   <div style="display: flex; justify-content: center; width: 100%; margin-top: 15px;">
     <a href="https://wa.me/6281388884349?text=Halo%20Sedot%20WC%20Jakarta,%20saya%20ingin%20konsultasi%20jadwal%20kuras%20septic%20tank." class="wa-btn-static" style="background: #22c55e; color: #ffffff; padding: 12px 30px; border-radius: 8px; font-weight: 700; text-decoration: none; display: inline-flex; align-items: center; justify-content: center; font-size: 1rem; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); text-align: center;">
       <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" width="20" height="20" fill="#ffffff" style="margin-right: 8px; flex-shrink: 0;"><path d="M380.9 97.1C339 55.1 283.2 32 223.9 32c-122.4 0-222 99.6-222 222 0 39.1 10.2 77.3 29.6 111L0 480l117.7-30.9c32.4 17.7 68.9 27 106.1 27h.1c122.3 0 224.1-99.6 224.1-222 0-59.3-25.2-115-67.1-157zm-157 341.6c-33.2 0-65.7-8.9-94-25.7l-6.7-4-69.8 18.3L72 359.2l-4.4-7c-18.5-29.4-28.2-63.3-28.2-98.2 0-101.7 82.8-184.5 184.6-184.5 49.3 0 95.6 19.2 130.4 54.1 34.8 34.9 56.2 81.2 56.1 130.5 0 101.8-84.9 184.6-186.6 184.6zm101.2-138.2c-5.5-2.8-32.8-16.2-37.9-18-5.1-1.9-8.8-2.8-12.5 2.8-3.7 5.6-14.3 18-17.6 21.8-3.2 3.7-6.5 4.2-12 1.4-32.6-16.3-54-29.1-75.5-66-5.7-9.8 5.7-9.1 16.3-30.3 1.8-3.7.9-6.9-.5-9.7-1.4-2.8-12.5-30.1-17.1-41.2-4.5-10.8-9.1-9.3-12.5-9.5-3.2-.2-6.9-.2-10.6-.2-3.7 0-9.7 1.4-14.8 6.9-5.1 5.6-19.4 19-19.4 46.3 0 27.3 19.9 53.7 22.6 57.4 2.8 3.7 39.1 59.7 94.8 83.8 35.2 15.2 49 16.5 66.6 13.9 10.7-1.6 32.8-13.4 37.4-26.4 4.6-13 4.6-24.1 3.2-26.4-1.3-2.5-5-3.9-10.5-6.6z"/></svg>
       Konsultasi &amp; Cek Lokasi Gratis
     </a>
   </div>
   ```

---

## 🖼️ 4. Standar Spesifikasi Aset Visual & Gambar WebP HD

Seluruh pengadaan media wajib mematuhi panduan master di [`SOP/06_IMAGE_&_MEDIA_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/06_IMAGE_&_MEDIA_SOP_v2.md):
1. **Featured Image (Gambar Utama):**
   - **Rasio & Resolusi:** 16:9 (1200 × 675 px).
   - **Format & Ukuran:** 100% WebP terkompresi (< 100 KB).
   - **Aturan Nama Berkas:** Format slug fokus keyword (contoh: `kuras-septic-tank-rumah-tangga-jakarta.webp`).
   - **Atribut `alt`:** Memuat fokus keyword utama secara natural.
2. **In-Content Image (Gambar Penjelas di Tubuh Artikel):**
   - **Rasio & Resolusi:** 16:9 (1200 × 675 px) atau 4:3 (800 × 600 px).
   - **Format & Ukuran:** 100% WebP terkompresi (< 80 KB).
   - **Integritas Rasio Aspek (Zero Distortion):** Atribut HTML `width` dan `height` pada tag `<img>` wajib mencerminkan dimensi asli berkas (misal `width="1200" height="675"`), bukan dipaksa tinggi/lebar yang menggepengkan gambar.
3. **Two-Way Media Protocol:** Wajib ada Featured Media dan minimal 1 gambar konten independen ($N$ pos = $2N$ media unik). Dilarang mendaur ulang gambar yang sama (anti-cross-duplicate).
4. **Anti-Rename Bypass & Larangan Comot Cache:** Dilarang me-rename file lama untuk artikel baru dan dilarang comot file cache lokal tanpa izin.

---

## 🔍 5. Standar E-E-A-T, Realisme Lapangan & Validasi Rujukan Eksternal

* **Experience:** Ceritakan kondisi lapangan nyata di pemukiman Jabodetabek (kendala rumah di dalam gang sempit yang membutuhkan selang hisap panjang 50–100 meter, posisi septic tank lama tanpa tutup kontrol, septic tank terendam banjir).
* **Expertise:** Jelaskan SOP pengerjaan yang higienis, penyedotan lumpur padat tanpa merusak resapan, mesin vakum bertenaga hisap tinggi, dan pembersihan kerak lemak pipa resto.
* **Authoritativeness (Evidence-Grade Citations):** Cantumkan referensi otoritas resmi sanitasi dan lingkungan hidup:
  - **SNI 2398:2017:** Tata Cara Perencanaan Tangki Septik dengan Pengolahan Lanjutan (Sistem Resapan).
  - **Permen LHK No. P.68/Menlhk/Setjen/Kum.1/8/2016:** Baku Mutu Air Limbah Domestik.
  - **Perda DKI Jakarta No. 3 Tahun 2013:** Pengelolaan Sampah & Pengolahan Air Limbah Terpusat.
  - **IPLT Resmi Pemda DKI Jakarta:** Pembuangan resmi limbah lumpur tinja ke Instalasi Pengolahan Lumpur Tinja (IPLT) Duri Kosambi (Jakarta Barat) dan IPLT Pulo Gebang (Jakarta Timur).
  - *Protokol Validasi Tautan:* Seluruh tautan eksternal wajib berupa tautan aktif live HTTP 200 ke dokumen/lembar fakta resmi (DILARANG link broken, soft-404, atau sekadar link ke homepage utama).
* **Trustworthiness:** Garansi pengerjaan ulang (*re-service*) tanpa biaya tambahan jika saluran air masih mampet, serta keterbukaan estimasi biaya di awal (*zero hidden fee*).

---

## ⚙️ 6. Parameter Penerbitan WordPress, SEOPress & Pencegahan Kebocoran Kode

Sebelum artikel diterbitkan atau dijadwalkan, parameter berikut wajib diset:
* **Kategori (Category):** Centang tepat **1 Kategori Silo** resmi (Pilihan: `septic-tank-pemukiman`, `saluran-pipa-mampet`, `grease-trap-resto-mbg`, `limbah-stp-industri`, `area-layanan-jabodetabek`). Dilarang mencentang kategori default `Info Update`.
* **Tag:** Dikosongkan total (**0 Tag Policy**).
* **SEOPress Title (`_seopress_titles_title`):** Format: `[Judul H1 Menarik] - Sedot WC Jakarta`. Wajib memuat fokus keyword secara utuh (*Exact Match*).
* **SEOPress Meta Description (`_seopress_titles_desc`):** Wajib diisi 140–160 karakter, memuat fokus keyword dan ajakan tindakan darurat (*"Respon < 5 Menit / Siaga 24 Jam Jabodetabek"*). Dilarang dibiarkan kosong.
* **SEOPress Target Keyword (`_seopress_analysis_target_kw`):** Diisi fokus keyword resmi dari `Silo/04`.
* **Protokol Pencegahan Kebocoran Kode Front-End (Zero Code Leaks):**
  - DILARANG KERAS menaruh tag `<script type="application/ld+json">` mentah di dalam editor teks postingan karena sanitasi `wp_kses` WordPress akan mencabut tag pembungkus dan menyebabkan barisan kode JSON mentah bocor ke layar pembaca.
  - Schema JSON-LD diproses melalui integrasi tema/plugin SEOPress atau blok Custom HTML terisolasi.
  - Dilarang ada kode CSS mentah (`style="..."`), komentar HTML internal (`<!-- [GAMBAR...] -->`), atau shortcode rusak yang tampak di layar pengunjung.

---

## 🔗 7. Blok Naskah Rekomendasi Inbound Link (Langkah 1 Anti-Orphan Post)

Di akhir draf setiap artikel baru, penulis wajib menyertakan blok instruksi pembaruan tautan masuk:

```markdown
### [REKOMENDASI INBOUND LINK - ANTI-ORPHAN]
- **Target Artikel Eksisting 1:** [Judul & URL Artikel Seklaster Lama]
  - **Paragraf Penempatan:** Di bawah sub-heading [Nama Sub-heading]
  - **Kalimat yang Disisipkan:** "Untuk panduan penanganan darurat selengkapnya, simak [Anchor Text Relevan](URL_Artikel_Baru_Ini)."
- **Target Artikel Eksisting 2:** [Judul & URL Artikel Seklaster Lama 2]
  - **Kalimat yang Disisipkan:** "...seperti yang dijelaskan dalam [Anchor Text Relevan](URL_Artikel_Baru_Ini)."
```
*(Publisher akan mengeksekusi penyisipan link ini ke artikel lama sebelum diaudit oleh Auditor).*
