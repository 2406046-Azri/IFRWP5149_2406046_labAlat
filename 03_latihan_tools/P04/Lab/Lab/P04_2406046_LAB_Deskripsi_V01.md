| No. | Sumber                                  | Hubungan       | Tujuan                                  |
| --- | --------------------------------------- | -------------- | --------------------------------------- |
| 1   | Peminjam                                | Association    | LAB-UC01 – Lihat Ketersediaan Peralatan |
| 2   | Peminjam                                | Association    | LAB-UC03 – Ajukan Peminjaman            |
| 3   | Mahasiswa                               | Association    | LAB-UC05 – Cetak Bukti Pengajuan        |
| 4   | Mahasiswa                               | Generalization | Peminjam                                |
| 5   | Dosen                                   | Generalization | Peminjam                                |
| 6   | Petugas Laboratorium                    | Association    | LAB-UC02 – Kelola Data Peralatan        |
| 7   | Petugas Laboratorium                    | Association    | LAB-UC06 – Proses Keputusan Peminjaman  |
| 8   | Petugas Laboratorium                    | Association    | LAB-UC11 – Catat Pengembalian Peralatan |
| 9   | Kepala Laboratorium                     | Association    | LAB-UC07 – Lihat Laporan Peminjaman     |
| 10  | LAB-UC03 – Ajukan Peminjaman            | `«include»`    | LAB-UC04 – Periksa Ketersediaan         |
| 11  | LAB-UC05 – Cetak Bukti Pengajuan        | `«extend»`     | LAB-UC03 – Ajukan Peminjaman            |
| 12  | LAB-UC08 – Tambah Data Peralatan        | Generalization | LAB-UC02 – Kelola Data Peralatan        |
| 13  | LAB-UC09 – Ubah Data Peralatan          | Generalization | LAB-UC02 – Kelola Data Peralatan        |
| 14  | LAB-UC10 – Hapus Data Peralatan         | Generalization | LAB-UC02 – Kelola Data Peralatan        |
| 15  | LAB-UC11 – Catat Pengembalian Peralatan | `«include»`    | LAB-UC12 – Periksa Kondisi Peralatan    |
| 16  | LAB-CO01 – Collaboration                | Realization    | LAB-UC03 – Ajukan Peminjaman            |
| 17  | LAB-CO02 – Collaboration                | Realization    | LAB-UC11 – Catat Pengembalian Peralatan |