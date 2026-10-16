<!--  -->
|       Elemen        |                  LAB_UC03_Ajukan_peminjaman                   |
|---------------------|---------------------------------------------------------------|
|       Tujuan        |       Menghasilkan pengajuan peminjaman yang tersimpan        |
|        Aktor        |                        utama Mahasiswa                        |
|       Sumber        |                 kebutuhan LAB-R03 dan LAB-R04                 |
|       Pemicu        |         Mahasiswa memilih fungsi pengajuan peminjaman         |
|      Prasyarat      |    Mahasiswa telah terautentikasi; data peralatan tersedia    |
|Pascakondisi_berhasil|Pengajuan tersimpan dengan nomor dan status Menunggu keputusan |
| Pascakondisi_gagal  |       Tidak ada pengajuan baru yang berhasil tersimpan        |
|       Include       |                LAB-UC04 — Periksa ketersediaan                |
|      Extension      |        point Bukti pengajuan tersedia, pada langkah 6         |
|       Extend        |            LAB-UC05 jika [mahasiswa memilih cetak]            |
