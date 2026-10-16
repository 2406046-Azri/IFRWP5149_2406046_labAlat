<!-- 5.1 UC-SIA-01 — Ajukan KRS -->
Bagian	            Deskripsi
ID dan nama	        UC-SIA-01 — Ajukan KRS
Sumber kebutuhan    SIA-R03
Tujuan	            Mahasiswa berhasil mengajukan KRS untuk mendapatkan mata kuliah yang dipilih.
Aktor               utama	Mahasiswa
Aktor               pendukung	Tidak ada aktor pendukung langsung.
Pemicu	            Mahasiswa memilih menu pengajuan KRS.
Prasyarat	        Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia.
Alur utama	        1. Mahasiswa membuka fitur pengajuan KRS. 2. Sistem menampilkan mata kuliah yang tersedia. 3. Mahasiswa memilih mata kuliah. 4. Mahasiswa mengirim pengajuan. 5. Sistem menjalankan UC-SIA-02 Validasi KRS. 6. Jika validasi berhasil, sistem menyimpan pengajuan dengan status menunggu persetujuan dosen wali. 7. Sistem menampilkan konfirmasi   bahwa pengajuan berhasil disimpan. 8. Sistem menyediakan extension point Bukti pengajuan tersedia.
Alur alternatif/pengecualian	A1 — Validasi gagal pada langkah 5: sistem menampilkan kesalahan atau masalah yang ditemukan. Pengajuan belum berhasil tersimpan dan mahasiswa dapat memperbaiki data sebelum mencoba kembali. A2 — Mahasiswa memilih unduh pada langkah 8: jalankan UC-SIA-03 Unduh Bukti Pengajuan KRS.
Pascakondisi berhasil	KRS tersimpan dengan status menunggu persetujuan dosen wali, terlepas dari apakah bukti diunduh.
Pascakondisi gagal	KRS belum berhasil tersimpan jika validasi gagal.
Aturan bisnis/asumsi	Validasi wajib dilakukan. Mengunduh bukti bukan syarat keberhasilan pengajuan. KRS yang tersimpan belum berarti disetujui.

5.2 UC-SIA-02 — Validasi KRS
Bagian	Deskripsi
ID dan nama	UC-SIA-02 — Validasi KRS
Sumber kebutuhan	SIA-R04
Tujuan	Memastikan pengajuan KRS memenuhi pemeriksaan yang ditetapkan skenario.
Aktor utama	Bagian internal proses pengajuan SIA; tidak dimulai langsung oleh aktor manusia.
Aktor pendukung	Mahasiswa sebagai pengaju KRS.
Pemicu	UC-SIA-01 mencapai langkah pengiriman pengajuan.
Prasyarat	Mahasiswa telah mengirim pilihan mata kuliah; data yang dibutuhkan untuk validasi tersedia.
Alur utama	1. Sistem memeriksa kelengkapan data pengajuan. 2. Sistem memeriksa prasyarat setiap mata kuliah yang dipilih. 3. Sistem memeriksa benturan jadwal. 4. Sistem menyatakan validasi berhasil jika seluruh pemeriksaan terpenuhi. 5. Sistem mengembalikan hasil validasi berhasil ke UC-SIA-01.
Alur alternatif/pengecualian	A1: Jika data tidak lengkap, sistem menyatakan validasi gagal. A2: Jika prasyarat mata kuliah tidak terpenuhi, sistem menyatakan validasi gagal. A3: Jika ditemukan benturan jadwal, sistem menyatakan validasi gagal. Untuk seluruh kegagalan, sistem mengembalikan hasil kepada UC-SIA-01 dan pengajuan belum berhasil disimpan.
Pascakondisi berhasil	Hasil validasi menyatakan pengajuan memenuhi pemeriksaan yang ditentukan. UC-SIA-01 dapat melanjutkan proses penyimpanan.
Pascakondisi gagal	Hasil validasi menyatakan pengajuan tidak memenuhi satu atau lebih pemeriksaan; pengajuan belum berhasil tersimpan.
Aturan bisnis/asumsi	Pemeriksaan hanya mencakup kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Tidak ditambahkan aturan batas SKS atau aturan lain yang tidak disebutkan skenario.

5.3 UC-SIA-03 — Unduh Bukti Pengajuan KRS
Bagian	Deskripsi
ID dan nama	UC-SIA-03 — Unduh Bukti Pengajuan KRS
Sumber kebutuhan	SIA-R05
Tujuan	Mahasiswa mendapatkan bukti pengajuan KRS yang telah berhasil disimpan.
Aktor utama	Mahasiswa
Aktor pendukung	Sistem Informasi Akademik
Pemicu	Mahasiswa memilih opsi unduh pada konfirmasi penyimpanan KRS.
Prasyarat	Pengajuan KRS berhasil disimpan dan bukti pengajuan tersedia.
Alur utama	1. Sistem menampilkan konfirmasi penyimpanan. 2. Mahasiswa memilih opsi unduh bukti. 3. Sistem menyediakan bukti pengajuan KRS. 4. Mahasiswa mengunduh bukti tersebut.
Alur alternatif/pengecualian	A1: Mahasiswa tidak memilih opsi unduh. UC-SIA-03 tidak dijalankan dan pengajuan KRS tetap berhasil. A2: Jika bukti tidak dapat disediakan, sistem memberi informasi bahwa bukti belum dapat diunduh; keadaan ini tidak membatalkan pengajuan KRS yang telah tersimpan.
Pascakondisi berhasil	Mahasiswa memperoleh bukti pengajuan KRS.
Pascakondisi gagal	Pengajuan tetap tersimpan, tetapi mahasiswa belum memperoleh bukti.
Aturan bisnis/asumsi	Pengunduhan bersifat opsional. Extension point pada UC-SIA-01 adalah Bukti pengajuan tersedia, dengan kondisi [mahasiswa memilih unduh].

5.4 UC-SIA-04 — Proses Keputusan KRS
Bagian	Deskripsi
ID dan nama	UC-SIA-04 — Proses Keputusan KRS
Sumber kebutuhan	SIA-R06
Tujuan	Dosen wali menetapkan persetujuan atau penolakan atas pengajuan KRS dan memberikan catatan keputusan.
Aktor utama	Dosen Wali
Aktor pendukung	Mahasiswa sebagai pengaju KRS, sebagai pihak yang pengajuannya diproses.
Pemicu	Dosen wali membuka pengajuan KRS yang menunggu keputusan.
Prasyarat	KRS telah berhasil tersimpan dengan status menunggu persetujuan dosen wali; dosen wali telah terautentikasi.
Alur utama	1. Dosen wali membuka daftar pengajuan KRS yang menunggu keputusan. 2. Dosen wali memilih pengajuan yang akan diproses. 3. Sistem menampilkan informasi pengajuan. 4. Dosen wali memilih keputusan setujui atau tolak. 5. Dosen wali mengisi catatan keputusan. 6. Dosen wali menyimpan keputusan. 7. Sistem mencatat keputusan dan catatannya.
Alur alternatif/pengecualian	A1 — Disetujui: sistem mencatat keputusan persetujuan dan catatan yang diberikan. A2 — Ditolak: sistem mencatat keputusan penolakan dan catatan yang diberikan. A3 — Keputusan belum disimpan: status keputusan belum berubah menjadi keputusan final.
Pascakondisi berhasil	Keputusan persetujuan atau penolakan beserta catatannya tercatat pada pengajuan KRS.
Pascakondisi gagal	Keputusan belum tercatat; pengajuan belum memiliki keputusan final dari proses ini.
Aturan bisnis/asumsi	Dosen wali dapat menyetujui atau menolak dan memberikan catatan keputusan. Rincian kewenangan atau kebijakan institusi lain tidak diasumsikan.