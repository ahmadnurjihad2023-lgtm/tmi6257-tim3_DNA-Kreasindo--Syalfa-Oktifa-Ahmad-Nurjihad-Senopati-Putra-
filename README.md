# Proyek Akhir ERP TMI6257 — Kelompok 3 DNA Kreasiindo

## 1. Profil dan Masalah Bisnis
**DNA Kreasiindo** adalah konteks studi kasus proyek akhir ERP TMI6257. Informasi berikut berasal dari rangkuman hasil wawancara semester sebelumnya dan daftar produk studi kasus yang tercatat dalam bahan kerja tim:
- Bahan baku utama yang disebutkan adalah kayu jati Belanda dari pallet bekas packing.
- Pemasok utama berada di Karawang dan pemasok cadangan berada di Tangerang. Nama badan usaha pemasok tidak tersedia pada bahan yang ditinjau.
- Pola pembelian kayu yang disebutkan adalah sekitar 20 pack pada kondisi normal dan 50 pack saat ramai. Isi/volume per pack belum diketahui.
- Produksi rata-rata yang disebutkan sekitar 500 pcs per bulan.
- Pasar mencakup dalam negeri dan luar negeri; Singapura dan Malaysia disebut sebagai pasar luar negeri melalui Shopee.
- Daftar produk yang dibahas: Rak Toples Kayu, Rak Meja Kayu, Rak Multifungsi, Kotak Jimpitan Kayu, dan Nomor Meja Kayu Custom.

### Masalah Bisnis



## 2. Master data dan BoM (tabel ringkas) 
### Master data rancangan

| Jenis | Kode/nama rancangan | Dasar dan status |
|---|---|---|
| Bahan baku | `RM-001` — Kayu Jati Belanda Pallet | Jenis bahan berasal dari wawancara. Satuan pembelian yang disebut adalah pack; konversi pack ke volume belum tersedia. |
| Bahan penolong | `BP-001` Lem Kayu; `BP-002` Sekrup Kayu; `BP-003` Amplas Kayu; `BP-004` Bahan Finishing Kayu | Asumsi simulasi untuk kebutuhan manufaktur; belum dikonfirmasi sebagai bahan aktual perusahaan. |
| Produk jadi | `FG-001` Rak Toples Kayu; `FG-002` Rak Meja Kayu; `FG-003` Rak Multifungsi; `FG-004` Kotak Jimpitan Kayu; `FG-005` Nomor Meja Kayu Custom | Lima produk dari daftar studi kasus/tim. |
| Pemasok | `SUP-001` Supplier Karawang; `SUP-002` Supplier Tangerang | Label simulasi berdasarkan lokasi yang disebut dalam wawancara, bukan nama badan usaha terverifikasi. Karawang disebut pemasok utama; Tangerang pemasok cadangan. |
| Pelanggan | `CUS-001` Pelanggan Domestik; `CUS-002` Pelanggan Ekspor | Nama/identitas simulasi untuk mewakili segmen pasar; bukan pelanggan aktual yang terverifikasi. |

### BoM sementara

Dua BoM yang direncanakan adalah `FG-001` Rak Toples Kayu dan `FG-005` Nomor Meja Kayu Custom. Dimensi dan jumlah komponen di bawah merupakan **rancangan sementara/asumsi teknis**, bukan hasil pengukuran produk aktual. BoM belum boleh dianggap tervalidasi terhadap bahan yang dibeli karena konversi pack dan ukuran kayu masuk belum tersedia.

| Produk | Rancangan komponen per unit | Kebutuhan geometris kayu rancangan |
|---|---|---:|
| Rak Toples Kayu (`FG-001`) | Alas 280×95×10 mm (1); sisi panjang 280×60×10 mm (2); sisi pendek 95×60×10 mm (2); tiang pegangan 20×20×220 mm (2); palang 240×20×20 mm (1) | 0,000988 m³ |
| Nomor Meja Kayu Custom (`FG-005`) | Alas bawah 120×50×20 mm (1); papan nomor 150×50×10 mm (1); penyangga segitiga siku-siku 40×30×10 mm (2) | 0,000207 m³ |

Kebutuhan tersebut adalah volume geometris rancangan per unit, belum termasuk susut pemotongan, penyerutan, atau pengamplasan. Ukuran alas Rak Toples 280×95 mm disebut mengacu pada ukuran katalog yang pernah dibahas; ukuran lainnya tetap rancangan. Produk Nomor Meja dimodelkan sebagai satu ukuran standar simulasi. Bahan penolong belum dihitung ke dalam BoM.

Urutan operasi rancangan: pemotongan → penyerutan → perakitan → penghalusan/pengamplasan → finishing. Waktu standar tiap operasi belum ditetapkan.
