# CONTENT APPROVAL PACKAGE — ZV-001

**Content ID:** ZV-001
**Judul internal:** DUSKHOLD BUILD 24–25 — "pack yang kamu commit sendiri kini jadi horde"
**Versi:** 1
**Status:** NEEDS_HUMAN_REVIEW
**Tanggal disiapkan:** 2026-10-21
**Tingkat risiko:** Level B (demo fitur produk baru + klaim kemampuan terukur) — approval manusia spesifik wajib.

---

## Tujuan

- **Tujuan utama:** Credibility (menunjukkan bukti eksekusi produk nyata, bukan klaim).
- **Target audiens:** Developers & Builders (dev indie/tech builder) + pemain strategy/survival mobile yang mengikuti build-in-public.
- **Platform:** X (thread) — adaptasi utama. Carousel LinkedIn tersedia sebagai versi turunan (perlu approval terpisah, lihat bawah).
- **Akun:** akun bisnis Zyvro Labs (identitas/aktivitas akun belum diverifikasi agent — owner yang memegang akun & publikasi; paket ini draft-only).
- **Format:** X thread 6 post + 2 actual-capture images (`captures/gate.png`, `captures/fight.png`).
- **CTA:** diskusi autentik (pertanyaan yang jawabannya memang belum diputuskan) — BUKAN link produk, karena tidak ada URL live build terkini yang valid (lihat Risiko).

## Materi final (draft caption — versi 1)

**Post 1 (hook):**
> Our horde is now built from the exact GLB pack our founder committed to the repo.
>
> No new models commissioned. One walk clip. We split it into 10 rigs and baked the attack + death we were missing. 🧵

**Post 2 (the constraint):**
> The pack shipped with 10 zombies sharing a single 7.37 s walk clip. No attack. No death. One shared texture atlas.
>
> A survival game can't ship a horde that only strolls. So we split the pack per skeleton (10 self-contained variants) and baked synthetic attack/die clips as real AnimationClips — addressed by each variant's own joint names.

**Post 3 (the result you can see):**
> Three kinds now come over the south gate: shambler, lurcher, wretch — same art family, different silhouettes. The painted atlas survives the crowd bake (we check UVs + a zero emissive-max in QA so nobody "improves" it back). [img: gate.png]

**Post 4 (the proof):**
> The frame above is actual gameplay capture from our web build, revision 376117d — taken by our QA harness, not a render, not a mockup. The same build that passed 25/25 device-facing checks (touch, pause, mid-night reload resume) in headless Chromium this morning.

**Post 5 (the honest part):**
> What this does NOT mean: it's shippable. This ran on software rendering — no real phone, no real fingers yet. Our own readiness audit still says production is not ready, and lists the five non-technical blockers by name. We'd rather publish that than fake a launch.

**Post 6 (CTA — pertanyaan terbuka):**
> Genuine question for devs shipping with asset packs: do you split shared-skeleton packs per body, or retarget everything to one rig? Ours now scales per-variant. Curious what's bitten you.

## Klaim dan bukti

| Klaim | Sumber pendukung | Status |
|---|---|---|
| Pack zombie berisi 10 body ber-rig, 1 klip walk 7,37 s ("Take 001"), tanpa attack/die | `docs/REBUILD-ROADMAP.md` § BUILD 25; file pack di-commit owner (commit `154d27f1`) | VERIFIED (dokumen ukur proyek + file di repo) |
| Dibagi jadi 10 variant rig; klip attack/die sintetis dibake menjadi AnimationClip asli | Roadmap § B25 (`src/game/render3d/zombipack3d.js`) — kode terkonfirmasi ada di clone rev `376117d6` | VERIFIED (source terintegrasi) |
| 3 kind: shambler (variant 0) / lurcher (5) / wretch (9, ber-beanie) | Roadmap § B25 + watermark BUILD 25 + frame capture `gate.png` | VERIFIED (runtime teramati secara tidak langsung lewat capture fresh hari ini; baked kind sichtbar di frame) |
| Atlas terbawa ke bake crowd; rim crimson 0.78/0.2/0.16; glowMax 0 | Roadmap § B25 + `qa-evidence/survival-build25/README.md` (plotsqa §13) | LIKELY (bukti = QA proyek sendiri; agent tidak menjalankan plotsqa ulang) |
| 25/25 device-facing checks lulus | Dijalankan ulang oleh agent ini 2026-10-21 di sandbox: `tools/survival-devqa.mjs` → SUMMARY 25/25 PASS (EXIT 0) terhadap rev `376117d6` | VERIFIED (runtime sandbox, headless Chromium software-WebGL) |
| Readiness audit: "production belum siap", 5 blocker non-teknis | `docs/PRODUCTION-HOOK-RESEARCH.md` + roadmap (dibaca penuh) | VERIFIED (dokumen internal; angka benchmark retensi = sumber pihak ketiga, tidak dipakai di caption) |

**Batasan yang harus diketahui reviewer:**
- Engine jam tidak membuktikan: frame capture berasal dari software rendering → bukan bukti FPS/performa HP.
- Nama produk: paket memakai **DUSKHOLD** (identitas store di `play-listing/LISTING.md`, 19 Okt). Host publik (`scary-night.vercel.app`, `duskhold.zyvrolabs.com`) masih memakai branding lama **"LAST NIGHT"** — karena itu caption tidak memuat link. Keputusan penamaan menunggu owner.
- Horde "buka-bukaan" hanya berlaku mode Survival; roster legacy mansion (demon/werewolf dll.) tidak berubah — caption sudah dibatasi pada "horde".

## Integritas visual

- **Jenis:** ACTUAL_PRODUCT_CAPTURE (tanpa editing) — lihat `CAPTURE_MANIFEST.md`.
- Visual menunjukkan produk aktual (build web rev `376117d6`), bukan konsep.
- Watermark "BUILD 25" pada frame = dari game sendiri; disengaja dipertahankan sebagai penanda tahap prototype (jangan di-crop keluar).
- Disclaimer di caption (Post 5) sudah menyatakan keterbatasan software rendering & status bukan rilis.

## Risiko

- **Informasi internal:** tidak ada secrets/roadmap sensitif. Rincian teknis yang dibagikan sudah tertulis di docs repo.
- **Privasi:** tidak ada data pengguna.
- **Hak penggunaan:** pack berlisensi free pack (nama file mencantumkan "free pack"; KayKit CC0 untuk prop lama tercatat di repo). Capture dari produk sendiri. Tetap: publikasi eksternal material preview = keputusan owner (Level B).
- **Klaim bisnis:** tidak ada angka pengguna/revenue/tanggal rilis. AAB/APK memang belum terbentuk — caption tidak mengklaim ketersediaan apa pun.
- **Risiko platform:** bila owner memilih link di bio ke host lama (branding LAST NIGHT), audiens akan menemui nama berbeda — disarankan selaraskan dahulu atau hindari link produk pada putaran pertama.

## Permintaan keputusan

- [ ] Approve caption versi 1 + `captures/gate.png` untuk X thread (akun bisnis Zyvro Labs), publikasi manual oleh owner.
- [ ] Request changes (catat revisinya).
- [ ] Reject.
- [ ] Hold pending evidence (mis. menunggu host live build terkini / keputusan nama DUSKHOLD vs LAST NIGHT).

**Catatan agent:** paket ini berhenti di draft. Tidak ada publikasi otomatis. Approval versi ini tidak berlaku bila caption/visual diganti secara substantif, platform/akun berubah, atau tautan ditambahkan.
