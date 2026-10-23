Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus digunakan untuk membantu proses peminjaman dan pengembalian peralatan laboratorium. Mahasiswa dan dosen dapat melihat ketersediaan peralatan serta mengajukan peminjaman. Petugas laboratorium bertugas mengelola data peralatan, memproses keputusan peminjaman, serta mencatat pengembalian dan kondisi peralatan. Kepala laboratorium dapat melihat laporan peminjaman.
Pada Pertemuan 4, sistem dikembangkan dengan menambahkan aktor umum Peminjam, aktor khusus Dosen, tiga use case khusus untuk pengelolaan data peralatan, use case pencatatan pengembalian, dan pemeriksaan kondisi peralatan. Dua collaboration juga ditambahkan untuk merealisasikan proses pengajuan peminjaman dan pencatatan pengembalian.
<!-- Batas Sistem  Dan Aturan -->
C. Batas sistem dan aturan
1. Sistem mencatat dan menyediakan informasi. Perpindahan fisik peralatan tidak terjadi di dalam perangkat lunak.
2. Pengguna telah terautentikasi dan mempunyai hak akses sesuai perannya.
3. Pengembalian hanya dapat dicatat jika status peminjaman adalah Dipinjam.
4. Peminjaman berstatus Menunggu Keputusan atau Ditolak tidak dapat dicatat pengembaliannya.
5. Kondisi peralatan saat dikembalikan terdiri dari Baik, Rusak Ringan, atau Rusak Berat.
6. Data peralatan hanya dapat dihapus apabila peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif.
<!-- Aktor umum -->
A|        ktor        |Kedudukan|  Tujuan  |terhadap |                                                                                 Sistem                                                                                 |
|--------------------|---------|----------|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      Peminjam      |  Umum   |(general),|  baru   |                                 pada Pertemuan 4 Peran umum bagi peminjam peralatan. Mewariskan fungsinya kepada Mahasiswa dan Dosen.                                  |
|     Mahasiswa      | Khusus  |   dari   |Peminjam,|tetap dari Pertemuan 3 Melihat ketersediaan dan mengajukan peminjaman melalui fungsi yang diwarisi dari Peminjam, serta mencetak bukti pengajuan sebagai fungsi khusus. |
|       Dosen        | Khusus  |   dari   |Peminjam,|                            baru pada Pertemuan 4 Melihat ketersediaan dan mengajukan peminjaman melalui fungsi yang diwarisi dari Peminjam.                            |
|Petugas_Laboratorium|  Tetap  |   dari   |Pertemuan|                                    3 Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan.                                    |
|Kepala_Laboratorium |  Tetap  |   dari   |Pertemuan|                                                                     3 Melihat laporan peminjaman.                                                                      |
<!-- Use Case -->
Berikut tabel yang sudah dirapikan menjadi satu tabel utuh.

| ID       | Nama Use Case                | Peran dalam Model                                                                   | Sumber Kebutuhan          |
| -------- | ---------------------------- | ----------------------------------------------------------------------------------- | ------------------------- |
| LAB-UC01 | Lihat Ketersediaan Peralatan | Fungsi umum Peminjam                                                                | LAB-R01, LAB-R07          |
| LAB-UC02 | Kelola Data Peralatan        | Use case umum untuk pengelolaan data peralatan                                      | LAB-R02, LAB-R08          |
| LAB-UC03 | Ajukan Peminjaman            | Fungsi umum Peminjam; menyertakan pemeriksaan ketersediaan; direalisasikan LAB-CO01 | LAB-R03, LAB-R07, LAB-R11 |
| LAB-UC04 | Periksa Ketersediaan         | Perilaku yang disertakan oleh LAB-UC03                                              | LAB-R03                   |
| LAB-UC05 | Cetak Bukti Pengajuan        | Fungsi khusus Mahasiswa; perluasan bersyarat dari LAB-UC03                          | LAB-R04                   |
| LAB-UC06 | Proses Keputusan Peminjaman  | Fungsi Petugas Laboratorium                                                         | LAB-R05                   |
| LAB-UC07 | Lihat Laporan Peminjaman     | Fungsi Kepala Laboratorium                                                          | LAB-R06                   |
| LAB-UC08 | Tambah Data Peralatan        | Use case khusus dari LAB-UC02                                                       | LAB-R08                   |
| LAB-UC09 | Ubah Data Peralatan          | Use case khusus dari LAB-UC02                                                       | LAB-R08                   |
| LAB-UC10 | Hapus Data Peralatan         | Use case khusus dari LAB-UC02                                                       | LAB-R08                   |
| LAB-UC11 | Catat Pengembalian Peralatan | Fungsi Petugas Laboratorium; menyertakan LAB-UC12; direalisasikan LAB-CO02          | LAB-R09, LAB-R10, LAB-R11 |
| LAB-UC12 | Periksa Kondisi Peralatan    | Perilaku yang disertakan oleh LAB-UC11                                              | LAB-R10                   |