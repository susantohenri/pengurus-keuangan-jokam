# Aplikasi KU Jokam 354
https://play.google.com/store/apps/details?id=com.jokam.penguruskeuangan
https://chatgpt.com/c/6acb300e-b6b0-83ec-91cb-9e7733b7499a

Aplikasi Android ringan untuk membantu pencatatan dan pembagian kartu infak, pengelolaan item jatah maupun item isi sendiri, serta rekap realisasi setoran pada proses KU Jokam 354.

> **Status:** Draft spesifikasi awal. Nama aplikasi, stack teknologi, dan detail implementasi belum ditetapkan.

## Tujuan

Membuat proses administrasi KU lebih praktis melalui HP, dengan alur yang mudah dipahami dan sesedikit mungkin langkah manual.

Prinsip utama:

- Fokus khusus pada kebutuhan KU Daerah, KU Desa, dan KU Kelompok dalam konteks Jokam 354.
- Penggunaan individual pada satu perangkat; tidak ada akun atau sinkronisasi antarperangkat.
- Data operasional disimpan di perangkat pengguna.
- Fitur utama dapat digunakan tanpa koneksi internet.
- Implementasi dibuat sederhana, ringan, dan menghindari backend serta dependensi berukuran besar yang tidak diperlukan.
- Tidak menambahkan modul atau konten di luar alur inti KU.

## Fitur

### 1. Pemilihan peran awal

Saat pertama kali membuka aplikasi, pengguna memilih salah satu peran:

- KU Daerah
- KU Desa
- KU Kelompok

Pilihan ini menyesuaikan istilah dan alur kerja yang relevan untuk pengguna. Tidak dibuat modul struktur organisasi terpisah.

### 2. Pengelolaan data unit dan jamaah

- Tambah desa, kelompok, atau jamaah sesuai peran pengguna.
- Pilih kontak dari daftar kontak HP untuk mempercepat input.
- Mendukung pemilihan beberapa kontak sekaligus.
- Sediakan input manual jika kontak tidak digunakan atau tidak tersedia.
- Simpan data yang digunakan aplikasi secara lokal di perangkat.

### 3. Pengelolaan item infak

Dua jenis item:

- **Jatah:** item dengan nominal atau target yang ditentukan dari tingkat atas dan dibagikan ke tingkat di bawahnya.
- **Isi sendiri:** item yang nominalnya ditentukan sendiri oleh jamaah, misalnya ISRUN/persenan.

Pengguna dapat menambah, mengubah, dan menghapus item sesuai kebutuhan periode. Untuk memulai periode baru, item dan pembagian periode sebelumnya dapat disalin agar tidak perlu dibuat ulang.

### 4. Desil kemampuan 1–10

Aplikasi menggunakan istilah **desil** sebagai skala kemampuan internal dari 1 sampai 10 untuk membantu pembagian target kepada desa, kelompok, atau jamaah.

- Nilai kemampuan dapat digunakan dalam perhitungan breakdown otomatis.
- Hasil breakdown ditampilkan sebagai simulasi sebelum diterapkan.
- Pengguna dapat menyesuaikan nominal hasil breakdown secara manual.
- Pembulatan harus ditangani agar jumlah pembagian konsisten dengan target induk.

Istilah ini merupakan terminologi aplikasi dan tidak dimaksudkan sebagai klasifikasi resmi BPS.

### 5. Breakdown otomatis kartu infak

- Bagikan target item jatah ke unit atau jamaah di tingkat bawah.
- Gunakan nilai desil 1–10 sebagai bobot pembagian.
- Tampilkan target awal, hasil breakdown, dan selisih total sebelum disimpan.
- Izinkan penyesuaian manual bila hasil otomatis perlu diubah.
- Item isi sendiri tidak diberi nominal wajib otomatis seperti item jatah.

### 6. Kartu infak

- Buat dan tampilkan kartu infak per jamaah.
- Bagikan kartu melalui fitur berbagi Android.
- Bagikan kartu sebagai gambar.
- Unduh atau buat PDF untuk satu jamaah, beberapa jamaah terpilih, atau semua jamaah.
- Sediakan ukuran kertas **A4** dan **F4**.
- Sediakan pratinjau sebelum file dibagikan atau disimpan.
- Atur layout cetak, margin, dan jumlah kartu per halaman dengan tetap menjaga hasil mudah dibaca.

### 7. Input realisasi setoran

- Catat nominal realisasi untuk item jatah maupun item isi sendiri.
- Nominal realisasi boleh berbeda dari target jatah.
- Perhitungan diperbarui langsung saat nominal dimasukkan atau diubah (*real-time*).
- Sediakan fungsi **Edit** untuk memperbaiki catatan yang salah.
- Gunakan status **Sudah setor** dan **Belum setor**, bukan “lunas” atau “belum lunas”.
- Tidak menyediakan fitur cicilan.

Status setoran menunjukkan apakah setoran telah dicatat; status tersebut tidak dengan sendirinya menyatakan bahwa nominal realisasi sama dengan target.

### 8. Rekap dan pencarian

- Rekap target dan realisasi per item.
- Tampilkan selisih antara target dan realisasi, termasuk kekurangan atau kelebihan.
- Filter jamaah berdasarkan status **Sudah setor** atau **Belum setor**.
- Cari jamaah berdasarkan nama.
- Rekap per periode agar hasil dapat diperiksa dengan cepat.
- Input setoran massal untuk beberapa jamaah tanpa harus membuka setiap kartu satu per satu.

### 9. Backup dan privasi lokal

- Ekspor data ke file cadangan lokal.
- Impor kembali file cadangan yang dibuat aplikasi.
- Pertimbangkan PIN aplikasi untuk membatasi akses dari orang lain yang memakai perangkat yang sama.
- Minta izin kontak hanya ketika pengguna memakai fitur pemilihan kontak.
- Hindari mengumpulkan data harta personal yang tidak diperlukan; nominal item isi sendiri dimasukkan sesuai pilihan pengguna.

Data lokal dapat hilang jika aplikasi dihapus, perangkat rusak, atau data aplikasi dihapus. Pengguna perlu membuat cadangan jika ingin memindahkan atau memulihkan data.

## Alur utama pengguna

1. Buka aplikasi dan pilih peran KU.
2. Tambahkan desa, kelompok, atau jamaah dari kontak maupun input manual.
3. Buat item infak dan tentukan jenisnya: **Jatah** atau **Isi sendiri**.
4. Untuk item jatah, masukkan target dan jalankan breakdown berdasarkan desil.
5. Tinjau hasil breakdown, sesuaikan bila diperlukan, lalu buat kartu infak.
6. Bagikan kartu atau unduh PDF untuk dicetak.
7. Catat realisasi setoran per item.
8. Pantau status Sudah setor/Belum setor serta rekap target dan realisasi.
9. Pada periode berikutnya, salin konfigurasi periode sebelumnya dan sesuaikan seperlunya.

## Prinsip UX

- Prioritaskan tiga pekerjaan utama: **Kartu Infak**, **Input Setoran**, dan **Rekap**.
- Gunakan bahasa singkat dan konsisten.
- Tampilkan total dan selisih secara langsung saat pengguna mengetik nominal.
- Minimalkan perpindahan layar serta input berulang.
- Gunakan konfirmasi sebelum tindakan yang berpotensi menghapus atau mengganti data.
- Berikan keadaan kosong yang jelas untuk pengguna baru.
- Pastikan layout kartu dan PDF terbaca saat dicetak pada A4 maupun F4.

## Batasan teknis dan scope

- Platform: Android.
- Penyimpanan: lokal di perangkat.
- Backend/API: tidak diperlukan.
- Akun/login: tidak diperlukan.
- Sinkronisasi antarperangkat: tidak termasuk scope.
- Internet: tidak dibutuhkan untuk fungsi inti; koneksi mungkin dibutuhkan untuk memuat iklan.
- Dependensi: pilih library seperlunya dan utamakan ukuran aplikasi yang kecil.
- Monetisasi: AdMob, dengan penempatan iklan yang tidak mengganggu input setoran atau tampilan data keuangan.

Integrasi iklan harus mengikuti kebijakan AdMob dan kebijakan privasi yang berlaku. Data operasional KU tidak boleh dikirim ke jaringan iklan sebagai informasi transaksi atau profil keuangan.

## Tidak termasuk scope

- Backend, server, dan sinkronisasi cloud.
- Akun pengguna atau multi-user online.
- Bukti pembayaran atau upload bukti transaksi.
- Fitur cicilan.
- Tombol khusus “Tandai lunas”.
- Status “Lunas/Belum lunas”.
- Modul struktur organisasi yang berdiri sendiri.
- Fitur generik untuk komunitas di luar konteks KU Jokam 354.
- Konten atau modul tambahan yang tidak mendukung kartu infak, setoran, breakdown, atau rekap.

## Kriteria keberhasilan MVP

- Pengguna dapat memulai aplikasi dan memilih peran tanpa membuat akun.
- Pengguna dapat menambah unit/jamaah dengan cepat.
- Pengguna dapat membuat item jatah dan isi sendiri.
- Breakdown desil berjalan otomatis, dapat dipratinjau, dan dapat disesuaikan manual.
- Kartu dapat dibuat, dibagikan, serta diekspor untuk satu atau banyak jamaah pada ukuran A4/F4.
- Nominal realisasi dapat dicatat dan diedit dengan perhitungan real-time.
- Rekap memperlihatkan target, realisasi, selisih, serta status Sudah setor/Belum setor.
- Data tetap tersedia setelah aplikasi ditutup dan dibuka kembali.
- Fungsi inti berjalan tanpa backend dan tanpa koneksi internet.
- Ukuran aplikasi serta jumlah dependensi dijaga seminimal mungkin.

## Keputusan yang belum ditetapkan

- Nama final aplikasi dan nama package Android.
- Stack UI dan format penyimpanan lokal.
- Rumus pembagian desil yang tepat, termasuk aturan pembulatan.
- Format visual kartu infak dan jumlah kartu per halaman.
- Detail format file backup dan format ekspor rekap.
- Bentuk serta penempatan iklan AdMob.

Keputusan tersebut ditetapkan setelah user journey dan wireframe layar disepakati.
