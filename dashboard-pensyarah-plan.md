# Dashboard Maklumat Pensyarah — Diploma Kejuruteraan Awam, Politeknik PD

## Overview

Bina sebuah fail HTML tunggal (single-page dashboard) yang memaparkan maklumat pensyarah Jabatan Kejuruteraan Awam di Politeknik Port Dickson. Dashboard menggunakan tema **Neon & Dark (Cyberpunk Futuristik)** — latar hitam/gelap dengan warna neon (biru, cyan, ungu, pink). Data pensyarah disimpan sebagai array JavaScript statik dalam fail yang sama. Tiada framework luaran — guna HTML + CSS + vanilla JavaScript sahaja supaya fail boleh dibuka terus dalam pelayar tanpa server.

---

## Sub-Task 1 — Struktur HTML & Tema Neon Dark

**Intent:** Bina kerangka utama fail HTML dengan tema cyberpunk futuristik — latar gelap, tipografi neon, animasi glow, dan grid layout responsif.

**Expected Outcomes:**
- Fail `dashboard-pensyarah.html` wujud dan boleh dibuka dalam pelayar
- Header menunjukkan nama jabatan dan logo/ikon
- Sidebar navigasi dengan tab: Ringkasan, Profil Pensyarah, Statistik
- Warna neon konsisten (--neon-cyan, --neon-purple, --neon-pink, --neon-blue)
- Animasi subtle: glow pulse pada border kad, scanline effect pada background

**Todo List:**
- [ ] Cipta fail `dashboard-pensyarah.html`
- [ ] Tambah CSS variables untuk warna neon dan dark theme
- [ ] Bina struktur `<header>`, `<nav>` sidebar, dan `<main>` content area
- [ ] Tambah Google Fonts (Orbitron untuk heading, Rajdhani untuk body — futuristik feel)
- [ ] Tambah CSS animasi: glow, pulse, scanline background

**Relevant Context:**
- Fail tunggal: semua CSS dan JS inline dalam satu HTML
- Font: Orbitron (heading) + Rajdhani (body) dari Google Fonts CDN

**Status:** [ ] pending

---

## Sub-Task 2 — Data Dummy Pensyarah (JavaScript Array)

**Intent:** Cipta set data dummy 8 pensyarah Diploma Kejuruteraan Awam yang realistik sebagai array JavaScript dalam fail HTML. Data ini mudah diganti dengan data sebenar kemudian.

**Expected Outcomes:**
- Array `pensyarahData` dengan 8 rekod pensyarah lengkap
- Setiap rekod mengandungi semua medan yang diperlukan

**Data Fields setiap pensyarah:**
```
id, nama, jawatan, gred, jantina, kelayakan, institusi, tahun_mula,
pengkhususan, subjek_diajar[], keahlian_profesional[], latihan[],
email, telefon, gambar_inisial (2 huruf untuk avatar)
```

**Todo List:**
- [ ] Tambah `const pensyarahData = [...]` dengan 8 pensyarah dummy
- [ ] Pastikan variasi data: 2 PhD, 4 Master, 2 Degree; campuran jantina; pelbagai pengkhususan (Struktur, Hidraulik, Geoteknik, Ukur Bahan)
- [ ] Tambah `const jabatanInfo` untuk metadata (nama jabatan, politeknik, bil. pelajar, dsb.)

**Relevant Context:**
- Pengkhususan DKA: Struktur & Bahan, Hidraulik & Hidrologi, Geoteknik, Ukur Bahan & Kos, BIM/CAD

**Status:** [ ] pending

---

## Sub-Task 3 — Seksyen Ringkasan (KPI Cards)

**Intent:** Paparan statistik cepat di halaman utama menggunakan KPI cards dengan neon glow effect — memberikan gambaran keseluruhan jabatan secara sekilas.

**Expected Outcomes:**
- 6 KPI cards: Jumlah Pensyarah, Bilangan PhD, Bilangan Master, Pensyarah Tetap, Pensyarah Wanita, Purata Tahun Pengalaman
- Angka dikira secara automatik dari `pensyarahData`
- Animasi counter (angka naik dari 0 ke nilai sebenar apabila kad muncul)
- Hover effect: border neon glow lebih terang

**Todo List:**
- [ ] Bina fungsi `renderKPICards()` yang kira statistik dari data
- [ ] Cipta CSS untuk KPI card dengan neon border dan glow shadow
- [ ] Tambah animasi counter JavaScript apabila seksyen dipaparkan

**Relevant Context:**
- Dikira automatik — tidak hardcode nilai

**Status:** [ ] pending

---

## Sub-Task 4 — Seksyen Profil Pensyarah (Grid + Modal)

**Intent:** Paparkan semua pensyarah dalam grid kad. Klik pada kad untuk buka modal/popup dengan maklumat penuh pensyarah.

**Expected Outcomes:**
- Grid responsif 3-4 kolum kad pensyarah
- Setiap kad: avatar inisial berwarna neon, nama, jawatan, pengkhususan, badge kelayakan
- Klik kad → modal popup dengan maklumat lengkap (semua fields dari data)
- Modal mengandungi: tab mini (Maklumat Am, Pengajaran, Pembangunan Profesional)
- Fungsi carian dan penapis (mengikut pengkhususan, kelayakan, jantina)

**Todo List:**
- [ ] Bina fungsi `renderPensyarahGrid()` untuk jana kad dari data
- [ ] Cipta CSS untuk kad pensyarah dengan hover tilt effect dan neon glow
- [ ] Bina modal HTML + CSS (overlay gelap, panel kaca/glassmorphism)
- [ ] Tambah fungsi `openModal(id)` dan `closeModal()`
- [ ] Bina bar carian (input) + dropdown penapis
- [ ] Tambah fungsi `filterPensyarah()` yang update grid secara dinamik

**Relevant Context:**
- Avatar: bulatan dengan inisial 2 huruf, warna neon berbeza setiap pensyarah (guna hue rotation)
- Modal guna glassmorphism di atas latar neon dark untuk contrast yang menarik

**Status:** [ ] pending

---

## Sub-Task 5 — Seksyen Statistik & Carta (Chart.js)

**Intent:** Visualisasikan data pensyarah dalam carta interaktif menggunakan Chart.js CDN.

**Expected Outcomes:**
- 4 carta yang dikira dari `pensyarahData`:
  1. Bar Chart — Bilangan pensyarah mengikut kelayakan (PhD, Master, Degree)
  2. Doughnut Chart — Pembahagian pengkhususan bidang
  3. Pie Chart — Nisbah jantina (Lelaki vs Perempuan)
  4. Bar Chart — Bilangan pensyarah mengikut gred jawatan
- Semua carta guna warna neon palette yang konsisten
- Tooltip hover menunjukkan nilai dan peratus

**Todo List:**
- [ ] Tambah Chart.js via CDN dalam `<head>`
- [ ] Bina fungsi `renderCharts()` yang proses `pensyarahData` dan jana semua carta
- [ ] Style canvas elemen dengan neon glow border
- [ ] Pastikan carta responsive (guna `maintainAspectRatio: false` dalam Chart.js)

**Relevant Context:**
- Chart.js CDN: `https://cdn.jsdelivr.net/npm/chart.js`
- Warna neon untuk carta: cyan (#00f5ff), purple (#b44aff), pink (#ff2d78), blue (#0080ff), green (#00ff9d)

**Status:** [ ] pending

---

## Sub-Task 6 — Navigasi, Animasi & Polish

**Intent:** Sambungkan semua seksyen dengan navigasi sidebar yang berfungsi, tambah animasi page transition, dan pastikan keseluruhan dashboard kelihatan polish dan konsisten.

**Expected Outcomes:**
- Sidebar navigasi: klik tab → tunjuk seksyen berkenaan, sembunyikan yang lain
- Active tab highlighted dengan neon glow
- Smooth fade-in transition antara seksyen
- Footer dengan maklumat jabatan
- Responsive: dashboard masih boleh guna pada skrin 1024px ke bawah
- Semua fungsi render dipanggil semasa page load

**Todo List:**
- [ ] Bina fungsi `showSection(sectionId)` untuk navigasi tab
- [ ] Tambah CSS transition: `opacity` dan `transform` untuk fade-in
- [ ] Cipta footer dengan nama politeknik, jabatan, tahun
- [ ] Uji semua interaksi: navigasi, modal, carian, penapis, carta
- [ ] Tambah `window.onload` yang panggil semua fungsi render awal

**Relevant Context:**
- Semua seksyen ada `class="section"` dan `display:none` kecuali yang aktif
- Navigasi guna `data-target` attribute untuk identify seksyen

**Status:** [ ] pending

---

## Fail Output

| Fail | Penerangan |
|---|---|
| `dashboard-pensyarah.html` | Satu fail HTML lengkap — boleh terus buka dalam pelayar |

## Teknologi

| Teknologi | Tujuan |
|---|---|
| HTML5 + CSS3 | Struktur dan styling |
| Vanilla JavaScript | Logik, render, interaktiviti |
| Chart.js (CDN) | Carta statistik |
| Google Fonts (CDN) | Font Orbitron + Rajdhani |

## Nota untuk Penggantian Data Sebenar

Apabila data sebenar sedia, cari bahagian `const pensyarahData = [...]` dalam fail HTML dan gantikan array tersebut dengan data sebenar. Tiada perubahan lain diperlukan.
