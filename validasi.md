# Validasi Dashboard Excel DNA Kreasindo

- **Tanggal validasi:** 26 November 2026
- **Database:** `dna_kreasindo`
- **Pembaruan Excel:** berhasil melalui **Data → Refresh Semua**

| KPI | Laporan Odoo | Dashboard Excel | Hasil |
|---|---:|---:|---|
| Total pembelian | Rp456.379,35 | Rp456.379 | Cocok; tampilan Excel membulatkan tanpa desimal |
| Total penjualan | Rp209.790 | Rp209.790 | Cocok |
| Nilai persediaan | Rp374.568,43 | Rp374.568,43 | Cocok |

Nilai persediaan pada Odoo juga cocok dengan view database `lapor.v_nilai_persediaan`. Dashboard memuat empat kueri: pembelian pemasok, penjualan bulanan, stok, dan nilai persediaan.

## Bukti

Simpan screenshot laporan Odoo dan dashboard Excel di folder `bukti` dalam folder proyek, lalu cantumkan nama file screenshot di sini.