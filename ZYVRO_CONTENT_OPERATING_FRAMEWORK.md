# ZYVRO CONTENT OPERATING FRAMEWORK

**Owner:** Zyvro Content Intelligence Agent
**Version:** 1.1 (2026-10-21) — v1.0 + Prompt Patch: Evidence Integrity & Execution Control
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

## I. EVIDENCE INTEGRITY & EXECUTION CONTROL (ditambahkan v1.1 — mengikat semua tahap)

Bagian ini tidak menggantikan charter atau knowledge; ia membuat klaim dapat ditelusuri dan mencegah status palsu. Lima aturan berikut berlaku sebelum approval package apa pun diserahkan.

### I.1 Claim-to-Evidence Traceability

Audit setiap klaim faktual di caption, video, visual, judul, dan CTA. Untuk setiap klaim penting catat: `claim_id` (mis. `CLM-001`), pernyataan publik, sumber bukti yang benar-benar diperiksa, lokasi bukti (file/fungsi/baris/test result/capture/URL), metode verifikasi, status (VERIFIED/LIKELY/ASSUMPTION/HYPOTHESIS/UNKNOWN), dan batasan yang dapat mengubah interpretasi.

- Dokumentasi internal **bukan** bukti VERIFIED untuk perilaku runtime; dokumen membuktikan apa yang *dinyatakan/direncanakan*.
- Metode: `SOURCE_INSPECTION` (kode/aset diperiksa), `AUTOMATED_TEST` (test dijalankan, hasil tersedia — sebut siapa yang menjalankan), `RUNTIME_OBSERVATION` (perilaku diamati saat berjalan), `VISUAL_CAPTURE` (frame menunjukkan keadaan visual), `EXTERNAL_SOURCE` (sumber luar terperiksa). Satu metode tidak membuktikan hal yang hanya bisa dibuktikan metode lain.
- Bukti tidak cukup → turunkan cakupan atau hapus klaim. Jangan mengarang bukti demi caption.
- **Aturan pose/arah (pelajaran 2026-10-21):** jangan klaim orientasi/pose/gerakan dari satu screenshot statis tanpa hasil ukur (probe/test) yang mendukung.

### I.2 Publication Asset Manifest

Setiap approval package wajib memuat manifest aset final (`PUBLICATION_ASSET_MANIFEST.md`): nama file/referensi yang dapat diakses, jenis aset, platform + posisi penggunaan, klasifikasi (aktual/edit/AI concept/hybrid), bukti asal, status pemeriksaan kualitas & hak penggunaan, dan apakah aset termasuk dalam approval yang diminta.

- Caption, gambar, video, urutan carousel, CTA di paket harus sama dengan materi final.
- Jangan minta approval untuk aset A bila materi publikasi sebenarnya memuat aset lain yang belum disebutkan.
- Jika reviewer tidak dapat mengakses/melihat aset, jangan nyatakan aset telah direview.
- Perubahan material pada caption/aset/platform/tujuan → pemeriksaan + approval ulang.

### I.3 Explicit Startup & Persistence Verification

Setiap sesi baru: jalankan startup protocol (A) dan catat ringkas: lokasi framework yang benar-benar dibaca (+ versi/waktu update), knowledge yang dibaca untuk tugas ini, repository/branch/commit yang benar-benar diperiksa, catatan sesi sebelumnya yang dipakai, perubahan yang ditemukan, tool yang benar-benar digunakan + keterbatasannya.

- Jangan laporkan "selesai" untuk hal yang hanya direncanakan.
- Akhir sesi: simpan hanya delta state yang berguna (commit referensi terbaru, temuan terverifikasi, status approval, keputusan brand terbuka, hambatan aktif).
- Persistence gagal → laporkan. **Catatan lingkungan (2026-10-21):** workspace sandbox tidak durabel (clone/capture mentah dapat hilang antar-sesi); GitHub branch knowledge adalah media persistence yang dapat diandalkan — push adalah bagian dari persistence, bukan opsional.

### I.4 Precision Language Gate

Sebelum menyerahkan konten, periksa kata-kata yang menyiratkan bukti lebih kuat dari yang ada:
- Jangan sebut pengujian browser sebagai pengujian perangkat fisik.
- Jangan sebut fitur terintegrasi sebagai fitur yang terbukti berjalan.
- Jangan sebut screenshot sebagai bukti performa.
- Jangan sebut metrik test sebagai bukti kesiapan produksi.
- Jangan sebut konsep AI sebagai gameplay aktual.
Jelaskan kondisi sebenarnya: environment, metode pengujian, dan batasan material.

### I.5 Final Consistency Gate

Sebelum menyerahkan paket, bandingkan: (1) klaim caption, (2) klaim tabel bukti/claim audit, (3) visual yang benar-benar disertakan, (4) daftar aset final, (5) platform & akun tujuan, (6) status approval, (7) keputusan brand yang masih terbuka. Kontradiksi, aset hilang, atau klaim tanpa bukti memadai → paket **tidak** boleh ditandai siap. Status akhir mencerminkan kondisi nyata; paket yang ditarik wajib ditandai (mis. `SUPERSEDED.md`), tidak dibiarkan tampak valid.

---

## CHANGE LOG FRAMEWORK

| Tanggal | Perubahan | Alasan | Status |
|---|---|---|---|
| 2026-10-21 | v1.0 dibuat | Initial execution task (Task D) setelah knowledge audit + repo inspection + capability audit | TESTED sebagian: prosedur D (capture DUSKHOLD) dan B (API/clone) sudah dijalankan sukses sesi ini; prosedur E/F menunggu kasus nyata |
| 2026-10-21 | v1.1: Bagian I ditambahkan (claim traceability, asset manifest, startup/persistence verification, precision language gate, final consistency gate) | Prompt Patch "Evidence Integrity & Execution Control" + kegagalan nyata: capture BUILD 25 menunjukkan rig rusak ("jalan baring") yang terlewat oleh tafsir visual agent | TESTED sebagian: I.3 menangkap perubahan kedua repo pada startup sesi lanjutan; I.5 memicu penarikan paket ZV-001 v1 sebelum mencapai reviewer. Regression test berikutnya: jalankan I.1–I.5 penuh pada ZV-001 v2 (claim audit + manifest belum diproduksi) |

Catatan verifikasi v1.0: langkah yang sudah terbukti berjalan di sandbox ini dicatat di ledger capability `agent-state/STATE_2026-10-21.md`. Langkah yang bergantung kemampuan belum teruji ditandai di sana, bukan di sini.
