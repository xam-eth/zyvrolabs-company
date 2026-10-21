# ⚠️ SUPERSEDED — PAKET ZV-001 VERSI 1 DITARIK

**Ditulis:** 2026-10-21 · **Status paket v1:** WITHDRAWN (bukan lagi `NEEDS_HUMAN_REVIEW`) · **Jangan publikasikan materi di folder ini.**

## Alasan penarikan (bukti)

Capture di `captures/` berasal dari revisi `376117d6` (BUILD 25). Setelah paket ini disiapkan, pemilik produk melaporkan bahwa rig zombie pack **"jalan baring"** — tubuh terbaring telentang (kaki ke atas) dan arah hadap 100% salah. Roadmap produk mengonfirmasi hal yang sama pada frame evidence BUILD 25: "tubuh horde terbaring telentang (kaki ke atas) dan skala meledak."

**Akar penyebab (terukur oleh dev, dibaca dari `xam-eth/Scary-Night` `docs/REBUILD-ROADMAP.md` § BUILD 26):** setiap varian pack menggantung di bawah node `rig_CharRoot*` yang membawa konversi sumbu FBX→glTF (quaternion −90° X). `zombipack3d._split` me-reparent mesh keluar dari bawah node itu ke group identitas, sehingga konversi sumbu hilang.

**Perbaikan:** BUILD 26 (commit `7f56bffd`, 2026-10-21) menyimpan `lostOrientation` dan memakainya kembali di root tiap varian. Verifikasi dev: probe render terkontrol + `glbtest` check baru (137/137 menurut dev).

## Pelajaran untuk agent (dicatat jujur)

Pada v1 agent menyatakan frame `gate.png` menunjukkan pasukan "menghadap kamera/gerbang" — tafsir visual mentah itu **keliru**; troop memang berdiri "di udara" karena memang terbaring. Sejak ini agent **tidak membuat klaim arah/pose dari satu screenshot statis** tanpa hasil ukur (probe/test) yang mendukungnya. Lihat framework v1.1 (Precision Language Gate + Claim-to-Evidence Traceability).

## Status pengganti

Paket **ZV-001 versi 2** sedang disiapkan terhadap revisi `57fe3373` (BUILD 26): capture ulang + cerita jujur mengenai bug dan perbaikannya + claim audit + asset manifest. Bukti runtime versi baru (dijalankan agent 2026-10-21): `survival-devqa` **24/25 PASS**; satu pengecualian terbuka — check `health` mencatat 3 request GLB `net::ERR_ABORTED` (sedang diinvestigasi; tidak diklaim bersih sampai penyebab terkonfirmasi).
