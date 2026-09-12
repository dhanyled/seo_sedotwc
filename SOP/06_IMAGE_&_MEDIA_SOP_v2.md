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
