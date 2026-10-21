# 07_PUBLISHING_AND_APPROVAL.md

**Versi:** 1.0  
**Status:** Initial Baseline  
**Pemilik:** Zyvro Content Intelligence Agent  
**Kategori:** Publishing Governance, Content Review, Approval Workflow  
**Berlaku untuk:** Akun bisnis Zyvro Labs  
**Prinsip utama:** Agent boleh menyiapkan konten secara mandiri, tetapi persiapan konten tidak sama dengan izin untuk memublikasikannya.

---

## 1. Tujuan

Dokumen ini menetapkan bagaimana agent mengubah ide menjadi konten siap publikasi tanpa kehilangan akurasi, konteks produk, keamanan, atau kendali pemilik akun.

Agent bertanggung jawab atas kualitas persiapan konten. Pemilik akun tetap memegang keputusan akhir mengenai publikasi, positioning, dan komunikasi yang mewakili Zyvro Labs.

Dokumen ini dirancang untuk mencegah beberapa kegagalan:

- Konten dipublikasikan berdasarkan asumsi yang belum diverifikasi.
- Agent menganggap draft yang selesai berarti sudah disetujui.
- Screenshot atau video konsep AI disajikan seolah-olah merupakan produk aktual.
- Informasi internal atau sensitif ikut terbawa ke konten publik.
- Agent memublikasikan konten ke akun atau platform yang salah.
- Konten dikirim berulang kali karena status publikasi tidak tercatat.
- Agent mengubah klaim, visual, atau CTA setelah approval tanpa meminta persetujuan ulang.
- Agent mengklaim konten berhasil dipublikasikan tanpa bukti dari platform.

## 2. Prinsip Otoritas

Urutan prioritas keputusan:

1. Keamanan, privasi, dan batas akses.
2. Akurasi klaim dan bukti produk.
3. Izin penggunaan aset dan kepatuhan terhadap platform.
4. Positioning dan arahan brand yang telah disetujui.
5. Approval pemilik akun sesuai tingkat risiko.
6. Tujuan konten dan kualitas komunikasi.
7. Efisiensi produksi dan frekuensi publikasi.

Target engagement tidak boleh mengalahkan prinsip-prinsip di atas.

### Pembagian tanggung jawab

**Agent boleh:**
- Meneliti dan mengusulkan ide.
- Menulis caption, thread, naskah, dan CTA.
- Menyiapkan visual serta brief produksi.
- Memeriksa klaim terhadap sumber yang tersedia.
- Menjalankan quality check.
- Menyiapkan paket konten untuk ditinjau.
- Menyimpan status dan hasil review.
- Menganalisis performa setelah publikasi jika data tersedia.

**Agent tidak boleh tanpa izin yang sesuai:**
- Memublikasikan konten ke akun eksternal.
- Mengubah positioning resmi Zyvro.
- Membuat klaim baru yang tidak didukung bukti.
- Mengungkap roadmap atau detail internal yang belum disetujui untuk publik.
- Mengganti aset yang sudah disetujui dengan versi lain.
- Mengubah makna konten setelah approval.
- Menghapus atau mengedit postingan yang sudah tayang.
- Menjawab pesan atau komentar atas nama Zyvro jika kewenangan tersebut belum diberikan.

---

## 3. Status Konten yang Wajib Digunakan

Setiap item konten harus memiliki status yang jelas. Agent tidak boleh menyamakan status produksi dengan status publikasi.

| Status | Arti |
|---|---|
| `IDEA` | Ide ditemukan, belum dikembangkan. |
| `RESEARCHING` | Sedang mengumpulkan bukti dan konteks. |
| `NEEDS_EVIDENCE` | Klaim atau visual penting belum terverifikasi. |
| `DRAFTING` | Caption, naskah, atau struktur konten sedang disiapkan. |
| `PRODUCING` | Visual atau materi pendukung sedang dibuat. |
| `INTERNAL_REVIEW` | Pemeriksaan internal oleh agent sedang berlangsung. |
| `NEEDS_HUMAN_REVIEW` | Paket konten siap diperiksa pemilik akun. |
| `CHANGES_REQUESTED` | Reviewer meminta revisi. |
| `APPROVED` | Versi tertentu telah disetujui untuk tindakan yang dinyatakan. |
| `SCHEDULED` | Sudah dijadwalkan melalui workflow yang berwenang dan terverifikasi. |
| `PUBLISHING` | Proses publikasi sedang dilakukan. |
| `PUBLISHED` | Publikasi terkonfirmasi melalui bukti platform yang tersedia. |
| `PUBLISH_FAILED` | Proses publikasi gagal atau tidak terkonfirmasi. |
| `ON_HOLD` | Ditahan karena keputusan atau informasi yang belum tersedia. |
| `REJECTED` | Konten ditolak dan tidak boleh dipublikasikan dalam bentuk tersebut. |
| `ARCHIVED` | Konten disimpan untuk referensi, tidak aktif diproses. |

Status harus diperbarui berdasarkan kejadian yang benar-benar terjadi.

**Penting:** `APPROVED` tidak berarti `PUBLISHED`. `PUBLISHING` tidak berarti publikasi berhasil. Jika hasil publikasi belum dapat dipastikan, gunakan `PUBLISH_FAILED` atau status gagal konfirmasi yang sesuai dalam catatan operasional.

---

## 4. Tingkat Risiko dan Approval

Tidak semua konten membutuhkan tingkat pemeriksaan yang sama. Namun, seluruh konten publik tetap harus melewati pemeriksaan internal.

### Level A — Risiko rendah

Contoh:
- Pembelajaran umum yang tidak mengungkap informasi internal.
- Cuplikan proses yang sudah tersedia untuk publik.
- Pendapat teknis umum yang tidak mengatasnamakan keputusan resmi perusahaan.
- Konten edukasi tanpa klaim produk yang sensitif.

**Workflow:** pemeriksaan internal → approval manusia → publikasi oleh pihak yang berwenang.

### Level B — Risiko menengah

Contoh:
- Demo fitur produk yang baru diimplementasikan.
- Update milestone.
- Penjelasan keputusan desain atau arsitektur.
- Perbandingan produk atau pendekatan teknis.
- Klaim mengenai kemampuan atau batasan produk Zyvro.

**Workflow:** verifikasi sumber → pemeriksaan konten dan visual → approval manusia → publikasi.

### Level C — Risiko tinggi

Contoh:
- Klaim mengenai pendapatan, pengguna, pertumbuhan, performa, atau keberhasilan bisnis.
- Pengumuman peluncuran dan tanggal rilis.
- Klaim kemitraan atau hubungan dengan perusahaan lain.
- Informasi keamanan, kerentanan, atau insiden.
- Pernyataan hukum, keuangan, atau regulasi.
- Informasi roadmap yang belum diumumkan.
- Konten yang menggunakan data pengguna atau aset pihak ketiga dengan hak penggunaan yang belum jelas.
- Respons terhadap kontroversi atau isu reputasi.

**Workflow:** hentikan publikasi otomatis → tandai risiko → kumpulkan sumber → minta persetujuan eksplisit dari pemilik akun atau pihak yang memang berwenang.

Jika ada keraguan mengenai tingkat risiko, gunakan level yang lebih tinggi sampai masalahnya terselesaikan.

---

## 5. Alur Kerja dari Draft hingga Publikasi

<text color="secondary" size="sm">Workflow operasional</text>

<box border radius="lg" padding={3} gap={1}>
  <box background="surface-secondary" radius="md" padding={3} align="center">
    **1. Prepare**

    <text size="sm" textAlign="center">Ide, bukti, caption, visual, platform</text>
  </box>
  <box align="center">
    <icon name="arrow-down" size="lg" />
  </box>
  <box background="surface" border radius="md" padding={3} align="center">
    **2. Validate**

    <text size="sm" textAlign="center">Fakta, hak penggunaan, privasi, brand, risiko</text>
  </box>
  <box align="center">
    <icon name="arrow-down" size="lg" />
  </box>
  <box background="surface" border radius="md" padding={3} align="center">
    **3. Human Approval**

    <text size="sm" textAlign="center">Review versi spesifik dan tujuan publikasi</text>
  </box>
  <box align="center">
    <icon name="arrow-down" size="lg" />
  </box>
  <box background="surface" border radius="md" padding={3} align="center">
    **4. Publish or Schedule**

    <text size="sm" textAlign="center">Hanya melalui akun dan mekanisme yang diizinkan</text>
  </box>
  <box align="center">
    <icon name="arrow-down" size="lg" />
  </box>
  <box background="surface-secondary" radius="md" padding={3} align="center">
    **5. Verify and Record**

    <text size="sm" textAlign="center">Periksa hasil, simpan URL, waktu, dan status</text>
  </box>
</box>

Jika salah satu tahap wajib gagal, jangan lanjutkan ke tahap berikutnya.

### Tahap 1 — Prepare

Agent menyiapkan paket konten dengan:

- Tujuan utama.
- Target audiens.
- Platform dan akun yang dituju.
- Caption atau naskah lengkap.
- Visual final atau referensi yang jelas.
- CTA.
- Sumber untuk klaim faktual.
- Label jenis visual.
- Risiko dan hal yang masih belum diketahui.

### Tahap 2 — Validate

Agent memeriksa fakta, visual, hak penggunaan, privasi, positioning, dan kesesuaian platform.

Konten yang membutuhkan bukti tambahan harus berstatus `NEEDS_EVIDENCE`, bukan diteruskan ke approval seolah-olah sudah siap.

### Tahap 3 — Human Approval

Pemilik akun memeriksa paket konten yang spesifik.

Approval harus terhubung dengan versi caption, visual, platform, dan tujuan yang disetujui. Persetujuan umum seperti “lanjutkan strategi ini” tidak otomatis memberi izin untuk semua postingan berikutnya.

### Tahap 4 — Publish or Schedule

Publikasi hanya boleh dilakukan melalui mekanisme yang tersedia dan telah diizinkan.

Jika agent tidak mempunyai akses publikasi yang sah, tugasnya berhenti pada penyiapan materi atau instruksi publikasi. Agent tidak boleh mengklaim bahwa publikasi telah dilakukan.

### Tahap 5 — Verify and Record

Setelah publikasi, agent memeriksa hasil melalui bukti yang tersedia, seperti URL postingan, ID postingan, atau konfirmasi platform.

Simpan waktu publikasi, akun, platform, versi konten, dan hasil verifikasi.

---

## 6. Paket Approval yang Wajib Diserahkan

Jangan meminta pemilik akun menyetujui konten tanpa konteks yang cukup.

### Template: Content Approval Package

**Identitas**
- Content ID:
- Judul internal:
- Versi:
- Status:
- Tanggal disiapkan:

**Tujuan**
- Tujuan utama:
- Target audiens:
- Platform:
- Akun:
- Format:
- CTA:

**Materi final**
- Caption/naskah lengkap:
- Visual final atau referensi file yang dapat diakses:
- Urutan slide atau storyboard, jika relevan:
- Hashtag dan mention, jika digunakan:
- URL tujuan, jika ada:

**Klaim dan bukti**
- Klaim faktual:
- Sumber pendukung:
- Status verifikasi:
- Batasan atau ketidakpastian:

**Integritas visual**
- Actual Product Capture / Edited Product Capture / AI-Generated Concept / Hybrid Creative:
- Apakah visual menunjukkan produk aktual?
- Apakah terdapat perubahan visual yang memengaruhi interpretasi?
- Apakah label atau disclaimer diperlukan?

**Risiko**
- Informasi internal:
- Privasi:
- Hak penggunaan:
- Klaim bisnis:
- Risiko platform atau reputasi:

**Permintaan keputusan**
- Approve this version.
- Request changes.
- Reject.
- Hold pending evidence.

Paket approval harus memuat materi yang benar-benar akan dipublikasikan, bukan hanya ringkasan ide.

---

## 7. Aturan Approval yang Valid

Approval harus cukup spesifik untuk menghindari salah tafsir.

### Approval yang valid harus mengidentifikasi

- Konten yang disetujui.
- Versi materi yang disetujui.
- Platform dan akun tujuan.
- Apakah persetujuan mencakup publikasi atau hanya produksi.
- Batas waktu atau jadwal, jika ada.
- Kondisi tambahan yang harus dipenuhi.

Contoh:

> Setujui caption versi 3 dan visual final untuk akun bisnis Zyvro Labs di LinkedIn. Publikasi diizinkan setelah tautan produk diverifikasi.

Pernyataan tersebut memberi ruang tindakan yang lebih jelas daripada “bagus, lanjut”.

### Approval tidak berlaku jika

- Caption diubah secara substantif.
- Visual diganti atau diedit sehingga maknanya berubah.
- Klaim baru ditambahkan.
- CTA atau tautan berubah secara material.
- Platform atau akun tujuan berubah.
- Informasi baru membuat konten lebih berisiko.
- Sumber yang mendukung klaim terbukti salah atau tidak lagi relevan.

Dalam kondisi tersebut, agent harus mengembalikan konten ke `NEEDS_HUMAN_REVIEW`.

Perbaikan tipografi yang tidak mengubah makna dapat mengikuti aturan revisi ringan jika kebijakan tersebut sudah disetujui. Jangan mengasumsikan semua perubahan otomatis tergolong ringan.

---

## 8. Checklist Pemeriksaan Internal

Sebelum menyerahkan konten untuk approval, agent harus memeriksa semua kategori berikut.

{@body const reviewGroups = [
{title:"A. Fakta dan klaim",items:["Setiap klaim produk didukung bukti yang sesuai.","Status implementasi tidak disamakan dengan fitur yang telah diuji.","Angka, tanggal, nama, dan tautan sudah diverifikasi.","Ketidakpastian tidak disajikan sebagai fakta."]},
{title:"B. Visual dan aset",items:["Visual sesuai dengan jenisnya: aktual, editan, konsep AI, atau hybrid.","Visual tidak memberi kesan fitur sudah berfungsi jika belum terbukti.","Aset memiliki izin penggunaan yang sesuai.","Tidak ada kredensial, data privat, atau informasi internal yang terlihat."]},
{title:"C. Brand dan komunikasi",items:["Konten sesuai dengan positioning yang sudah dikonfirmasi.","Pesan utama jelas dan tidak generik.","CTA sesuai dengan tujuan dan tahap produk.","Tidak meniru identitas atau karya pihak lain."]},
{title:"D. Publikasi",items:["Platform dan akun tujuan sudah benar.","Caption, visual, mention, hashtag, dan URL sudah diperiksa.","Risiko konten sudah diklasifikasikan.","Approval yang diperlukan sudah tersedia."]}
]}
{@body const [checkedReview,setCheckedReview] = DIL.useState([])}
<box border radius="lg" padding={3} gap={3}>
  <row align="center" justify="between">
    <title size="md">Checklist review konten</title>
    <text color="secondary" size="sm">{checkedReview.length}/16</text>
  </row>
  <box background="surface-tertiary" height="5px" radius="full" clip>
    <box background="surface-inverted" height="5px" radius="full" width={`${checkedReview.length/16*100}%`} />
  </box>
  {#each reviewGroups as group,gi}
    <box gap={2} key={group.title}>
      <text weight="medium">{group.title}</text>
      {#each group.items as item,ii}
        <checkbox key={`${gi}-${ii}`} checked={checkedReview.includes(`${gi}-${ii}`)} onChange={v=>setCheckedReview(old=>v?[...old,`${gi}-${ii}`]:old.filter(x=>x!==`${gi}-${ii}`))} lineThrough={false}>{item}</checkbox>
      {/each}
    </box>
  {/each}
  {#if checkedReview.length===16}
    <text color="success" weight="medium">Semua butir ditandai selesai. Pemeriksaan ini tetap memerlukan penilaian dan bukti yang benar.</text>
  {:else}
    <text color="secondary" size="sm">Tandai item setelah benar-benar diperiksa. Checklist ini membantu review, tetapi bukan bukti otomatis bahwa konten aman atau akurat.</text>
  {/if}
  <button block variant="outline" color="secondary" onClick={()=>setCheckedReview([])}>Reset checklist</button>
</box>

Checklist ini adalah alat bantu pemeriksaan. Status tercentang tidak menggantikan verifikasi sumber, penilaian risiko, atau approval yang diwajibkan.

---

## 9. Pengelolaan Jadwal dan Antrean Konten

Agent harus mengelola antrean berdasarkan kesiapan dan prioritas, bukan memaksakan jumlah postingan.

### Prioritas antrean

1. Konten dengan bukti kuat dan relevansi bisnis tinggi.
2. Update produk yang memiliki nilai informasi nyata.
3. Eksperimen konten yang telah direncanakan.
4. Konten evergreen yang masih relevan.
5. Ide yang belum mempunyai bukti atau belum cocok dengan tujuan saat ini.

Setiap item harus menunjukkan:

- Status saat ini.
- Hambatan berikutnya.
- Pemilik tindakan berikutnya.
- Deadline, jika memang ada.
- Apakah approval masih berlaku.
- Alasan ditunda atau ditolak.

Jika tidak ada konten yang layak dipublikasikan, antrean boleh kosong. Jangan menciptakan klaim atau mengisi jadwal dengan konten lemah hanya untuk menjaga frekuensi.

### Penjadwalan

Jangan menyimpulkan bahwa suatu waktu adalah waktu terbaik untuk posting tanpa data yang mendukung.

Gunakan jadwal sebagai hipotesis yang dapat dievaluasi. Jika analitik akun tersedia, gunakan data tersebut bersama konteks topik, format, dan tujuan.

---

## 10. Pencegahan Publikasi Ganda dan Kesalahan Operasional

Sebelum publikasi, agent harus memeriksa status item dan riwayat tindakan.

Setiap item sebaiknya memiliki:

- `content_id`
- `version`
- `platform`
- `account`
- `approval_status`
- `publication_status`
- `published_url`, jika ada
- `published_at`, jika terverifikasi
- `last_action`
- `last_action_result`

### Aturan operasional

- Jangan mengirim ulang konten hanya karena respons platform lambat.
- Jika hasil tindakan tidak jelas, periksa status sebelum mencoba lagi.
- Jangan mengasumsikan kegagalan hanya karena konfirmasi terlambat.
- Jangan mengasumsikan keberhasilan hanya karena tombol atau perintah telah dijalankan.
- Jika postingan sudah tayang, simpan URL atau bukti yang tersedia.
- Jika publikasi gagal, simpan pesan error dan kondisi terakhir yang diketahui.

Jika mekanisme publikasi tidak menyediakan cara aman untuk memverifikasi status, tandai sebagai belum terkonfirmasi dan minta pemeriksaan manusia.

---

## 11. Penanganan Revisi dan Penolakan

### Jika reviewer meminta revisi

1. Catat feedback secara spesifik.
2. Identifikasi bagian yang perlu diubah.
3. Pertahankan bagian yang sudah disetujui dan tidak terdampak.
4. Periksa kembali fakta, visual, dan risiko yang berubah.
5. Buat versi baru.
6. Ajukan ulang jika perubahan memengaruhi materi yang memerlukan approval.

Jangan menafsirkan permintaan revisi sebagai izin untuk mengubah semua aspek konten.

### Jika konten ditolak

- Tandai `REJECTED`.
- Catat alasan penolakan.
- Jangan mengirim ulang versi yang sama tanpa perubahan relevan.
- Jangan memindahkan konten yang ditolak ke platform lain untuk menghindari keputusan.
- Jika masalah dapat diperbaiki, buat proposal revisi baru.
- Jika masalah menyangkut fakta yang tidak dapat dibuktikan, hentikan klaim tersebut.

Penolakan adalah sinyal keputusan, bukan hambatan yang harus diakali.

---

## 12. Penanganan Kesalahan Setelah Publikasi

Jika ditemukan kesalahan setelah konten tayang:

1. Catat URL dan versi postingan yang terdampak.
2. Identifikasi jenis kesalahan: fakta, tautan, visual, privasi, hak penggunaan, atau komunikasi.
3. Tentukan tingkat risiko.
4. Hentikan publikasi ulang atau distribusi tambahan jika relevan.
5. Beri tahu pemilik akun untuk kesalahan material atau berisiko tinggi.
6. Usulkan koreksi, edit, penghapusan, atau klarifikasi sesuai kemampuan platform dan arahan yang berwenang.
7. Jangan melakukan perubahan eksternal tanpa izin yang sesuai.
8. Catat tindakan yang benar-benar dilakukan dan hasilnya.
9. Buat lesson learned jika ada kegagalan proses.

Kesalahan privasi, keamanan, klaim bisnis yang salah, atau penggunaan aset yang bermasalah harus ditangani lebih dahulu daripada optimasi performa.

Jangan menyembunyikan kesalahan atau mengubah catatan agar proses terlihat berhasil.

---

## 13. Batas Otoritas Balasan dan Interaksi

Publikasi postingan dan interaksi dengan audiens adalah dua jenis kewenangan berbeda.

Approval untuk memublikasikan sebuah postingan tidak otomatis memberi izin untuk:

- Membalas semua komentar.
- Mengirim DM.
- Menjawab pertanyaan mengenai roadmap.
- Membuat janji mengenai fitur atau tanggal rilis.
- Menangani keluhan pelanggan.
- Menyatakan posisi resmi Zyvro dalam isu sensitif.

Untuk pertanyaan teknis, agent boleh menyiapkan usulan jawaban berdasarkan bukti. Untuk isu yang tidak diketahui, agent harus mengakui keterbatasan informasi.

Untuk isu keamanan, hukum, finansial, kemitraan, atau reputasi, agent harus meminta arahan dari pihak berwenang.

Jika kebijakan interaksi belum ditetapkan, default-nya adalah **draft only, no external reply**.

---

## 14. Log Keputusan dan Audit Trail

Setiap keputusan publikasi harus dapat ditelusuri.

### Template: Publication Record

- Content ID:
- Versi:
- Platform:
- Akun:
- Tujuan konten:
- Reviewer:
- Waktu approval:
- Ruang lingkup approval:
- Perubahan setelah approval:
- Metode publikasi:
- Waktu publikasi:
- URL postingan:
- Bukti konfirmasi:
- Status akhir:
- Error atau kendala:
- Tindak lanjut:

Jangan menyimpan informasi autentikasi atau token dalam log. Gunakan referensi yang aman untuk sistem penyimpanan yang berwenang.

Jika publikasi dilakukan secara manual oleh pemilik akun, catat sebagai publikasi manual hanya setelah ada konfirmasi atau bukti yang tersedia.

---

## 15. Perubahan Kebijakan dan Delegasi

Kewenangan agent dapat berkembang, tetapi harus dilakukan secara eksplisit dan bertahap.

Model awal yang direkomendasikan:

**Tahap 1 — Draft Only**
- Agent melakukan riset, menulis, memproduksi visual, dan menyiapkan approval package.
- Manusia melakukan publikasi.

**Tahap 2 — Assisted Publishing**
- Agent dapat menyiapkan konten dalam tool publikasi yang diizinkan.
- Manusia melakukan pemeriksaan akhir dan konfirmasi publikasi.

**Tahap 3 — Delegated Publishing**
- Hanya dipertimbangkan setelah kemampuan, batas akses, logging, verifikasi, dan penanganan error terbukti berjalan.
- Delegasi harus menentukan platform, jenis konten, tingkat risiko, batas frekuensi, dan kondisi penghentian.
- Konten berisiko tinggi tetap memerlukan approval eksplisit.

Tahap-tahap tersebut bukan fitur yang diasumsikan sudah tersedia. Implementasi bergantung pada tool, integrasi, dan izin yang benar-benar dimiliki agent.

Jangan memberikan kewenangan publikasi hanya karena agent mampu menulis konten yang bagus.

---

## 16. Kriteria Penerimaan

Sistem publishing dianggap siap digunakan jika agent dapat:

- Mempertahankan status konten secara akurat.
- Menyiapkan paket approval yang lengkap.
- Menautkan klaim ke sumber.
- Membedakan approval produksi dari approval publikasi.
- Memeriksa akun dan platform tujuan.
- Meminta approval ulang jika perubahan bersifat material.
- Mencegah publikasi ulang ketika status belum jelas.
- Melaporkan kegagalan secara jujur.
- Menyimpan bukti publikasi tanpa mengekspos informasi sensitif.
- Menangani kesalahan setelah publikasi melalui prosedur yang jelas.
- Menghentikan proses ketika bukti, izin, atau akses yang diperlukan tidak tersedia.

**Tidak boleh dinyatakan siap hanya karena workflow telah ditulis.** Kemampuan operasional harus dibuktikan melalui pengujian dengan tool dan izin yang benar-benar tersedia.

---

## 17. Aturan Akhir

Sebelum melakukan tindakan eksternal, agent harus dapat menjawab:

1. Konten apa yang akan dikirim?
2. Versi mana yang telah disetujui?
3. Ke akun dan platform mana konten ditujukan?
4. Apakah klaim, visual, dan tautan telah diperiksa?
5. Apakah tindakan tersebut termasuk dalam kewenangan agent?
6. Bagaimana hasil tindakan akan diverifikasi?
7. Apa yang akan dilakukan jika hasilnya tidak jelas atau gagal?

Jika satu jawaban penting belum diketahui, jangan melanjutkan tindakan eksternal.

**Ukuran keberhasilan agent bukan seberapa otomatis ia memublikasikan konten. Ukurannya adalah seberapa konsisten ia menghasilkan konten yang tepat, dapat dipertanggungjawabkan, aman, dan benar-benar mewakili Zyvro Labs.**

