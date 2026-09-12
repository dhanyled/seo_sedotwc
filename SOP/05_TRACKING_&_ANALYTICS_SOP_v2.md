# SOP Master Pelacakan, Analitik & Triangulasi Data (Versi 2.0)

> **Status Dokumen:** Master SOP Pelacakan Perilaku Pengunjung & Konversi Iklan (V2.0 - Active).  
> **Website Target:** https://sedotwcdijakarta.com/  
> 
> ### 🔄 Peta Hubungan Resiprokal (Reciprocal Workflow Role):
> * **Hulu / Objek Pantauan Organik:** Memantau artikel terbitan [`SOP/01_CONTENT_WRITER_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/01_CONTENT_WRITER_SOP_v2.md) & [`Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/04_PUBLISHING_ROADMAP_&_KEYWORD_ABSORPTION_v2.md), kuis & kalkulator dari [`Silo/03_GAMIFIKASI_DWELL_TIME_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/Silo/03_GAMIFIKASI_DWELL_TIME_v2.md), serta konversi AI dari [`SOP/03_AI_SEARCH_&_FAN_OUT_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/03_AI_SEARCH_&_FAN_OUT_SOP_v2.md).
> * **Hulu / Objek Pantauan Iklan:** Memantau konversi Halaman 749 Google Ads yang dirancang pada [`.agents/copywriting_master_system_lp_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/copywriting_master_system_lp_v2.md) dan trigger kata kunci dari [`.agents/ifso_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/ifso_v2.md).
> * **Hilir / Tindak Lanjut Peringkat:** Temuan kueri potensial di posisi 4–20 dialirkan ke [`SOP/04_MONTHLY_GSC_LINKING_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/04_MONTHLY_GSC_LINKING_SOP_v2.md) untuk injeksi internal link.
> * **Hilir / Tindak Lanjut Retensi:** Temuan dwell time < 30 detik menjadi sinyal revisi hook bagi penulis di [`SOP/01_CONTENT_WRITER_SOP_v2.md`](file:///D:/Dhany/Client/sedotwcdijakarta/SOP/01_CONTENT_WRITER_SOP_v2.md).
> * **Tata Kelola Induk:** Kredensial akun dan guardrail mengacu ke [`.agents/AGENTS.md`](file:///D:/Dhany/Client/sedotwcdijakarta/.agents/AGENTS.md).

---

## 🛠️ 1. Ekosistem Pelacakan & Konfigurasi MCP

| Tool / Platform | Identifier / Akun Resmi | Peran & Parameter Pelacakan |
| :--- | :--- | :--- |
| **Google Analytics 4 (GA4)** | Property ID: `546175720` (Sedotwcdijakarta) | Pelacakan kuantitatif: *User Engagement, Scroll Depth (25%-90%), WA Clicks, Form Submits, If-So Triggers*. |
| **Microsoft Clarity** | Project ID: `xovu751tup` | Pelacakan kualitatif & visual: *Heatmaps, Session Recordings, Dead Clicks, Rage Clicks, Quick Backs*. |
| **Google Search Console** | Site: `https://sedotwcdijakarta.com/` | Analitik pencarian organik: *Queries, Impressions, CTR, Average Position*. |
| **Google Ads (GSN)** | Akun: `2401751609` / `1262123968` | Pelacakan konversi iklan berbayar: *Cost per Lead, Keyword Conversion Rate*. |
| **Telegram Lead Alerts** | Bot: `@LookerSendJpgReportBot`<br/>Group Chat: `-1003207388237` | Notifikasi instan saat formulir Click-to-Chat / Greetings dikirim pengunjung. |

---

## 📐 2. Metode Triangulasi Data (GA4 + Clarity + GSC)

Analisis data tidak boleh hanya bergantung pada satu sumber. Kombinasikan angka kuantitatif GA4 dengan rekaman visual Clarity untuk diagnosa presisi:

```
┌─────────────────────────────────┐     ┌─────────────────────────────────┐
│     GA4 (Indikator Kuantitatif) │     │  Clarity (Indikator Kualitatif) │
│ • Engagement Time < 30 detik    │ ──➔ │ • Rekaman: User kena Quick Back │
│ • Bounce Rate tinggi            │     │ • Dead Click di gambar/nomor WA │
└─────────────────────────────────┘     └─────────────────────────────────┘
                                   │
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                        TINDAKAN PERBAIKAN PRESISI                      │
│ 1. Buat hook 3 baris pertama lebih lugas & hilangkan kata klise AI     │
│ 2. Jadikan elemen yang diklik keliru sebagai tombol WhatsApp asli      │
│ 3. Pastikan floating CTA tidak menutupi tombol navigasi penting HP     │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🎯 3. Matriks Diagnosa Masalah & Solusi Konversi

| Gejala Data Gabungan | Akar Masalah Lapangan | Tindakan Perbaikan Cepat |
| :--- | :--- | :--- |
| **Engagement Time < 30 Detik + Quick Backs** | Judul iklan / SEO tidak cocok dengan 3 detik pertama artikel. Pembaca merasa salah alamat. | Tulis ulang paragraf pembuka (*Hook*). Sebutkan masalah darurat di baris pertama dan sematkan nomor WA langsung di atas. |
| **Scroll Depth < 50% + Tidak Ada Klik WA** | Tombol CTA WhatsApp diletakkan terlalu jauh di bawah, sementara pembaca butuh bantuan mendesak. | Pindahkan tombol WhatsApp ke paruh atas (*Above the Fold* / area 30%). Gunakan floating CTA kanan bawah. |
| **Dead Clicks / Rage Clicks Tinggi di Clarity** | Pengunjung mengira gambar brosur, ikon truk, atau teks nomor telepon bisa diklik, namun ternyata statis. | Ubah gambar brosur atau nomor telepon teks menjadi tautan interaktif langsung ke WhatsApp (`https://wa.me/...`). |
| **High Impression di GSC tapi Low CTR (< 2%)** | Judul meta snippet di Google kurang memikat atau kalah menarik dari kompetitor. | Perbarui Meta Title & Meta Description dengan menyisipkan pemicu konversi: *"Respon < 5 Menit"*, *"Garansi Tuntas"*, *"Harga Jujur"*. |
| **Banyak Form Submit tapi Sedikit yang Chat WA** | Form greetings terlalu panjang atau formulir tidak langsung mengarahkan ke aplikasi WhatsApp. | Pastikan form submit otomatis membuka chat WhatsApp pelanggan dengan teks tersusun rapi. |
