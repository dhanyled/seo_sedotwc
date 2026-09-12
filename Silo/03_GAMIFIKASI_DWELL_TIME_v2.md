# Strategi Gamifikasi Interaktif & Peningkatan Dwell Time (Versi 2.0)

> **Status Dokumen:** Framework Widget Interaktif & Optimasi Sinyal Perilaku UX (V2.0 - Active).  
> **Website Target:** https://sedotwcdijakarta.com/  
> 
> ### 🔄 Peta Hubungan Resiprokal (Reciprocal Workflow Role):
> * **Penempatan oleh Penulis:** Penulis wajib menyisipkan minimal 1 modul widget ini di bagian tengah artikel (paragraf 40–50%) sesuai anatomi artikel di [`SOP/01_CONTENT_WRITER_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/01_CONTENT_WRITER_SOP_v2.md).
> * **Korelasi Data Logistik Hyperlocal:** Logika kalkulator selang mengacu pada batas jangkauan truk engkel dan selang 100M di [`Silo/02_LOCAL_GEO_HYPERLOCAL_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/02_LOCAL_GEO_HYPERLOCAL_v2.md).
> * **Pasangan Artikel di Roadmap:** Widget kuis diprioritaskan pada artikel Silo 1 & Silo 2, sedangkan kalkulator selang pada Silo 1 & Silo 5 di [`Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md).
> * **Verifikasi Auditor (QC Gate):** Wajib lolos pemeriksaan retensi pengguna & modul interaktif pada [`SOP/02_CONTENT_AUDIT_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/02_CONTENT_AUDIT_SOP_v2.md) (Hard Gate 9).
> * **Monitoring Event GA4:** Data interaksi dan konversi kuis/kalkulator dilacak melalui skema event pada [`SOP/05_TRACKING_&_ANALYTICS_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/05_TRACKING_&_ANALYTICS_SOP_v2.md).
> * **Tata Kelola Induk:** Tunduk pada guardrail utama di [`.agents/AGENTS.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/AGENTS.md).

---

## ⚡ 1. Korelasi Gamifikasi dengan Sinyal NavBoost & User Engagement

Algoritma mesin pencari Google modern (**NavBoost & Helpful Content System**) sangat memperhatikan perilaku pengguna pasca-klik (*post-click behavioral signals*):

* **Website Biasa (Teks Statis Membosankan):**  
  Pengunjung yang panik membaca sekilas, tidak menemukan jawaban pasti dalam 30 detik, lalu menekan tombol *Back* kembali ke Google (*Pogo-Sticking*). Hal ini mengirim sinyal negatif ke Google bahwa konten tidak memuaskan.
* **Website Interaktif (`sedotwcdijakarta.com`):**  
  Pengunjung menemukan modul diagnosa instan atau kalkulator kebutuhan selang. Mereka berinteraksi aktif mengklik opsi (menaikkan *Dwell Time* menjadi **2–3+ menit**). Google membaca sinyal bahwa pengguna sangat terbantu sehingga peringkat SEO terdongkrak naik ke Top 3.

---

---

## 🛠️ 2. Dua Widget Interaktif Penahan Durasi Kunjungan

---

### 🩺 Widget 1: Kuis Cek Diagnosa Mandiri: "Kloset Mampet atau Septic Tank Penuh?"
* **Estimasi Penambahan Dwell Time:** +2 Menit.
* **Latar Belakang Masalah:** 80% calon pelanggan tidak tahu apakah kloset mereka hanya tersumbat kotoran/benda asing ringan atau bak penampungan septic tank di bawah tanah yang sudah penuh air/lumpur.

```
┌────────────────────────────────────────────────────────────────────────┐
│               KUIS DIAGNOSA CEPAT MASALAH WC (30 DETIK)                │
├────────────────────────────────────────────────────────────────────────┤
│ Pertanyaan 1: Bagaimana reaksi air saat kloset disiram?                │
│ [ ] A. Air tidak turun sama sekali dan langsung meluap ke atas bibir   │
│ [ ] B. Air turun sangat lambat (butuh waktu 10-15 menit baru surut)    │
│                                                                        │
│ Pertanyaan 2: Kapan terakhir kali septic tank rumah Anda disedot?      │
│ [ ] A. Baru 1 - 6 bulan yang lalu                                      │
│ [ ] B. Lebih dari 2 tahun yang lalu / Belum pernah sejak ditempati     │
│                                                                        │
│ Pertanyaan 3: Apakah ada bau busuk gas menyengat di sekitar saluran?   │
│ [ ] A. Tidak ada bau, murni air saja yang mampet                       │
│ [ ] B. Tercium bau menyengat dari lubang kloset & got sekitarnya       │
├────────────────────────────────────────────────────────────────────────┤
│ HASIL DIAGNOSA OTOMATIS:                                               │
│ Jika Mayoritas B ➔ "Indikasi Kuat: Bak Septic Tank Anda Penuh Lumpur"  │
│ [ Tombol WA: Hubungi Tukang Kuras Tangki Terdekat (Respon < 5 Mnt) ]   │
│                                                                        │
│ Jika Mayoritas A ➔ "Indikasi: Pipa Saluran Tersumbat Benda Asing"      │
│ [ Tombol WA: Pesan Layanan Pelancar Pipa Tanpa Bongkar ]               │
└────────────────────────────────────────────────────────────────────────┘
```

#### 📦 Implementasi Resmi via Shortcode (MU-Plugin Architecture):
> ⚠️ **ATURAN MUTLAK ARSITEKTUR WORDPRESS:**  
> DILARANG MENYUNTIKKAN FORM HTML DAN INLINE JAVASCRIPT LANGSUNG KE POST CONTENT ATAU GUTENBERG!  
> **Mengapa?** Filter keamanan WordPress (`wp_filter_post_kses`) otomatis melucuti tag `<form>`, `<select>`, dan `<input>`, sedangkan fungsi `wpautop` menyisipkan tag `<p>` ke baris kode JavaScript yang memicu `SyntaxError` di konsol browser (sehingga tombol menjadi macet tanpa respon saat diklik).
> 
> **Solusi Standar:** Cukup pasang Shortcode resmi di badan artikel:
> ```
> [kuis_diagnosa_septic]
> ```
> Seluruh logika form dan kalkulasi dieksekusi secara aman melalui MU-Plugin `wp-content/mu-plugins/sanitasi-gamifikasi.php` dengan script yang di-enqueue pada `wp_footer` beratribut `data-no-optimize="1"` (kebal kompresi agresif LiteSpeed Cache).

Untuk pengujian lokal atau pratinjau standalone, struktur logika kuis adalah sebagai berikut:
  <form id="swcDiagnosaForm" onchange="runDiagnosa()" style="display:flex;flex-direction:column;gap:14px;">
    <div>
      <label style="font-weight:600;font-size:0.9rem;display:block;margin-bottom:6px;">1. Bagaimana reaksi air saat kloset disiram?</label>
      <label style="display:block;margin-bottom:4px;font-size:0.85rem;"><input type="radio" name="q1" value="A"> Air tidak turun sama sekali / meluap seketika</label>
      <label style="display:block;font-size:0.85rem;"><input type="radio" name="q1" value="B"> Air turun sangat lambat (butuh waktu 10–15 menit)</label>
    </div>
    <div>
      <label style="font-weight:600;font-size:0.9rem;display:block;margin-bottom:6px;">2. Kapan terakhir septic tank rumah Anda disedot?</label>
      <label style="display:block;margin-bottom:4px;font-size:0.85rem;"><input type="radio" name="q2" value="A"> Baru 1–6 bulan yang lalu</label>
      <label style="display:block;font-size:0.85rem;"><input type="radio" name="q2" value="B"> Lebih dari 2 tahun / Belum pernah sejak dihuni</label>
    </div>
    <div>
      <label style="font-weight:600;font-size:0.9rem;display:block;margin-bottom:6px;">3. Apakah muncul bau busuk gas menyengat di sekitar saluran?</label>
      <label style="display:block;margin-bottom:4px;font-size:0.85rem;"><input type="radio" name="q3" value="A"> Tidak ada bau, murni aliran air tersumbat</label>
      <label style="display:block;font-size:0.85rem;"><input type="radio" name="q3" value="B"> Ya, bau gas menyengat dari kloset dan got sekitar</label>
    </div>
  </form>
  <div id="swcQuizResult" style="display:none;margin-top:16px;padding:14px;border-radius:8px;background:#e0f2fe;border:1px solid #7dd3fc;">
    <div id="swcQuizTitle" style="font-weight:700;color:#0369a1;margin-bottom:6px;"></div>
    <div id="swcQuizText" style="font-size:0.85rem;color:#334155;margin-bottom:12px;"></div>
    <a id="swcQuizCta" href="#" target="_blank" rel="noopener noreferrer" style="display:inline-block;background:#22c55e;color:#fff;text-decoration:none;padding:10px 18px;border-radius:6px;font-weight:700;font-size:0.9rem;">Chat WhatsApp Sekarang</a>
  </div>
</div>
<script>
function runDiagnosa() {
  const f = document.getElementById('swcDiagnosaForm');
  const q1 = f.q1.value; const q2 = f.q2.value; const q3 = f.q3.value;
  if (!q1 || !q2 || !q3) return;
  if (window.dataLayer) window.dataLayer.push({event: 'quiz_diagnosa_complete'});
  let countB = (q1==='B'?1:0) + (q2==='B'?1:0) + (q3==='B'?1:0);
  const resBox = document.getElementById('swcQuizResult');
  const t = document.getElementById('swcQuizTitle');
  const d = document.getElementById('swcQuizText');
  const c = document.getElementById('swcQuizCta');
  resBox.style.display = 'block';
  if (countB >= 2) {
    t.innerHTML = '⚠️ Indikasi Kuat: Bak Septic Tank Anda Penuh Lumpur';
    d.innerHTML = 'Kondisi ini membutuhkan penyedotan tuntas dengan mesin tangki vakum agar resapan air kembali normal.';
    c.href = 'https://wa.me/6281388884349?text=Halo%20Admin%20Sedot%20WC,%20hasil%20kuis%20diagnosa%20menunjukkan%20septic%20tank%20saya%20penuh.%20Mohon%20bantuan%20armada%20terdekat.';
    c.innerText = 'Pesan Truk Kuras Tangki (Respon < 5 Mnt)';
  } else {
    t.innerHTML = '🔧 Indikasi: Pipa Saluran Tersumbat Benda Asing / Lemak';
    d.innerHTML = 'Kloset/wastafel tersumbat tanpa septic tank penuh. Butuh pelancaran kawat spiral baja tanpa bongkar keramik.';
    c.href = 'https://wa.me/6281388884349?text=Halo%20Admin%20Sedot%20WC,%20hasil%20kuis%20diagnosa%20saluran%20pipa%20saya%20tersumbat.%20Bisa%20kirim%20tukang%20pelancar%20pipa%20hari%20ini?';
    c.innerText = 'Pesan Layanan Pelancar Pipa Tanpa Bongkar';
  }
}
</script>
<!-- /wp:html -->
```

---

### 📏 Widget 2: Kalkulator Estimasi Kebutuhan Selang & Akses Armada Truk
* **Estimasi Penambahan Dwell Time:** +1,5 Menit.
* **Tujuan:** Menjawab keraguan pemilik rumah di dalam gang sempit mengenai kemampuan truk armada menjangkau rumah mereka.
* **Mekanisme Interaktif:**
  * Pengunjung memasukkan jarak perkiraan rumah ke tepi jalan raya (misal: *30 meter, 60 meter, 80 meter*).
  * Pengunjung memilih lebar jalan depan rumah (*< 2 meter*, *2,5 meter*, *> 3 meter*).
* **Output Sistem:**
  * *"Rekomendasi: Pos armada kami akan mengerahkan **Truk Engkel Kecil (Roda 4)** dengan sambungan selang **[X] Meter** berdaya hisap tinggi tanpa biaya siluman."*
  * Tombol CTA: *"Kirim Data Ini ke Admin WA untuk Cek Kesiapan Armada Hari Ini"*.

#### 📦 Kode Blok Gutenberg Resmi (Kalkulator Selang):

```html
<!-- wp:html -->
<div class="swc-calc-card" style="background:#f8fafc;border:2px solid #059669;border-radius:12px;padding:20px;margin:28px 0;font-family:sans-serif;">
  <h3 style="margin-top:0;color:#0f172a;font-size:1.15rem;display:flex;align-items:center;gap:8px;">
    📏 <span>Kalkulator Jarak Selang & Armada Gang Sempit</span>
  </h3>
  <div style="display:flex;flex-direction:column;gap:14px;">
    <div>
      <label style="font-weight:600;font-size:0.9rem;display:block;margin-bottom:6px;">Perkiraan Jarak Rumah ke Jalan Utama / Parkir Truk:</label>
      <input type="range" id="swcDistRange" min="10" max="100" step="5" value="30" oninput="runCalc()" style="width:100%;accent-color:#059669;">
      <div style="font-size:0.85rem;color:#059669;font-weight:700;margin-top:4px;"><span id="swcDistVal">30</span> Meter</div>
    </div>
    <div>
      <label style="font-weight:600;font-size:0.9rem;display:block;margin-bottom:6px;">Lebar Jalan di Depan Rumah:</label>
      <select id="swcRoadWidth" onchange="runCalc()" style="width:100%;padding:8px;border-radius:6px;border:1px solid #cbd5e1;font-size:0.85rem;">
        <option value="narrow">Gang Sempit (< 2.5 Meter - Hanya Motor)</option>
        <option value="medium">Jalan Lingkungan (2.5 - 3 Meter - Muat Truk Engkel Roda 4)</option>
        <option value="wide">Jalan Lebar (> 4 Meter - Muat Truk Standar Roda 6)</option>
      </select>
    </div>
  </div>
  <div id="swcCalcResult" style="margin-top:16px;padding:14px;border-radius:8px;background:#ecfdf5;border:1px solid #6ee7b7;">
    <div id="swcCalcRec" style="font-weight:700;color:#047857;margin-bottom:6px;">Rekomendasi Armada: Truk Engkel Roda 4 + Selang 40M</div>
    <div id="swcCalcDetail" style="font-size:0.85rem;color:#334155;margin-bottom:12px;">Armada engkel lincah siap bermanuver di jalan lingkungan dengan daya hisap vakum stabil.</div>
    <a id="swcCalcCta" href="#" target="_blank" rel="noopener noreferrer" style="display:inline-block;background:#22c55e;color:#fff;text-decoration:none;padding:10px 18px;border-radius:6px;font-weight:700;font-size:0.9rem;">Konfirmasi Armada ke WhatsApp</a>
  </div>
</div>
<script>
function runCalc() {
  const d = parseInt(document.getElementById('swcDistRange').value);
  document.getElementById('swcDistVal').innerText = d;
  const w = document.getElementById('swcRoadWidth').value;
  const rec = document.getElementById('swcCalcRec');
  const det = document.getElementById('swcCalcDetail');
  const cta = document.getElementById('swcCalcCta');
  let armada = (w === 'narrow') ? 'Truk Parkir di Jalan Utama + Selang Khusus ' + (d + 10) + ' Meter' : (w === 'medium' ? 'Truk Engkel Roda 4 (Masuk Jalan 2.5M) + Selang ' + (d + 5) + ' Meter' : 'Truk Standar Kapasitas Penuh + Selang ' + d + ' Meter');
  rec.innerText = 'Rekomendasi: ' + armada;
  det.innerText = 'Mesin vakum bertekanan tinggi menjamin daya hisap maksimal hingga jarak 100M tanpa biaya tersembunyi.';
  cta.href = 'https://wa.me/6281388884349?text=Halo%20Admin%20Sedot%20WC,%20saya%20butuh%20' + encodeURIComponent(armada) + '%20untuk%20kuras%20di%20lokasi%20saya.%20Bisa%20jadwalkan%20hari%20ini?';
  if (window.dataLayer) window.dataLayer.push({event: 'calculator_selang_used', distance: d, road_width: w});
}
runCalc();
</script>
<!-- /wp:html -->
```

---

## 📊 3. Pelacakan Event Interaktif di GA4

Setiap interaksi pada widget ini wajib dipasangi event pelacakan kustom:
* Event `quiz_diagnosa_start` (Saat pertanyaan pertama diklik).
* Event `quiz_diagnosa_complete` (Saat hasil rekomendasi tampil).
* Event `calculator_selang_used` (Saat slider atau input jarak diisi).
* Event `whatsapp_click_from_widget` (Konversi utama yang dihasilkan).
