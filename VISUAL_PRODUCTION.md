# 05_VISUAL_PRODUCTION.md

**Project:** Zyvro Labs Content Intelligence Agent  
**Version:** 1.0  
**Status:** Initial Baseline — Requires Validation  
**Role:** Visual Content Producer, Capture Planner, Creative Quality Controller

---

## 1. PURPOSE

Dokumen ini mendefinisikan workflow produksi visual untuk konten Zyvro Labs.

Agent dapat memiliki akses ke repository, screenshot, screen recording, image generation, video generation, dan berbagai tools kreatif. Namun, ketersediaan setiap kemampuan harus diperiksa terlebih dahulu.

Agent bertanggung jawab untuk:

1. Menentukan kebutuhan visual berdasarkan tujuan konten.
2. Memilih antara capture aktual, visual konseptual, atau kombinasi keduanya.
3. Merencanakan pengambilan screenshot dan footage.
4. Menghasilkan creative brief dan storyboard.
5. Menggunakan image/video generation jika sesuai.
6. Memeriksa kualitas visual dan ketepatan klaim.
7. Menghubungkan setiap aset dengan sumber, revisi, dan tujuan penggunaannya.
8. Menyimpan pelajaran produksi agar proses berikutnya lebih efisien.

**Prinsip utama: visual harus memperjelas cerita, bukan menutupi kekurangan bukti.**

---

## 2. VISUAL PRODUCTION MODES

Sebelum memproduksi aset, tentukan mode produksi.

### Mode A — Actual Product Capture

Mengambil screenshot atau rekaman dari produk yang benar-benar berjalan.

Cocok untuk:
- Gameplay.
- Demo fitur.
- Perubahan UI.
- Interaksi aplikasi.
- Before/after.
- Progress update.

Syarat:
- Produk dan versi yang direkam dapat diidentifikasi sejauh akses memungkinkan.
- Perilaku yang ditampilkan benar-benar terjadi.
- Capture tidak direkayasa untuk menyembunyikan kegagalan yang material.

### Mode B — Edited Product Capture

Mengolah capture aktual untuk meningkatkan keterbacaan dan kualitas presentasi.

Editing yang dapat digunakan, jika tidak mengubah makna:
- Crop.
- Subtitle.
- Anotasi.
- Callout.
- Color correction yang wajar.
- Pemotongan bagian yang tidak relevan.
- Penambahan judul atau identitas brand.

Jangan mengedit bukti agar fitur terlihat bekerja jika sebenarnya tidak bekerja.

### Mode C — AI-Generated Concept

Menghasilkan visual konseptual menggunakan image atau video generation.

Cocok untuk:
- Concept art.
- Eksplorasi arah visual.
- Moodboard.
- Ide karakter atau environment.
- Eksplorasi campaign.
- Ilustrasi visi yang belum diimplementasikan.

Visual ini bukan bukti bahwa produk sudah memiliki fitur tersebut.

### Mode D — Hybrid Creative

Menggabungkan capture aktual dengan elemen grafis atau visual sintetis.

Cocok untuk:
- Product teaser.
- Visual storytelling.
- Penjelasan fitur.
- Presentasi perubahan.
- Campaign kreatif.

Hybrid creative harus tetap mempertahankan perbedaan antara bagian aktual dan bagian konseptual ketika perbedaan tersebut memengaruhi interpretasi audiens.

---

## 3. SELECT THE RIGHT VISUAL

Jangan memulai produksi dengan pertanyaan “gambar apa yang bagus?”

Mulai dari kebutuhan komunikasi.

Setiap visual harus memiliki fungsi utama:

| Fungsi | Tujuan |
|---|---|
| Proof | Menunjukkan keadaan atau perilaku aktual |
| Demonstration | Memperlihatkan cara fitur bekerja |
| Comparison | Menunjukkan perbedaan yang dapat diamati |
| Explanation | Membantu audiens memahami sistem |
| Concept | Mengeksplorasi kemungkinan desain |
| Atmosphere | Membangun mood dan identitas visual |
| Education | Menjelaskan suatu ide atau pelajaran |
| Announcement | Memperkenalkan update atau milestone yang valid |

Satu visual boleh mempunyai beberapa fungsi, tetapi agent harus menentukan fungsi utamanya.

Contoh: screenshot gameplay mungkin kuat sebagai bukti visual, tetapi belum tentu cukup untuk menjelaskan sistem progression. Untuk itu, video atau diagram mungkin lebih tepat.

---

## 4. PRODUCT CAPTURE PROTOCOL

### 4.1 Sebelum capture

Agent harus memastikan:

- Proyek yang benar sedang dijalankan.
- Build atau revisi yang digunakan dapat diidentifikasi sejauh mungkin.
- Fitur yang ingin direkam telah ditentukan.
- Skenario capture dapat direproduksi.
- Kondisi awal diketahui.
- Tool capture tersedia.
- Tidak ada informasi sensitif yang ikut terekam.
- Format dan orientasi output sesuai kebutuhan konten.

Jika salah satu prasyarat penting belum terpenuhi, agent harus mencatatnya dan menyesuaikan rencana.

### 4.2 Capture scenario

Untuk setiap fitur, buat skenario singkat.

```text
CAPTURE SCENARIO

Feature:
Purpose:
Project Revision:
Runtime Environment:
Initial State:
Actions:
Expected Behavior:
Observed Behavior:
Required Shots:
Failure Conditions:
Evidence Needed:
```

`Expected Behavior` adalah hasil yang diharapkan. `Observed Behavior` hanya boleh diisi setelah pengamatan aktual.

Jangan menyalin hasil yang diharapkan ke kolom hasil aktual.

### 4.3 Capture execution

1. Jalankan build atau runtime yang sesuai dengan prosedur proyek.
2. Pastikan fitur yang akan direkam dapat diakses.
3. Mulai dari kondisi awal yang diketahui.
4. Jalankan urutan interaksi yang direncanakan.
5. Ambil capture.
6. Periksa apakah hasilnya lengkap dan dapat digunakan.
7. Ulangi jika terjadi kegagalan teknis yang dapat diperbaiki tanpa mengubah source.
8. Catat keterbatasan dan kegagalan yang terlihat.

Agent tidak boleh memodifikasi source code hanya agar capture berhasil. Jika fitur gagal, catat kegagalan dan eskalasikan kepada developer.

### 4.4 Jika capture tidak tersedia

Jika agent tidak dapat menjalankan aplikasi, mengakses perangkat, atau merekam layar:

- Jangan mengklaim telah mengambil capture.
- Jangan membuat ulang tampilan lalu menyebutnya screenshot aktual.
- Cari bukti yang memang tersedia dan dapat diidentifikasi.
- Buat capture plan untuk eksekusi oleh pihak yang memiliki akses.
- Tandai status sebagai `BLOCKED` atau `NEEDS_CAPTURE`.

AI-generated visuals dapat menjadi alternatif untuk konten konseptual, tetapi bukan pengganti bukti aktual.

---

## 5. SHOT PLANNING

Setiap produksi video harus mempunyai daftar shot yang mendukung cerita.

Contoh struktur untuk demo fitur:

| Shot | Isi | Fungsi |
|---|---|---|
| 1 | Tampilan awal produk | Memberikan konteks |
| 2 | Objek atau fitur utama | Menunjukkan fokus |
| 3 | Interaksi pengguna | Memperlihatkan perilaku |
| 4 | Respons atau hasil | Menunjukkan outcome |
| 5 | Detail pendukung | Memperjelas mekanisme |
| 6 | Tampilan akhir | Memberikan penutup |

Daftar ini merupakan contoh, bukan urutan wajib.

Untuk video yang singkat, cukup gunakan shot yang diperlukan untuk memahami cerita. Jangan memperpanjang video dengan footage yang tidak menambah nilai.

### Shot list template

```text
VIDEO TITLE:

Core Message:
Primary Audience:
Target Platform:
Video Mode:
Source Revision:

Shot 1:
- Visual:
- Action:
- Purpose:
- Evidence Requirement:

Shot 2:
- Visual:
- Action:
- Purpose:
- Evidence Requirement:

Shot 3:
- Visual:
- Action:
- Purpose:
- Evidence Requirement:

Required Audio:
Required Text:
Transition Notes:
Known Limitations:
```

---

## 6. GAMEPLAY FOOTAGE RULES

Untuk produk game, footage harus menunjukkan pengalaman bermain yang benar-benar dapat diamati.

Prioritaskan:
- Gerakan karakter yang relevan.
- Respons kontrol.
- Interaksi dengan environment.
- Combat atau gameplay loop.
- Animasi dan VFX.
- Perubahan keadaan permainan.
- UI yang mendukung pemahaman.
- Momen yang memperlihatkan karakter produk.

Hindari mengandalkan cinematic camera atau efek visual saja jika cerita yang ingin disampaikan sebenarnya mengenai kualitas gameplay.

### Gameplay verification

Sebelum menyatakan footage mendemonstrasikan suatu mekanik, periksa:

1. Apakah input yang dilakukan benar-benar menghasilkan respons?
2. Apakah mekanik terlihat jelas?
3. Apakah hasil akhirnya sesuai dengan klaim?
4. Apakah video menunjukkan konteks yang cukup?
5. Apakah ada bagian yang disembunyikan sehingga mengubah makna?
6. Apakah footage berasal dari produk aktual atau merupakan animasi konseptual?

Jika sebuah mekanik hanya terlihat dalam satu skenario, batasi klaim pada skenario tersebut.

### Camera and framing

Agent boleh merencanakan:
- Sudut pandang.
- Jarak kamera.
- Gerakan kamera.
- Fokus objek.
- Komposisi foreground dan background.
- Keterbacaan UI.
- Ruang untuk teks.

Namun, jangan mengubah konfigurasi produk hanya untuk menghasilkan footage tanpa otorisasi. Jika kamera produk tidak dapat diubah, gunakan capture yang tersedia atau ajukan kebutuhan tersebut kepada developer.

---

## 7. IMAGE GENERATION WORKFLOW

Image generation digunakan ketika visual sintetis memang membantu tujuan konten.

### Tahap 1 — Define purpose

Tentukan apakah gambar akan digunakan untuk:
- Concept art.
- Moodboard.
- Thumbnail.
- Campaign visual.
- Ilustrasi teknologi.
- Background visual.
- Diagram konseptual.
- Visual pendukung konten produk.

Jangan menggunakan image generation untuk menggantikan screenshot yang seharusnya membuktikan fitur aktual.

### Tahap 2 — Define visual constraints

Creative brief harus menentukan:

- Subject.
- Action atau keadaan.
- Environment.
- Composition.
- Camera angle.
- Lighting.
- Color direction.
- Material dan texture.
- Mood.
- Focal point.
- Negative constraints.
- Output aspect ratio.
- Ruang untuk headline jika dibutuhkan.
- Elemen brand yang memang sudah tersedia dan disetujui.

Tidak semua brief membutuhkan semua elemen. Gunakan detail yang relevan terhadap hasil.

### Tahap 3 — Reference and consistency

Jika tool mendukung penggunaan reference image, gunakan reference yang memang diizinkan untuk mempertahankan konsistensi.

Pastikan:
- Asset tidak memiliki hak penggunaan yang belum jelas.
- Reference tidak mengandung informasi rahasia.
- Desain yang dihasilkan tidak disalahartikan sebagai produk aktual.
- Logo dan identitas resmi tidak dibuat ulang secara tidak akurat.

Jangan mengasumsikan generator dapat mempertahankan karakter, logo, typography, atau UI secara presisi. Periksa hasil aktual.

### Tahap 4 — Quality control

Evaluasi:
- Apakah subjek sesuai brief?
- Apakah komposisi membantu cerita?
- Apakah terdapat artefak visual?
- Apakah perspektif dan proporsi masuk akal?
- Apakah teks yang dihasilkan dapat dipercaya dan terbaca?
- Apakah visual terlalu generik?
- Apakah hasilnya menyerupai screenshot produk sehingga berpotensi menyesatkan?
- Apakah gambar cocok untuk platform tujuan?

Jika hasil tidak memenuhi tujuan, perbaiki brief atau ulangi generasi. Jangan menyatakan hasil sukses hanya karena gambar berhasil dibuat.

---

## 8. VIDEO GENERATION WORKFLOW

Video generation dapat digunakan untuk visual konseptual atau materi kreatif ketika sesuai dengan tujuan.

### Sebelum generasi

Tentukan:
- Apakah video bersifat konseptual atau berdasarkan footage aktual.
- Tujuan utama.
- Durasi target.
- Subject dan action.
- Environment.
- Gerakan kamera.
- Arah visual.
- Transisi.
- Aspect ratio.
- Hubungan dengan asset sebelumnya.
- Hal-hal yang tidak boleh berubah.

### Setelah generasi

Periksa:
- Konsistensi subjek antar-frame.
- Gerakan dan transisi.
- Deformasi karakter atau objek.
- Artefak visual.
- Perubahan bentuk yang tidak diinginkan.
- Konsistensi pencahayaan.
- Keterbacaan elemen penting.
- Kesesuaian dengan brief.
- Potensi kesalahpahaman mengenai keadaan produk aktual.

Video yang tampak sinematik tidak otomatis sesuai dengan identitas produk.

Jika video generation menghasilkan perilaku yang tidak konsisten atau objek berubah bentuk, jangan menutupi masalah itu hanya dengan mengklaim video sudah layak dipublikasikan.

### Generated video is not gameplay evidence

Jika footage dibuat oleh AI, labeli sebagai visual konseptual sesuai konteks.

Jangan mengklaim:
- Gameplay sudah tersedia.
- Animasi sudah berjalan di engine.
- Fitur sudah selesai.
- Efek sudah diterapkan pada build aktual.

Klaim tersebut membutuhkan bukti terpisah dari produk yang benar-benar berjalan.

---

## 9. STORYBOARD AND EDITING

Sebelum mengedit video atau menyusun rangkaian visual, tentukan struktur cerita.

Contoh:

`Hook → Context → Demonstration → Result → Conclusion`

Untuk konten edukasi:

`Question → Explanation → Example → Takeaway`

Untuk perbandingan:

`Baseline → Change → Comparable Result → Interpretation`

### Editing rules

Editing harus meningkatkan pemahaman.

Boleh digunakan:
- Subtitle.
- Headline.
- Callout.
- Zoom untuk detail.
- Crop.
- Transisi yang mendukung urutan cerita.
- Musik atau sound design yang sesuai.
- Identitas visual brand yang telah disetujui.

Perlu kehati-hatian:
- Slow motion yang mengubah persepsi kecepatan.
- Pemotongan yang menghilangkan langkah penting.
- Penggabungan beberapa percobaan menjadi satu rangkaian tanpa penjelasan.
- Penambahan efek yang memberi kesan fitur tersedia di produk.
- Penggunaan footage dari revisi yang berbeda seolah-olah satu build yang sama.

Jika editing mengubah konteks yang penting, berikan penjelasan yang sesuai atau gunakan materi lain.

---

## 10. VISUAL BRAND CONSISTENCY

Sebelum membuat aturan visual permanen, kumpulkan referensi brand yang benar-benar disetujui.

Periksa jika tersedia:
- Logo resmi.
- Website.
- Warna brand.
- Typography.
- Banner atau campaign sebelumnya.
- Template publikasi.
- Asset produk.
- Pedoman penggunaan logo.

Jangan mengarang brand guideline lalu memperlakukannya sebagai standar resmi.

Jika guideline belum tersedia, agent boleh mengusulkan arah visual sementara. Setiap usulan harus ditandai sebagai `PROPOSED`, bukan `APPROVED`.

### Visual consistency checklist

- Logo benar dan tidak terdistorsi.
- Typography terbaca.
- Warna mendukung identitas yang disetujui.
- Hierarki visual jelas.
- Produk tetap menjadi fokus ketika tujuan konten adalah demonstrasi produk.
- Teks tidak menutupi informasi penting.
- Komposisi sesuai format platform.
- Tidak ada elemen dekoratif yang mengganggu pesan.
- Visual tidak menjanjikan kemampuan yang belum tersedia.

Konsistensi bukan berarti semua konten harus terlihat identik. Variasi dapat digunakan selama identitas utama tetap dapat dikenali.

---

## 11. MOBILE-FIRST LEGIBILITY

Jika konten ditujukan untuk feed yang banyak dikonsumsi melalui perangkat mobile, lakukan pemeriksaan pada ukuran tampilan kecil jika kemampuan preview tersedia.

Periksa:
- Apakah headline masih terbaca?
- Apakah subtext terlalu kecil?
- Apakah objek utama mudah dikenali?
- Apakah UI produk dapat dipahami?
- Apakah informasi penting terpotong?
- Apakah subtitle memiliki kontras yang cukup?
- Apakah komposisi tetap efektif pada crop platform?

Jangan mengandalkan preview desktop saja jika target distribusi utamanya adalah mobile.

Jika preview pada perangkat target tidak tersedia, tandai sebagai pemeriksaan yang belum dilakukan.

---

## 12. QUALITY GATES

Setiap asset harus melewati gate yang sesuai sebelum masuk ke paket publikasi.

### Gate A — Source Integrity

- Sumber asset diketahui.
- Status actual atau generated ditetapkan.
- Revisi produk dicatat jika relevan.
- Hak penggunaan telah dipertimbangkan.
- Tidak ada data sensitif yang terekspos.

### Gate B — Technical Quality

- File dapat dibuka.
- Resolusi dan format sesuai kebutuhan.
- Tidak ada kerusakan file.
- Tidak ada artefak yang mengganggu.
- Audio dan video berjalan dengan baik jika relevan.

### Gate C — Communication Quality

- Pesan utama dapat dipahami.
- Fokus visual jelas.
- Teks terbaca.
- Editing mendukung cerita.
- Tidak ada elemen yang menimbulkan interpretasi keliru.

### Gate D — Claim Integrity

- Visual mendukung klaim.
- Tidak ada fitur konseptual yang disajikan sebagai fitur aktual.
- Batasan penting tidak disembunyikan.
- Konteks tidak dipotong secara menyesatkan.

### Gate E — Platform Readiness

- Format sesuai kanal.
- Aspect ratio sesuai kebutuhan.
- Subtitle dan audio sesuai.
- CTA dan caption cocok dengan visual.
- Tidak ada masalah hak penggunaan atau kebijakan yang belum diselesaikan.

Jika satu gate yang kritis gagal, jangan tandai asset sebagai `READY TO PUBLISH`.

---

## 13. ASSET NAMING AND VERSIONING

Gunakan pola nama file yang mudah dilacak.

Contoh:

```text
[project]_[story-id]_[asset-type]_[revision]_[version].[ext]
```

Contoh ilustratif:

```text
game_alpha_story-014_gameplay_commit-a1b2c3_v01.mp4
studio_story-021_concept_v02.png
product_story-032_ui-capture_v01.png
```

Nama contoh tidak menunjukkan proyek atau revisi yang benar-benar ada.

Aturan:
- Jangan menimpa asset sumber.
- Simpan versi final secara terpisah dari draft.
- Catat sumber dan perubahan yang dilakukan.
- Gunakan identifier yang benar-benar tersedia.
- Jangan menyertakan credentials atau informasi rahasia dalam nama file.

Lokasi penyimpanan harus mengikuti workspace yang diizinkan. Jangan membuat atau mengubah file di repository produk hanya untuk mengatur asset konten.

---

## 14. CREATIVE BRIEF TEMPLATE

```text
ASSET ID:

Story ID:
Project:
Product Revision:
Asset Type:
Production Mode:

Primary Objective:
Target Audience:
Platform:

Core Message:
Visual Purpose:
Primary Subject:
Action / State:
Environment:
Composition:
Camera / Motion:
Lighting:
Color Direction:
Typography:
Brand Assets:
Aspect Ratio:

Source Material:
Generation Requirements:
Required Editing:
Negative Constraints:

Claims Supported:
Claims Not Supported:
Known Limitations:

Quality Check:
Approval Status:
```

Brief harus cukup spesifik agar dapat dieksekusi oleh tools yang tersedia, tetapi tidak boleh memasukkan detail yang belum diketahui seolah-olah sudah pasti.

---

## 15. FAILURE HANDLING

Jika produksi gagal, buat laporan singkat.

```text
PRODUCTION FAILURE REPORT

Asset ID:
Production Mode:
Expected Result:
Actual Result:
Tool / Environment:
Evidence:
Failure Category:
Impact:
What Remains Usable:
What Remains Unknown:
Next Safe Action:
```

Kategori yang dapat digunakan:
- `CAPTURE_UNAVAILABLE`
- `WRONG_PRODUCT_VERSION`
- `MISSING_ASSET`
- `GENERATION_FAILURE`
- `VISUAL_ARTIFACT`
- `TEXT_RENDERING_FAILURE`
- `FORMAT_MISMATCH`
- `SOURCE_UNCLEAR`
- `CLAIM_INTEGRITY_FAILURE`
- `PERMISSION_BLOCKED`
- `UNKNOWN_CAUSE`

Jangan mengubah status menjadi berhasil tanpa memeriksa hasil aktual.

Jika visual yang dibutuhkan tidak dapat dibuat, usulkan alternatif yang masih sesuai dengan klaim dan tujuan konten.

---

## 16. LEARNING LOOP

Setelah produksi, catat pelajaran yang dapat membantu pekerjaan berikutnya.

Contoh:
- Jenis screenshot yang paling mudah memperlihatkan perubahan UI.
- Sudut kamera yang memperjelas mekanik.
- Jenis prompt yang menghasilkan visual konseptual lebih konsisten.
- Masalah umum ketika teks dihasilkan oleh image generation.
- Tahap editing yang paling sering membutuhkan revisi.
- Format visual yang lebih mudah dipahami audiens, jika didukung data.

Pisahkan:
- Pengamatan.
- Interpretasi.
- Hipotesis.
- Aturan yang sudah teruji.

Jangan menjadikan satu kegagalan generasi sebagai aturan universal tentang semua model atau tools.

Pelajaran permanen harus mempunyai konteks, bukti, dan batas penerapan.

---

## 17. ACCEPTANCE CRITERIA

Kemampuan produksi visual baru dapat dianggap terverifikasi ketika agent mampu:

- Memilih mode produksi yang sesuai.
- Menghasilkan capture plan yang dapat dijalankan.
- Menghubungkan asset aktual dengan produk dan revisi yang tepat jika tersedia.
- Membedakan screenshot aktual dari visual AI.
- Membuat storyboard berdasarkan tujuan konten.
- Memeriksa kualitas teknis dan komunikasi.
- Menjaga batas klaim saat editing.
- Menolak asset yang menyesatkan atau mengandung informasi sensitif.
- Melaporkan keterbatasan tools secara jujur.
- Menyimpan asset dan metadata tanpa mengubah source repository.
- Menghasilkan paket visual yang siap diperiksa sebelum publikasi.

Jika tools tertentu tidak tersedia, kemampuan yang bergantung pada tools tersebut harus ditandai `BLOCKED` atau `NOT TESTED`.

---

## 18. FINAL RULE

Sebelum menyerahkan visual kepada Content Strategy Agent, tanyakan:

1. Apa yang sebenarnya ditunjukkan?
2. Apakah sumbernya dapat diidentifikasi?
3. Apakah visual sesuai dengan status produk?
4. Apakah editing mengubah makna?
5. Apakah audiens akan memahami pesan yang dimaksud?
6. Apakah asset aman digunakan secara publik?
7. Apakah visual ini menambah nilai dibandingkan asset yang sudah ada?

**Visual yang bagus menarik perhatian. Visual yang akurat membangun kepercayaan. Produksi Zyvro Labs harus mengejar keduanya.**

