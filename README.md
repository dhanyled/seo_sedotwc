# 🚽 SEO & Publishing Roadmap System — sedotwcdijakarta.com

Repository ini berisi aset laporan audit, simulasi SEO, dan dashboard master penerbitan konten (Topical Authority & 5 Silo Sanitasi) untuk domain **[sedotwcdijakarta.com](https://sedotwcdijakarta.com/)**.

---

## 📊 Akses Laporan & Dashboard HTML

| Nama File Laporan | Deskripsi & Fungsi | Link Akses |
| :--- | :--- | :--- |
| **`index.html`** / **`publishing_schedule_and_silo_roadmap.html`** | **Master Publishing Roadmap & Topical Authority Dashboard**<br/>Memuat pemantauan 30 rencana artikel silo, telemetri real-time, audit penyerapan 800+ kueri, dan framework skalabilitas 2 fase. | [Buka Dashboard](index.html) |
| **`report.html`** | **Laporan Audit Teknis Google Lighthouse**<br/>Audit performa Core Web Vitals, aksesibilitas WCAG, best practices, dan SEO teknis. | [Buka Lighthouse Report](report.html) |
| **`audit_simulasi_keyword_title.html`** | **Audit Simulasi Snippet Judul & SERP**<br/>Simulasi keterbacaan judul meta dan pencegahan pemotongan teks (*title truncation*) di Google SERP. | [Buka Simulasi Judul](audit_simulasi_keyword_title.html) |
| **`blueprint_master_adgroup_ifso.html`** | **Blueprint Ad Groups & Dynamic If-So Insertion**<br/>Pemetaan kata kunci iklan berbayar (GSN) dan integrasi Dynamic Keyword Insertion. | [Buka Blueprint Ad Groups](blueprint_master_adgroup_ifso.html) |
| **`panduan_segmentasi_title_ifso.html`** | **Panduan Segmentasi Judul Dinamis**<br/>Katalog formula judul dinamis berbasis intensi pencarian warga Jabodetabek. | [Buka Panduan Segmentasi](panduan_segmentasi_title_ifso.html) |

---

## 🏛️ Ringkasan Arsitektur 5 Silo & Penyerapan 800+ Kueri

Seluruh kueri pencarian warga Jabodetabek diserap secara sistematis ke dalam 3 saluran utama:
1. **Transaksional (35%):** Diserap oleh Landing Page Iklan (Halaman 749) dan Direct WhatsApp CTA `0813-8888-4349`.
2. **Hiperlokal (15%):** Diserap oleh 6 Halaman Hub Wilayah WordPress (`/jakarta-selatan/`, `/jakarta-barat/`, dll.) dan Google Business Profile.
3. **Edukasi / Informasional (50%):** Diserap ke dalam **30 Artikel Blog Silo** (Rasio 1 Pilar Hub : 5 Pendukung Spoke per Silo).

### Pembagian 5 Silo:
* **Silo 1:** Sedot Septic Tank Pemukiman (`septic-tank-pemukiman`, ID 20) — 6 Artikel
* **Silo 2:** Pelancaran Saluran Pipa Mampet Tanpa Bongkar (`saluran-pipa-mampet`, ID 21) — 6 Artikel
* **Silo 3:** Sedot Lemak & Grease Trap Resto / Dapur MBG (`grease-trap-resto-mbg`, ID 22) — 6 Artikel
* **Silo 4:** Limbah Industri Domestik & Bak STP Non-B3 (`limbah-stp-industri`, ID 23) — 6 Artikel
* **Silo 5:** Direktori Hyperlocal Pos Armada Jabodetabek (`area-layanan-jabodetabek`, ID 24) — 6 Artikel

---

## 📈 Roadmap Skalabilitas 2 Fase (Anti-Kanibalisasi)
* **Fase 1 (Aktif):** 30 Artikel Blog (Minimum Viable Topical Authority) untuk domain warming logaritmik (2–3 artikel/minggu).
* **Fase 2 (Terencana):** Tambahan 15–25 artikel baru (Maksimal 45–55 artikel) setelah evaluasi 60–90 hari via data Google Search Console (`SOP/04`).
