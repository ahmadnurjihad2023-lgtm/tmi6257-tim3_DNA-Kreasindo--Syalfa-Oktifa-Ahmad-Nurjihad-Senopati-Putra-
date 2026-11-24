# Proyek Akhir ERP TMI6257 — Kelompok 3 DNA Kreasiindo

README ini merangkum dasar studi kasus, rancangan simulasi, dan status implementasi proyek ERP Kelompok 3. **Data wawancara** menggambarkan informasi yang dilaporkan tentang perusahaan. **Usulan simulasi** adalah keputusan kerja tim untuk membuat alur ERP dapat diuji; usulan tersebut bukan klaim tentang transaksi atau kondisi aktual DNA Kreasiindo. Status Odoo dan analitik hanya dinyatakan selesai setelah ada bukti dari sistem.

## 1 Profil dan masalah bisnis

DNA Kreasiindo merupakan usaha kerajinan kayu dalam studi kasus proyek. Berdasarkan ringkasan wawancara semester sebelumnya dan bahan yang telah dibahas:

- Bahan baku utama adalah kayu jati Belanda yang berasal dari pallet bekas packing.
- Pemasok utama disebut berada di Karawang dan pemasok cadangan di Tangerang. Nama badan usaha tidak tercatat dalam bahan yang tersedia.
- Pembelian kayu disebut sekitar 20 pack pada kondisi normal dan 50 pack saat ramai. Isi/volume satu pack belum diketahui.
- Produksi rata-rata yang dilaporkan sekitar 500 pcs per bulan.
- Pasar mencakup dalam negeri dan luar negeri. Singapura dan Malaysia disebut sebagai pasar luar negeri melalui Shopee.
- Produk yang dibahas: Rak Toples Kayu, Rak Meja Kayu, Rak Multifungsi, Kotak Jimpitan Kayu, dan Nomor Meja Kayu Custom.

**Masalah yang dimodelkan dalam proyek:** informasi pembelian dalam pack belum langsung dapat dibandingkan dengan kebutuhan kayu dalam proses produksi; stok bahan, barang dalam proses, produk jadi, dan pesanan penjualan perlu ditelusuri dalam satu alur. Sistem simulasi ditujukan untuk menghubungkan pembelian, persediaan, manufaktur, dan penjualan serta menyediakan ringkasan analitik. Ini adalah fokus pemodelan proyek, bukan diagnosis terukur atas seluruh operasi perusahaan.

**Batas bukti:** sumber yang tersedia berupa ringkasan wawancara semester sebelumnya dan pembahasan studi kasus. Tidak ada observasi baru, data historis rinci, maupun pengukuran waktu dan material aktual yang disertakan.

## 2 Master data dan BoM

### Master data yang digunakan untuk simulasi

| Jenis | Kode dan nama | Status/keterangan |
|---|---|---|
| Bahan baku | `RM-001` — Kayu Jati Belanda Pallet | Jenis bahan dari wawancara. Satuan beli perusahaan disebut pack; konversi ke volume untuk BoM belum dikonfirmasi. |
| Bahan penolong | `BP-001` Lem Kayu; `BP-002` Sekrup Kayu; `BP-003` Amplas Kayu; `BP-004` Bahan Finishing Kayu | Usulan komponen simulasi yang perlu diverifikasi terhadap proses aktual; jangan diklaim sebagai bahan yang dikonfirmasi wawancara. |
| Produk jadi | `FG-001` Rak Toples Kayu; `FG-002` Rak Meja Kayu; `FG-003` Rak Multifungsi; `FG-004` Kotak Jimpitan Kayu; `FG-005` Nomor Meja Kayu Custom | Daftar produk studi kasus/tim. Satuan pencatatan simulasi: unit. |
| Pemasok | `SUP-001` Pemasok Karawang; `SUP-002` Pemasok Tangerang | Label sementara berdasar lokasi yang disebut. Karawang adalah pemasok utama dan Tangerang pemasok cadangan menurut ringkasan wawancara; nama legal pemasok belum tersedia. |
| Pelanggan | `CUS-001` Pelanggan Domestik; `CUS-002` Pelanggan Ekspor | Mitra simulasi untuk mewakili dua segmen pasar, bukan identitas pelanggan aktual. Negara ekspor dapat dipilih Singapura untuk satu skenario karena Singapura disebut dalam ringkasan pasar. |

### BoM untuk demonstrasi

Dua produk dipilih untuk BoM agar lingkup manufaktur tetap terkelola dan sesuai kebutuhan minimum proyek yang tercatat dalam ringkasan tugas. Dimensi berikut merupakan **usulan teknis sementara** untuk simulasi; bukan hasil pengukuran produk aktual. Ukuran alas Rak Toples 280 × 95 mm pernah disebut sebagai acuan katalog, sedangkan komponen lain adalah rancangan tim.

| Produk | Komponen per satu unit (rancangan) | Volume geometris kayu per unit |
|---|---|---:|
| `FG-001` Rak Toples Kayu | Alas 280×95×10 mm (1); sisi panjang 280×60×10 mm (2); sisi pendek 95×60×10 mm (2); tiang pegangan 20×20×220 mm (2); palang 240×20×20 mm (1) | 0,000988 m³ |
| `FG-005` Nomor Meja Kayu Custom | Alas bawah 120×50×20 mm (1); papan nomor 150×50×10 mm (1); penyangga segitiga siku-siku 40×30×10 mm (2) | 0,000207 m³ |

Angka volume adalah hasil geometri komponen rancangan per unit. Angka belum mencakup kehilangan saat pemotongan, penyerutan, atau pengamplasan. BoM Nomor Meja memakai satu ukuran standar agar dapat disimulasikan; variasi ukuran pesanan custom belum dimodelkan. Lem, sekrup, amplas, dan finishing belum diberi kuantitas BoM karena takaran aktual belum tersedia.

**Keputusan satuan untuk simulasi:** BoM memakai m³ agar kebutuhan kayu bisa dihitung dari dimensi. Sebelum PO dapat mengalir ke MO secara konsisten, tim harus menetapkan isi pack berdasarkan pengukuran atau memakai konversi simulasi yang dinyatakan terbuka. Jika harus memakai asumsi sementara, gunakan **1 pack = 0,05 m³** hanya sebagai parameter demonstrasi, beri label asumsi di master data, dan ganti dengan hasil ukur sebelum menyimpulkan efisiensi atau biaya aktual. Jangan menyajikan konversi ini sebagai fakta perusahaan.

Operasi manufaktur yang diusulkan: pemotongan → penyerutan → perakitan → pengamplasan → finishing. Waktu baku tiap operasi belum diketahui dan tidak diperlukan untuk klaim kapasitas aktual.