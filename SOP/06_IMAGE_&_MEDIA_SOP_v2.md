# SOP Master Manajemen Media, Visual & Gambar Sanitasi (Versi 2.0)

> **Status Dokumen:** Master SOP Manajemen Media, Visual & Aset Gambar (V2.0 - Active).  
> **Website Target:** https://sedotwcdijakarta.com/  
> **Target Pengguna:** Graphic Designer, AI Image Prompt Engineer, Content Writer, Publisher, Quality Auditor.  
> **Posisi dalam Siklus:** Pendukung Tahap 2 & 3 — Pengadaan Media dan Verifikasi Visual Sebelum Rilis.  
> 
> ### 🔄 Peta Hubungan Resiprokal (Reciprocal Workflow Role):
> * **Hulu / Penentuan Kebutuhan Visual:** Draf artikel dari [`SOP/01_CONTENT_WRITER_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/01_CONTENT_WRITER_SOP_v2.md) dan topik dari [`Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md).
> * **Hilir / Verifikasi Integritas:** Diuji kelayakannya pada Hard Gate 7 di [`SOP/02_CONTENT_AUDIT_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/02_CONTENT_AUDIT_SOP_v2.md).
> * **Tata Kelola Induk:** Tunduk pada proteksi tata letak dan guardrail di [`.agents/AGENTS.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/AGENTS.md).

---

## 🛑 1. Konvensi Penamaan File & Larangan Keras Anti-Bypass

### 1.1 Format Nama File Resmi
Nama berkas gambar wajib menggunakan huruf kecil semua, berbasis slug fokus keyword artikel yang deskriptif, dan dipisahkan tanda hubung (`-`):
```
[topik-slug-artikel]-[konteks-singkat].webp
```

**Contoh Benar:**
* `kuras-septic-tank-jakarta-selang-panjang.webp`
* `penyedotan-grease-trap-restoran-dapur-mbg.webp`
* `alat-spiral-drain-snake-pelancar-pipa.webp`
* `truk-tangki-vakum-engkel-gang-sempit.webp`

**Contoh Salah (DILARANG KERAS):**
* ❌ `sedot-wc-jakarta-1.webp` *(menggunakan suffix angka generic)*
* ❌ `sedot-wc-jakarta-v2.webp` *(menggunakan suffix versi)*
* ❌ `gambar1.webp` atau `DSC_0023.webp` *(nama generik/kamera mentah)*
* ❌ `kuras septic tank (1).webp` *(menggunakan spasi dan tanda kurung)*

### 1.2 Larangan Keras Me-Rename File yang Sudah Ada (Anti-Rename Bypass)
> ⛔ **ATURAN MUTLAK (ZERO TOLERANCE):**  
> DILARANG KERAS mengambil file gambar yang sudah pernah dipakai di artikel lain (baik di folder lokal maupun WordPress Media Library), lalu me-rename namanya agar cocok dengan slug artikel baru untuk diunggah ulang.
> 
> **Mengapa Dilarang Keras?**
> 1. **Visual Tetap Kembar:** Mengubah nama file tidak mengubah piksel visual gambar. Pengunjung tetap melihat foto armada atau pipa yang sama persis di artikel berbeda.
> 2. **Menipu Sistem Audit:** Me-rename file menghasilkan ID media baru di WordPress yang membuat skrip audit teks mengira gambar tersebut unik (`usage count === 1`), padahal secara biner dan visual terjadi duplikasi 100%.
> 3. **Pelanggaran E-E-A-T & Google Helpful Content:** Google Vision AI mengenali fitur visual gambar. Dua artikel berbeda dengan gambar kembar akan ditandai sebagai konten fabrikasi massal (*scaled/reused content abuse*).

### 1.3 Larangan Mengambil Gambar dari Cache Sesi Tanpa Izin
> ⛔ **PROTOKOL PENGADAAN GAMBAR:**  
> Agen dilarang mengambil jalan pintas dengan comot gambar dari *cache* sesi sebelumnya (`.tempmediaStorage`, `brain/`, folder unduhan sementara) tanpa persetujuan eksplisit.
> 1. **Opsi Default Wajib Fresh Generation:** Setiap artikel baru wajib dibuatkan aset gambar baru dari nol menggunakan tool AI (`generate_image`) atau foto dokumentasi riil operasional lapangan.
> 2. **Kelemahan Validasi Hash Lintas Format:** Nilai hash kriptografis SHA-256 **TIDAK DAPAT** mendeteksi duplikasi antara file mentah JPG di cache lokal dengan file WebP yang telah dikompresi di WordPress (*False Negative*). Byte keduanya 100% berbeda padahal visualnya sama persis. Oleh karena itu, pengecekan hash lokal tidak menjamin gambar bebas duplikasi jika bersumber dari cache yang sama.

---

## 📐 2. Protokol Dua Sisi & Eksklusivitas Media (Two-Way Media Protocol)

Setiap artikel blog yang diterbitkan wajib memiliki status **Eksklusif Tunggal (1 Post ID = 1 Pasang Gambar Unik)**:
1. **Kaidah 2N Media Unik:** Untuk $N$ artikel yang ada di database, wajib terdapat $2N$ aset gambar unik (0 duplikasi lintas website).
2. **Mandatori Kelengkapan Dua Sisi:**
   * `featured_media > 0` pada metadata WordPress (Gambar Utama).
   * Minimal 1 In-Content Image independen di tubuh teks.
   * Artikel berstatus **GAGAL AUDIT (FAIL)** jika `featured_media === 0` atau tidak memiliki gambar di dalam teks artikel.
3. **Anti-Self-Duplicate (Internal Artikel):** Gambar Utama (*Featured Image*) wajib berbeda dengan Gambar Konten di dalam artikel yang sama (`featuredMedia !== inContentImage`).
4. **Anti-Cross-Duplicate (Lintas Artikel):** Dilarang mendaur ulang gambar yang sudah terikat pada artikel lain yang sudah terbit maupun yang berstatus terjadwal (*Scheduled/Future*).

---

## 🎨 3. Spesifikasi Teknis, Rasio & Standar Anti-Distorsi

### 3.1 Spesifikasi Berkas & Kompresi
* **Format Berkas Wajib:** 100% `.webp`. DILARANG KERAS `.jpg`, `.jpeg`, atau `.png`.
* **Kualitas Kompresi:** Kualitas WebP 80–85%.
* **Batas Ukuran Berkas:**
  * Featured Image: **< 100 KB** (Rekomendasi 50–90 KB).
  * In-Content Image: **< 80 KB** (Rekomendasi 40–75 KB).
* **Dimensi & Resolusi Minimal:**
  * Featured Image (16:9): **1200 × 675 px** (Standar Google Discover & Large Image Snippet).
  * In-Content Image (16:9 atau 4:3): **1200 × 675 px** atau **800 × 600 px** (Lebar minimal 800 px).

### 3.2 Integritas Rasio Aspek (Zero Distortion)
> ⚠️ **Pencegahan Gambar Gepeng / Terdistorsi:**  
> Atribut HTML `width` dan `height` pada tag `<img>` **WAJIB** mencerminkan rasio dan dimensi asli biner file.
* **Contoh Benar:**  
  Jika file berdimensi 1200 × 675 px:
  ```html
  <img src="https://sedotwcdijakarta.com/wp-content/uploads/2026/09/kuras-septic-tank-jakarta-selang-panjang.webp" alt="Teknisi Sedot WC Jakarta membentangkan selang hisap 100 meter di gang sempit pemukiman" width="1200" height="675" style="width: 100%; max-width: 800px; height: auto; aspect-ratio: 16/9;" />
  ```
* **Contoh Salah (DILARANG):**  
  File 1200 × 675 px tetapi atribut dipaksa `height="400"` atau `height="533"`, sehingga tampilan truk tangki atau pipa menjadi gepeng/tertekan.

### 3.3 Larangan Mencopot Gambar Tanpa Pengganti (Atomic Image Replacement)
DILARANG menghapus tag gambar lama/rusak tanpa langsung menyuntikkan file gambar pengganti sah (*Fresh WebP*) dalam satu transaksi penyimpanan yang sama. Artikel tidak boleh dibiarkan tanpa gambar di tubuh teks.

---

## 🦺 4. Realisme Lapangan Sanitasi, Etika Visual & APD Teknisi

Gambar yang dihasilkan untuk website sanitasi wajib mematuhi standar realisme operasional industri:
1. **Karakter & Etnisitas Lokal:** Sosok teknisi dan masyarakat wajib mencerminkan orang Indonesia/Asia dengan busana sopan dan wajar. Dilarang sosok Kaukasia/bule atau latar pemukiman luar negeri.
2. **Kelengkapan Alat Pelindung Diri (APD) Teknisi:**
   * Teknisi wajib digambarkan mengenakan seragam kerja rapi/wearpack, sarung tangan karet pelindung (*safety gloves*), dan sepatu bot karet (*safety rubber boots*).
   * Citra visual harus profesional, higienis, dan teratur (bukan kesan kumuh atau kotor jorok berlebihan).
3. **Peralatan Kerja yang Akurat:**
   * **Armada Truk Tangki:** Truk engkel tangki berkapasitas 3.000–4.000 liter dengan plat kendaraan Indonesia (plat kuning wilayah Jabodetabek B/F).
   * **Selang Hisap Industri:** Selang spiral fleksibel bertenaga vakum warna oranye/kuning/biru standar industri sanitasi dengan sambungan coupling rapi.
   * **Mesin Pelancar Pipa:** Menggambarkan mesin *spiral drain cleaner* / *roding machine* atau *jetting pump* bertekanan tinggi modern tanpa merusak ubin lantai.
4. **Kepatuhan Anatomi AI:** DILARANG KERAS gambar AI dengan jari berlebih, tangan ganda, sendi terdistorsi, atau bentuk tangki truk yang tidak masuk akal secara fisik. Setiap sosok wajib memiliki 2 tangan dengan 5 jari sempurna.
5. **Integritas & Kontinuitas Selang Hisap (Hose Logic & Closed Circuit Continuity):**  
   Jika gambar menampilkan selang hisap/vakum, alur selang wajib tampak normal dan kedua ujungnya terlihat jelas fungsinya secara logis:
   * **Ujung Hulu (Input):** Terhubung ke katup hisap tangki truk (*vacuum intake valve*) atau tergulung rapi di rak/tatakan samping bodi mobil tangki (*hose tray*).
   * **Ujung Hilir (Output):** Sedang dipegang mantap oleh teknisi bersarung tangan, sedang diulur/ditarik rapi di sepanjang jalan pemukiman, atau dimasukkan langsung ke lubang septic tank (*manhole/inspection hole*), lubang kloset, atau bak grease trap.
   * **Titik Sambungan (Ekstensi 50–100M Gang Sempit):** Jika menggambarkan sambungan antar-selang panjang, titik sambung wajib menggunakan klem kopling cepat (*quick coupling / camlock fitting*) yang menyentuh permukaan tanah secara wajar.

---

## 🎯 5. Panduan Gaya Visual & Keselarasan Core Business Sanitasi (5 Silo Directives)

Setiap aset visual (Featured & In-Content) **WAJIB MENYATU** dengan inti bisnis sanitasi *sedotwcdijakarta.com*. Visual dibagi menjadi 2 pilar gaya utama:

### 5.1 Gaya 1: Realisme Lapangan & Dokumenter Operasional (Hero / Featured Images)
* **Pencahayaan:** Natural daylight pemukiman perkotaan Indonesia, pencahayaan alami tanpa filter fantasi berlebihan.
* **Konteks Lingkungan:** Pemukiman warga Jakarta (gang perumahan padat, paving block/aspal lingkungan, ruko komersial, atau basement gedung perkantoran).
* **Objek Utama:** Truk tangki vakum bersih, selang hisap spiral industri, perlengkapan APD teknisi Indonesia yang profesional.

### 5.2 Gaya 2: Diagram Teknik 3D & Skema Penampang Melintang (In-Content Images)
* **Karakter Visual:** 3D technical cutaway diagram / isometric cross-section beresolusi tinggi dengan anotasi komponen yang informatif dan akurat secara teknik teknik lingkungan.
* **Keselarasan 5 Silo:**
  1. **Silo 1 (Septic Tank):** Diagram penampang melintang bak beton bertulang SNI 2398:2017, sekat pemisah (*baffle wall*), lapisan lumpur dasar (*sludge*), buih lemak (*scum*), cairan limbah jernih (*effluent*), bidang resapan kerikil/ijuk, serta pipa hawa T-vent.
  2. **Silo 2 (Saluran Pipa Mampet):** Diagram penampang pipa paralon PVC dengan kawat spiral baja fleksibel (*drain cleaner rooter*) menembus sumbatan lemak atau benda asing di tikungan L-bow tanpa merusak dinding pipa.
  3. **Silo 3 (Grease Trap Resto & MBG):** Skema kompartemen 3 sekat stainless steel pemisah minyak dan lemak (FOG) di bawah bak cuci piring komersial, memperlihatkan keranjang saringan sisa makanan, ruang perangkap minyak terapung, dan pipa pembuangan air jernih.
  4. **Silo 4 (Limbah STP Industri):** Skema fasilitas Sewage Treatment Plant (STP) gedung bertingkat/pabrik, memperlihatkan bak aerasi biologis, blower oksigen, proses sedimentasi lumpur aktif sekunder, dan bak desinfeksi sebelum dibuang ke saluran kota berizin IPLT.
  5. **Silo 5 (Hyperlocal Jabodetabek):** Infografis peta pangkalan armada pos reaksi cepat 5 wilayah DKI Jakarta (< 5 menit respon WhatsApp, 30–45 menit tiba di lokasi) dengan rute jalan dan ilustrasi jangkauan selang 100 meter.

---

## 🚫 6. Daftar Hitam Visual (Strict Visual Blacklist)

Untuk menjaga reputasi otoritas dan konversi, hal-hal berikut **DILARANG KERAS** muncul di artikel blog maupun landing page:
1. ❌ **Peralatan Pertukangan / Konstruksi Lepas Konteks:**  
   Dilarang keras memuat foto bor tangan, bor listrik, palu, gergaji, gerinda, scaffolding bangunan, atau pekerja proyek bertopi proyek kuning di lokasi cor semen gedung. Ini adalah bisnis sanitasi/sedot WC/pelancaran pipa, BUKAN renovasi bangunan sipil.
2. ❌ **Toilet Mewah Gaya Barat:**  
   Dilarang menggunakan foto kamar mandi mewah gaya Eropa/Amerika (bathtub marmer, jendela kaca besar dengan salju di luar) yang tidak relevan dengan tipikal hunian di Indonesia.
3. ❌ **Foto Stok Generik Asing (Bule/Western):**  
   Dilarang menampilkan teknisi atau model warga asing Kaukasia yang jelas-jelas diambil dari database foto stok luar negeri gratisan.
4. ❌ **Gambar Kartun / Clipart Rendahan:**  
   Dilarang menggunakan ilustrasi clipart 2D atau gambar kartun tidak profesional yang menurunkan nilai kepercayaan (*trust factor*) pelanggan komersial/B2B.
5. ❌ **Halusinasi Selang AI (AI Hose Glitches):**  
   Dilarang keras memuat gambar dengan selang melayang di udara tanpa gravitasi (*floating hoses*), selang yang ujungnya buntung/terpotong di tengah aspal tanpa tujuan, selang yang melebur aneh (*merging*) ke dalam ban/roda truk atau dinding rumah, serta lilitan ruwet tidak masuk akal (*spaghetti loop*) yang mustahil digunakan teknisi di lapangan.

---

## ⚡ 7. Protokol Cache-Busting & Invalidation CDN / Browser

### 7.1 Masalah Caching CDN & Browser
Server Hostinger (`hcdn`) dan browser modern menerapkan header `Cache-Control: public, max-age=31557600` (1 tahun) pada file gambar WebP. Jika suatu file gambar lama diperbarui di server dengan nama file yang persis sama:
* Browser pengunjung yang pernah membuka halaman tersebut **TIDAK AKAN** mendownload gambar baru dan tetap menampilkan gambar lama dari memori cache lokalnya.

### 7.2 Prosedur Wajib Penggantian Gambar (Atomic Cache-Busting):
Saat melakukan revisi atau perbaikan gambar yang sudah pernah terbit:
1. **Gunakan Nama Berkas Baru / Berversi (*Versioned Filename*):**  
   Ganti nama file gambar baru, misalnya dari `skema-anatomi-septic-tank-sni.webp` menjadi `diagram-struktur-septic-tank-sni.webp` (atau tambahkan suffix spesifik).
2. **Tambahkan Query String Cache-Busting di HTML:**  
   Pada tag `<img>` di dalam konten, sertakan parameter versi, contoh: `src=".../diagram-struktur-septic-tank-sni.webp?v=2"`.
3. **Purge Cache Server Menyeluruh:**  
   Segera jalankan pembersihan cache LiteSpeed (`LiteSpeed\Purge::purge_all()`) agar server menyajikan HTML segar kepada seluruh CDN edge dan browser klien.

