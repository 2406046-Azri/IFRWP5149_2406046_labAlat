1. Deskripsi Use Case
A. SIA-UC08 — Input Nilai Mata Kuliah
- Aktor: Dosen
- Tujuan: Memasukkan nilai mahasiswa untuk mata kuliah yang diajarkan.
- Prasyarat: Dosen sudah login dan memiliki hak menginput nilai pada mata kuliah tersebut.
- Pemicu: Dosen memilih menu Input Nilai Mata Kuliah.
- Kondisi akhir: Nilai berhasil disimpan oleh sistem.
Alur utama:
1. Dosen membuka menu Input Nilai Mata Kuliah.
2. Sistem menampilkan mata kuliah yang diajarkan oleh dosen.
3. Dosen memilih mata kuliah.
4. Sistem menampilkan daftar mahasiswa pada mata kuliah tersebut.
5. Dosen memasukkan nilai mahasiswa.
6. Sistem memeriksa kelengkapan dan validitas nilai.
7. Dosen menyimpan nilai.
8. Sistem menyimpan nilai dan menampilkan pemberitahuan berhasil.
Alur alternatif:
- Jika dosen tidak mengajar mata kuliah tersebut, sistem menolak akses input nilai.
- Jika nilai tidak valid atau belum lengkap, sistem meminta dosen memperbaikinya.
- Jika penyimpanan gagal, sistem menampilkan pemberitahuan bahwa nilai belum berhasil disimpan.
B. SIA-UC09 — Lihat Kartu Hasil Studi (KHS)
- Aktor: Mahasiswa
- Tujuan: Melihat hasil studi pada semester tertentu.
- Prasyarat: Mahasiswa sudah login.
- Pemicu: Mahasiswa memilih menu Kartu Hasil Studi.
- Kondisi akhir: KHS ditampilkan jika nilai untuk semester tersebut sudah dipublikasikan.
Alur utama:
1. Mahasiswa membuka menu Kartu Hasil Studi.
2. Sistem menampilkan pilihan semester.
3. Mahasiswa memilih semester yang ingin dilihat.
4. Sistem memeriksa ketersediaan nilai yang sudah dipublikasikan.
5. Sistem menampilkan KHS sesuai semester yang dipilih.
Alur alternatif:
- Jika nilai belum dipublikasikan, sistem memberi informasi bahwa KHS belum tersedia sebagai hasil resmi.
- Jika data KHS gagal dimuat, sistem menampilkan pesan kesalahan.
C. SIA-UC10 — Kelola Data Mahasiswa
- Aktor: Admin Akademik
- Tujuan: Mengelola data mahasiswa.
- Prasyarat: Admin Akademik sudah login dan memiliki hak akses pengelolaan data.
- Alur: Admin memilih pengelolaan data mahasiswa, kemudian menambahkan, mengubah, atau menghapus data sesuai kebutuhan.
Use case ini memiliki tiga use case turunan:
- SIA-UC11 — Tambah Data Mahasiswa: Admin memasukkan data mahasiswa baru dan menyimpannya.
- SIA-UC12 — Ubah Data Mahasiswa: Admin memilih data mahasiswa, memperbarui informasi, lalu menyimpan perubahan.
- SIA-UC13 — Hapus Data Mahasiswa: Admin memilih data yang akan dihapus dan mengonfirmasi penghapusan. Penghapusan harus mengikuti aturan sistem akademik.