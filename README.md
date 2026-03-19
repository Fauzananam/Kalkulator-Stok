# Kalkulator Stok

Alat bantu perhitungan stok harian untuk kebutuhan laporan inventaris restoran. Dibuat berdasarkan pengamatan langsung terhadap alur kerja pencatatan stok di lapangan.

---

## Latar Belakang

Di restoran, pencatatan stok harian tidak selalu bisa diselesaikan dengan satu cara. Ada barang yang jumlah keluarnya sudah diketahui dari sistem kasir, sehingga yang perlu dicari adalah sisa stoknya. Ada juga barang yang lebih praktis dihitung secara fisik terlebih dahulu, sehingga yang perlu dicari justru berapa yang sudah keluar.

Kalkulator ini menangani kedua kondisi tersebut dalam satu halaman.

---

## Cara Kerja

Semua perhitungan menggunakan formula dasar yang sama:

```
Sisa = Stok Awal + Masuk - Keluar - Retur - Rusak
```

Yang berbeda hanya **mana yang diketahui** dan **mana yang dicari**.

### Mode A — Cari Sisa

Digunakan ketika jumlah keluar sudah diketahui, misalnya dari sistem kasir atau catatan penjualan. Pengguna memasukkan semua kolom termasuk jumlah keluar, dan sistem menghitung sisa secara otomatis.

Cocok untuk: Mie, Box, Minuman, dan barang lain yang keluarnya tercatat di sistem.

### Mode B — Cari Keluar

Digunakan ketika pengguna lebih mudah menghitung fisik barang yang tersisa terlebih dahulu. Pengguna memasukkan sisa hasil hitung fisik, dan sistem menghitung berapa yang keluar.

Cocok untuk: Ayam, Sambel, Bumbu, dan bahan baku yang tidak selalu tercatat per unit di kasir.

---

## Kolom yang Tersedia

| Kolom | Keterangan |
|---|---|
| Stok Awal | Jumlah barang sebelum aktivitas hari ini |
| Masuk | Barang yang diterima atau di-restock |
| Keluar | Barang yang terjual atau terpakai |
| Retur | Barang yang dikirim ke outlet lain |
| Rusak | Barang yang tidak bisa dipakai |
| Sisa | Stok tersisa setelah semua aktivitas |

Catatan: kolom Retur di sini bukan berarti barang kembali ke stok, melainkan barang yang dikirimkan ke cabang atau outlet lain, sehingga ikut mengurangi stok.

---

## Fitur Perbandingan Aktual

Setelah hasil sisa diperoleh, pengguna dapat memasukkan jumlah stok aktual hasil hitung fisik. Sistem akan menampilkan apakah kondisi stok:

- Sesuai — angka cocok antara catatan dan fisik
- Plus — fisik lebih banyak dari catatan
- Minus — fisik lebih sedikit dari catatan

Fitur ini membantu mendeteksi selisih antara catatan dan kondisi nyata di lapangan.

---

## Penggunaan

Tidak memerlukan instalasi. Cukup buka file `index.html` di browser, atau akses melalui link deployment jika sudah di-deploy ke Vercel.

Semua perhitungan berjalan di sisi klien. Tidak ada data yang dikirim ke server. Setiap sesi baru dimulai dari angka nol.

---

## Deployment

Proyek ini adalah static site murni (HTML, CSS, JavaScript). Dapat di-deploy langsung ke Vercel tanpa konfigurasi tambahan.

1. Upload folder project ke Vercel
2. Vercel akan mendeteksi otomatis sebagai static site
3. Akses melalui URL yang diberikan, termasuk dari perangkat mobile

---

## Konteks Pengembangan

Alur kerja dan logika perhitungan dalam aplikasi ini disusun berdasarkan pengamatan langsung sebagai karyawan restoran. Kondisi di lapangan menunjukkan bahwa tidak semua barang bisa diperlakukan dengan cara pencatatan yang sama, sehingga dibutuhkan dua pendekatan dalam satu alat yang sama.