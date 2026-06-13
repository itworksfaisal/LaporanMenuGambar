# LaporanMenuGambar by @amir.faisalj
Skill ini mengotomatisasi laporan Kegiatan Harian SIPGN dari gambar poster menu MBG.  
Alurnya dibuat untuk kerja cepat, presisi, dan minim bolak-balik manual.

## Apa yang Dikerjakan

- Login SIPGN dengan session yang sama
- Cek apakah tanggal laporan sudah ada
- Ambil data menu, gizi, dan tanggal dari poster
- Isi form operasional Ya, Ada Operasional
- Isi rincian penerima sampai Selisih = 0
- Upload foto poster menu
- Simpan dan verifikasi hasil di daftar kegiatan

## Kapan Dipakai

Pakai skill ini saat ada tugas seperti:

- laporan kegiatan harian dari foto
- input menu MBG dari poster
- isi laporan operasional SIPGN
- upload gambar menu lalu simpan

## Input Yang Dibutuhkan

- sipgn.username
- sipgn.password
- tanggal_kegiatan dalam format DD-MM-YYYY
- Foto poster menu harian

## Cara Kerja Singkat

1. Login ke SIPGN.
2. Buka halaman Kegiatan Harian.
3. Cek apakah tanggal sudah terisi.
4. Jika belum ada, buka form baru.
5. Isi tanggal, menu, gizi, tahapan produksi, dan rincian porsi.
6. Upload foto poster.
7. Simpan dengan simpanData(1).
8. Verifikasi baris baru muncul di daftar.

## Hal Yang Dibuat Skill Ini Kuat

- Login SIPGN yang stabil lewat POST /Sign/login
- Pengisian field readonly via JavaScript saat dibutuhkan
- Sinkronisasi Grand Total dan Jumlah Porsi Produksi
- Parsing menu dari gambar tanpa menebak berlebihan
- Verifikasi hasil setelah submit

## Fitur Teknis

- Mendukung input operasional dari poster menu
- Mendukung tahapan produksi default MBG
- Mendukung upload foto laporan
- Menghindari duplikasi tanggal
- Cocok untuk workflow harian yang berulang

## Contoh Prompt

text
Use $menuharianlogingambar to login to SIPGN and fill a daily menu report from a poster image.


## Catatan

Skill ini dibuat untuk workflow yang repetitif dan sensitif terhadap urutan input.  
Kalau SIPGN menolak input, biasanya penyebabnya ada di login session, tanggal yang sudah ada, atau field readonly yang belum diisi dengan cara yang benar.
