# Navigator Perlindungan

Alat kerja riset aksi yang menyertai naskah "Terinklusi tetapi Tidak Terlindungi: Zonasi Spasial Ketergantungan pada
Kanal Keuangan tanpa Jaring Pengaman di 33 Provinsi Indonesia" (LPS Call for Research 2026, Kategori Umum, Topik 8).
Situs ini bukan publikasi resmi LPS; kartu aksi, indikator, dan jadwal ronde adalah usulan penelitian.

## Apa yang ada di dalamnya

1. **Diagnosis**: peta zonasi 33 provinsi dengan saringan wilayah kerja (kantor pusat, KP LPS I, II, III).
2. **Kartu aksi provinsi**: diagnosis, paket program R1–R5 yang berlaku, sasaran terukur, mitra dan kanal, rencana
   90 hari yang dapat dicentang; dapat dicetak, disalin, atau disimpan sebagai JSON.
3. **Siklus riset aksi**: usulan ronde 0–3 dan papan catatan lapangan (rencana, tindakan, amati, refleksi) per
   Kantor Perwakilan, dengan ekspor dan impor JSON.
4. **Simulator**: S-A dan S-B dengan asumsi φ, LGD, dan TWP90 yang dapat digeser; proyeksi RETT per provinsi.
5. **Pemantauan**: papan skor per wilayah kerja, tabel 33 provinsi, dan indikator keberhasilan yang diusulkan.
6. **Cek perlindungan**: pemeriksa produk (tiga lapis), pesan kunci untuk penyuluh, kuis lima pertanyaan.
7. **Agar berdampak**: ide sekarang, tiga bulan, dan dua belas bulan.

Situs satu halaman tanpa pustaka luar; huruf dari Google Fonts. Catatan lapangan dan centang rencana disimpan di
`localStorage` peramban pengguna, tidak dikirim ke mana pun. Untuk papan catatan bersama antar-pengguna diperlukan
penyimpanan di luar situs statis (misalnya formulir daring atau isu di repositori ini).

## Data

- `data/indikator_provinsi.csv` (33 baris): Indikator pemantauan 33 provinsi (zona, RETT, TWP90, kegagalan BPR, sasaran program). Kolom: `kode`, `provinsi`, `kantor_perwakilan_LPS`, `zona`, `zona_inti`, `bendera_Lapis2`, `RETT_2025Q2`, `RETT_2021Q1`, `RETT_rata2`, `TWP90_2025Q2`, `TWP90_rata2`, `kegagalan_BPR_per100kantor`, `rekening_peminjam_aktif`, `rekening_per_1000_dewasa`, `outstanding_LPBBTI_Rpmiliar`, `outstanding_lewat90hari_Rpmiliar`, `Lapis1_RpT`, `Lapis2_RpT`, `Lapis3_RpT`, `LISA_2025Q2`.
- `data/zonasi_provinsi.csv` (33 baris): Zonasi 33 provinsi, zona inti, bendera Lapis 2, Kantor Perwakilan. Kolom: `kode`, `provinsi`, `zona`, `nama_zona`, `zona_inti`, `RETT_rata2`, `TWP90_rata2`, `bendera_sumbu_Lapis2`, `kantor_perwakilan_LPS`.
- `data/rett_provinsi_triwulan.csv` (594 baris): RETT per provinsi dan triwulan, 2021Q1–2025Q2. Kolom: `kode`, `provinsi`, `periode`, `RETT_persen`.
- `data/nasional_triwulan.csv` (18 baris): Rata-rata, sebaran, dan Moran's I RETT per triwulan. Kolom: `periode`, `RETT_rata2_provinsi`, `simpangan_baku`, `koefisien_variasi`, `Moran_I_kNN5`, `p_permutasi`.

Ambang zonasi: RETT 11,16% dan TWP90 1,777% (median panel). Angka SNLIK 2026 yang dipakai:
inklusi 93,61%, literasi 69,57%, tahu simpanannya dijamin 62,51%, mengenal LPS 46,31% (OJK, 2026).

## Sumber

OJK (Statistik Perbankan Indonesia, Statistik LPBBTI termasuk Tabel 12, Statistik Lembaga Pembiayaan, siaran pers
SNLIK 2026), LPS (Distribusi Simpanan Bank Umum, Laporan Kelembagaan), BPS (PDRB, IPM, Susenas, Sakernas), dan
Bank Indonesia (SPIP); seluruhnya diolah. Hak atas data sumber tetap pada instansi penerbitnya.

## Menerbitkan dengan GitHub Pages

1. Buat repositori baru di GitHub, lalu unggah seluruh isi folder ini (termasuk `.nojekyll` dan folder `data/`).
2. Buka **Settings → Pages**, pilih **Deploy from a branch**, cabang `main`, folder `/ (root)`, lalu **Save**.
3. Situs tersedia di `https://<nama-pengguna>.github.io/<nama-repositori>/` dalam satu sampai dua menit.

Halaman memuat `<meta name="robots" content="noindex, nofollow">`; hapus baris itu bila situs ingin muncul di mesin
pencari. Untuk memperbarui angka setelah data baru terbit: jalankan ulang `analisis.py`, lalu `bangun_aksi.py`.
