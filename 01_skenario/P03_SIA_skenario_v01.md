<!-- Deskripsi Skenario -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- Tabel kebutuhan -->
|  ID   |                             Kebutuhan_tugas                              |
|-------|--------------------------------------------------------------------------|
|SIA-R01|                  Mahasiswa dapat melihat jadwal kuliah                   |
|SIA-R02|               Admin akademik dapat mengelola jadwal kuliah               |
|SIA-R03|                      Mahasiswa dapat mengajukan KRS                      |
|SIA-R04|             Sistem memvalidasi KRS sebagai bagian pengajuan              |
|SIA-R05|Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|        Dosen wali dapat memproses persetujuan atau penolakan KRS         |
<!-- batasan sistem dan aturan -->
Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar
tugas.
<!-- Tabel identifikasi aktor -->
|  Aktor  |                                       Tujuan_terhadap_sistem                                        |
|---------|-----------------------------------------------------------------------------------------------------|
|Mahasiswa|      Mengajukan KRS dengan memilih mata kuliah dan mengunduh bukti pengajuan jika memilihnya.       |
|  Dosen  |Wali Memproses pengajuan KRS dengan memberikan persetujuan atau penolakan beserta catatan keputusan. |


<!-- Tabel susunan katalog use case  -->
|   ID    |Use_Case|Nama_fungsi_Aktor_terkait|            Sumber_kebutuhan             |
|---------|--------|-------------------------|-----------------------------------------|
|UC-SIA-01| Ajukan |           KRS           |            Mahasiswa SIA-R03            |
|UC-SIA-02|Validasi|           KRS           |bagian internal proses pengajuan SIA-R04 |
|UC-SIA-03| Unduh  |          Bukti          |     Pengajuan KRS Mahasiswa SIA-R05     |
|UC-SIA-04| Proses |        Keputusan        |         KRS Dosen Wali SIA-R06          |


<!-- relasi  -->
Relasi <<include>>
- Use case dasar: Ajukan KRS.
- Use case yang disertakan: Validasi KRS.
- Sumber kebutuhan: SIA-R03 dan SIA-R04.
- Alasan: Setiap pengajuan KRS harus melalui validasi kelengkapan data, prasyarat mata kuliah, dan benturan jadwal. Validasi merupakan bagian wajib dari pengajuan.
- Arah panah: Ajukan KRS menuju Validasi KRS.
elasi <<extend>>
- Use case dasar: Ajukan KRS.
- Use case tambahan: Unduh Bukti Pengajuan KRS.
- Sumber kebutuhan: SIA-R05.
- Kondisi: [mahasiswa memilih unduh].
- Extension point: Bukti pengajuan tersedia.
- Alasan: Pengajuan tetap berhasil meskipun mahasiswa tidak mengunduh bukti. Pengunduhan hanya dilakukan jika mahasiswa memilihnya setelah pengajuan berhasil disimpan.
- Arah panah: Unduh Bukti Pengajuan KRS menuju Ajukan KRS.