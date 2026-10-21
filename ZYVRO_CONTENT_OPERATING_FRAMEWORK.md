# ZYVRO CONTENT OPERATING FRAMEWORK

**Owner:** Zyvro Content Intelligence Agent
**Version:** 1.0 (2026-10-21)
**Status:** ACTIVE — dibuat setelah knowledge audit, repository inspection, dan capability audit nyata.
**Bukan pengganti knowledge.** Dokumen ini menggabungkan `AGENT-CHARTER.md`, `ZYVRO_BRAND_CONTEXT.md`, `PRODUCT_INTELLIGENCE.md`, `CONTENT_STRATEGY.md`, `PLATFORM_PLAYBOOK.md`, `VISUAL_PRODUCTION.md`, `COMPETITOR_INTELLIGENCE.md`, `PUBLISHING_AND_APPROVAL.md` menjadi urutan tindakan yang bisa dijalankan berulang. Jika bertentangan dengan charter atau knowledge, charter/knowledge menang dan konflik dicatat di change log bawah.

Lokasi state kerja: `agent-state/STATE_<tanggal>.md` (catatan operasional per sesi).
Lokasi produksi konten: `content-production/<paket>/`.

---

## A. STARTUP PROTOCOL

**Kapan:** setiap sesi kerja dimulai, sebelum menulis konten apa pun.
**Input:** dokumen ini + state sesi terakhir.

1. Baca file ini. Baca `agent-state/STATE_*.md` terbaru (bila ada).
2. Baca knowledge yang relevan dengan tugas sesi (minimal charter + content strategy; tambah product intelligence / visual / publishing bila tugas menyentuh area itu).
3. Tentukan tujuan sesi dan produk/repo yang relevan dari state atau dari permintaan.
4. Verifikasi referensi repo sebelum dipercaya: `git log -1` / GitHub API untuk branch aktif + commit SHA per repo (state bisa basi; verifikasi, jangan asumsikan).
5. Deteksi perubahan sejak state terakhir: bandingkan SHA; bila berbeda, baca commit baru yang relevan (API `commits?sha=<branch>`), jangan re-inspeksi seluruh repo.
6. Catat startup report singkat (knowledge dibaca, repo+commit diperiksa, tool yang dibutuhkan, tujuan, hambatan).

**Bukti berhasil:** startup report berisi SHA yang benar-benar dibaca hari itu.
**Jika gagal (state hilang/rusak):** jalankan inspeksi penuh ulang (B), lalu tulis state baru. Jangan berpura-pura framework sudah berjalan.

## B. PRODUCT INTELLIGENCE PROTOCOL

**Kapan:** sebelum klaim produk apa pun; dan saat SHA berubah.
**Input:** akses repo (clone lokal di `/home/user/product-repos/` atau GitHub API).

1. Kunci identitas revisi: repo, branch, commit SHA penuh, tanggal, working tree status. Tulis di laporan.
2. Baca struktur sesuai proyek nyata (Godot: `game/project.godot`, scenes, scripts, tests; web game: `index.html`, `src/`, `tools/`). Jangan asumsikan engine.
3. Untuk setiap fitur kandidat konten, klasifikasikan F0–F5 (PRODUCT_INTELLIGENCE §6) dan beri label bukti VERIFIED / LIKELY / ASSUMPTION / HYPOTHESIS / UNKNOWN per klaim spesifik.
4. Pisahkan selalu: (a) ada di source, (b) terintegrasi, (c) teramati runtime (siapa yang mengamati, kapan, lingkungan apa), (d) boleh diklaim publik.
5. Change detection: bandingkan branch aktif vs baseline (main atau state sebelumnya) via API compare / log; kelompokkan dampak (New Capability, UX Change, Visual, Bug Fix, Experiment, Regression, Infrastructure, Unclear).
6. Baca dokumen ukur proyek bila ada (audit, delivery report, qa-evidence README) — mereka sering memuat status jujur PASS/NOT TESTED/BLOCKED yang langsung pakai.
7. Jangan mengubah source produk. Temuan bug → catat untuk developer, bukan perbaiki.

**Bukti berhasil:** product state report berisi SHA, daftar verified vs unverified, dan batas klaim.
**Jika repo tidak terjangkau:** tandai UNKNOWN/BLOCKED; jangan klaim telah memeriksa.

## C. CONTENT DECISION PROTOCOL

**Kapan:** setelah product state report.
**Input:** temuan B + knowledge CONTENT_STRATEGY.

1. Lengkapi tiga gate: Integrity → Audience Value → Strategic Value. Gagal integrity = stop.
2. Pilih pillar (A–G) dan story angle (1–7) yang paling cocok dengan bukti, bukan dengan tren.
3. Skor 6 dimensi (0–5) hanya sebagai alat bantu prioritas; evidence gate tetap mengikat.
4. Satu konten = satu tujuan utama. Tentukan audiens utama eksplisit.
5. Pilih format dari kebutuhan cerita: gerakan/interaksi → video; satu perubahan terlihat → gambar before/after; urutan alasan → carousel; pelajaran/perspektif → text-led.
6. Tentukan platform dari tujuan + audiens + kemampuan produksi nyata (lihat ledger capability di state). Akun/platform yang belum diverifikasi aktif = jangan jadikan tujuan publikasi.
7. CTA harus sesuai tahap produk; tidak ada CTA lebih baik daripada CTA palsu. Bila tidak ada tujuan live/URL yang valid, CTA maksimal diskusi autentik atau tanpa CTA.
8. Putuskan status: PUBLISHABLE / NEEDS_CAPTURE / NEEDS_VERIFICATION / INTERNAL_ONLY / NOT_WORTH_PUBLISHING / BLOCKED. "Tidak posting" adalah keputusan valid.

## D. VISUAL PRODUCTION PROTOCOL

**Kapan:** setiap paket konten yang butuh visual.
**Mode prioritas:** (A) actual capture produk berjalan → (B) edited capture → (D) hybrid → (C) AI concept berlabel. Konsep AI tidak pernah menjadi bukti fitur.

Capability capture yang sudah terverifikasi di sandbox ini (per 2026-10-21):
- **DUSKHOLD (Scary-Night):** serve repo dengan `python3 tools/devserver.py <port> 0.0.0.0`; QA runtime `node tools/survival-devqa.mjs --port=<port>` (perlu `npm ci --prefix tools` sekali); capture frame `node tools/survival-look.mjs --out=<dir-luar-repo> --port=<port2>` (jangan menulis ke dalam repo produk). Lingkungan: headless Chromium + software WebGL → frame rate tidak representatif perangkat nyata; wajib dicatat di manifest.
- **Cyber-Strike (EXOCONFLICT/Project Overdrive):** build web TIDAK bisa dijalankan di sandbox (payload `web/index.pck`+`index.wasm` kini LFS; host LFS dan host artefak CI tidak terjangkau). Gunakan bukti yang sudah ada: `qa-evidence/**` (actual capture, software-rendered) + log CI + dokumen ukur. Tandai NEEDS_CAPTURE bila cerita butuh frame baru.
- **Android/device:** UNAVAILABLE. Jangan pernah mengklaim perilaku perangkat.

Aturan eksekusi:
1. Tentukan fungsi utama visual (proof/demonstration/comparison/explanation/concept/atmosphere/education/announcement).
2. Capture hanya lewat tool yang benar-benar ada; catat revisi, viewport, environment, skenario, dan batasan di `CAPTURE_MANIFEST.md` paket.
3. Simpan aset konten di `content-production/` (workspace knowledge), bukan di repo produk.
4. Quality gate A–E (VISUAL_PRODUCTION §12) sebelum menandai READY.
5. Kegagalan capture → laporkan (PRODUCTION FAILURE REPORT singkat), jangan ganti dengan visual sintetis berlabel salah.

## E. RESEARCH PROTOCOL

**Kapan:** butuh konteks eksternal (platform, kompetitor, tren, aturan store).
1. Sumber prioritas: dokumentasi resmi platform → data akun sendiri (bila ada) → konten publik akun pembanding → diskusi komunitas.
2. Setiap temuan: sumber + URL + tanggal akses + tingkat keyakinan; pisahkan OBSERVED / INTERPRETATION / ALTERNATIVE EXPLANATION / HYPOTHESIS.
3. Jangan klaim metrik internal kompetitor atau tren dari satu contoh.
4. Simpan ringkasan riset di state atau laporan, bukan sebagai fakta permanen knowledge.

## F. QUALITY & APPROVAL PROTOCOL

**Kapan:** sebelum menyerahkan paket apa pun untuk review manusia.
1. Jalankan checklist internal PUBLISHING_AND_APPROVAL §8 (fakta/visual/brand/publikasi) dan 10 pertanyaan charter §13.
2. Klasifikasikan risiko: A rendah / B menengah (demo fitur, klaim kemampuan produk) / C tinggi (angka bisnis, tanggal rilis, kemitraan, keamanan). Ragukan → naikkan level.
3. Semua konten publik fase ini = minimal approval manusia spesifik (versi caption, visual, platform, akun). Siapkan Content Approval Package lengkap; status `NEEDS_HUMAN_REVIEW`.
4. Tidak ada tindakan eksternal (posting, jadwal, DM, reply, upload store) tanpa otorisasi eksplisit. Default: draft only.
5. Jangan masukkan secrets, token, data internal belum disetujui, atau path kredensial ke materi apa pun.

## G. PERSISTENCE PROTOCOL

**Kapan:** akhir setiap sesi, dan setiap kali keputusan penting diambil.
Simpan/update di `agent-state/STATE_<tanggal>.md`:
- Peta repo: nama, peran, branch aktif, SHA terakhir diperiksa, cara menjalankan/memverifikasi.
- Temuan terverifikasi yang mahal diperoleh (hasil QA, capture, status CI) agar tidak diulang.
- Status pipeline konten per item (IDEA…PUBLISHED/REJECTED) + lokasi paket.
- Blocker terbuka + pemilik tindakan berikutnya.
- Konflik knowledge/dokumen yang ditemukan (mis. nama produk basi, registry stale).
- Change log framework ini (tanggal, perubahan, alasan, status PROPOSED/TESTED/VERIFIED).
Jangan menyimpan dump besar; simpan konteks yang mengurangi kerja berulang. Aset besar tinggal di `content-production/` atau repo produk, dirujuk path-nya.

## H. OUTPUT PROTOCOL

Format minimal per jenis keluaran:
- **Startup report:** knowledge dibaca; repo+SHA; perubahan sejak state; tool & batasan; tujuan; hambatan.
- **Product state report:** template PRODUCT_INTELLIGENCE §13 (ringkas, berisi verified/unverified/blocker/next action).
- **Content brief:** template CONTENT_STRATEGY §16 + status verifikasi tiap klaim + label visual.
- **Approval package:** template PUBLISHING_AND_APPROVAL §6.
- **Production report:** aset dihasilkan (path, label source type, revisi), gate yang lulus, yang gagal.
- **Blocker report:** hambatan, dampak, bukti, alternatif, tindakan yang diperlukan pemilik.

---

## CHANGE LOG FRAMEWORK

| Tanggal | Perubahan | Alasan | Status |
|---|---|---|---|
| 2026-10-21 | v1.0 dibuat | Initial execution task (Task D) setelah knowledge audit + repo inspection + capability audit | TESTED sebagian: prosedur D (capture DUSKHOLD) dan B (API/clone) sudah dijalankan sukses sesi ini; prosedur E/F menunggu用例 nyata |

Catatan verifikasi v1.0: langkah yang sudah terbukti berjalan di sandbox ini dicatat di ledger capability `agent-state/STATE_2026-10-21.md`. Langkah yang bergantung kemampuan belum teruji ditandai di sana, bukan di sini.
