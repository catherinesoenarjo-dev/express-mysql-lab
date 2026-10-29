## LOGBOOK PENGUJIAN & INTEGRITAS KODE

| ID Uji | Fitur / Operasi | Target Endpoint URL | HTTP Method | Skenario Pengujian | Hasil yang Diharapkan | Status | Bukti Tangkapan Layar |
| :--- | :--- | :--- | :---: | :--- | :--- | :---: | :--- |
| **TC-01** | Koneksi Pool | App Startup | - | Server dijalankan pertama kali | Terhubung ke MySQL Pool tanpa error | Pass | [docs/screenshots/01-db-pool-connection.png](https://drive.google.com/file/d/1XMzdezuIo0kuVMOFMSYMIYdxcDAkZikM/view?usp=sharing) |
| **TC-02** | Read (All) | `/produk` | GET | Akses halaman daftar produk | Menampilkan seluruh record tabel MySQL ke antarmuka EJS| Pass | [docs/screenshots/02-read-select-renderer.png](https://drive.google.com/file/d/19hAc_v-bNAIve7ipOewBMbRr8nRRBddQ/view?usp=drive_link) |
| **TC-03** | Create | `/produk/tambah` | POST | Submit formulir produk baru | Data tersimpan di DB, DevTools mencatat 302 Redirect ke `/produk`| Pass | [docs/screenshots/03-create-insert-prg.png](https://drive.google.com/file/d/1ktnLQHZMdsqfCJAEVEMwZ--BisThXcWD/view?usp=drive_link) |
| **TC-04** | Update | `/produk/edit/:id` | POST | Mengubah harga & stok produk | Nilai kolom pada baris MySQL berubah sesuai input baru | Pass | [docs/screenshots/04-update-param-redirect.png](https://drive.google.com/file/d/1KiRc6PvYp1iupc7bsl5sVR4ha8fZ1nmp/view?usp=drive_link) |
| **TC-05** | Delete | `/produk/hapus/:id` | POST | Eksekusi tombol hapus produk | Baris record terhapus dari MySQL dan UI ter-refresh | Pass | [docs/screenshots/05-delete-feedback.png](https://drive.google.com/file/d/1-fRCMQA7FDih1GVt0cqdIHJbJUfyKE7C/view?usp=drive_link) |
| **TC-06** | Keamanan | `/uji-keamanan` | GET | Input `' OR '1'='1` via URL | Prepared Statement memperlakukan input sebagai literal string (No Injection) | Pass | [docs/screenshots/06-sql-injection-mitigation.png](https://drive.google.com/file/d/1cdcj7jEiWEdbsV5ZPbiWT6IqU_I7ORSM/view?usp=drive_link) |
