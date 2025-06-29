# TemuRasa

### Deskripsi Singkat
Temurasa adalah sistem manajemen restoran berbasis Java dengan antarmuka grafis (GUI) yang dirancang khusus untuk mengelola operasional restoran secara efisien dan profesional. Aplikasi ini mengimplementasikan prinsip-prinsip Object-Oriented Programming (OOP) yang solid dan memanfaatkan database SQLite untuk penyimpanan data yang handal dan terstruktur

---

### 👥Anggota Kelompok

- **Marche Gatriani Sude (H071241054)**
- **Shabrina Zahra Ramadhani (H071241045)**
- **Siti Nur Halisa Tahir (H071241086)**

---

###  🍽️ Tema
**Restoran dan Kuliner:** Aplikasi Manajemen Menu dan Proses Makanan dan Minuman

---

### 📋 Fitur Utama dan Tampilan Aplikasi

### 🔐 Login dan Register
<img width="384" alt="image" src="https://github.com/user-attachments/assets/bfb0da3c-23ab-43be-970d-3b3400888bfd" />

1. Admin akan diarahkan login atau register
2. Saat Admin belum punya akun akan diarahkan ke register untuk membuat username dan password baru
3. Saat Admin sudah punya akun akan, admin hanya perlu login saja
   

  ### 💰 Point of Sale (Kasir)
  <img width="533" alt="image" src="https://github.com/user-attachments/assets/0b1255f2-1b1d-4b70-9c13-69853ede43d7" />
  
  1. Input nama customer - Memasukkan identitas pelanggan
  2. Menu Items - Katalog berisi nama dan kategori makanan/minuman
  3. Tabel Orderan Saat Ini - Menampilkan:
       Item yang dipesan
        - Kuantitas
        - Harga per unit
        - Subtotal per item
        - Total keseluruhan harga

  4. Kontrol Pesanan - Tombol manajemen:
     - 🗑️ Hapus Item: Menghapus item tertentu yang dipilih
     - ➖ Kurangkan Item: Mengurangi satu item yang dipilih
     - 🗑️ Hapus Order: Menghapus semua isi pada tabel Orderan Saat Ini
     - ✅ Proses Order: Memproses hasil order ke laporan penjualan


### 📝 Manajemen Menu
<img width="530" alt="image" src="https://github.com/user-attachments/assets/e3cf1a2c-a8fe-41ba-9810-79070e07b6f2" />


1. Menu Items - Database berisi nama, kategori, harga, dan stok
   
2. Tabel Menu Items Details - Menampilkan:
   - Nama item
   - Kategori (Makanan dan Minuman)
   - Harga
   - Stok tersedia

3. Operasi CRUD - Tombol kontrol:
    - ➕ Tambah: Menambahkan nama, kategori, harga, dan stok pada Menu Items
    - ✏️ Update: Memperbarui informasi seperti nama, kategori, harga, dll
    - 🗑️ Hapus: Menghapus item yang dipilih dari tabel Menu Items Details

### 📊 Laporan Penjualan
<img width="529" alt="image" src="https://github.com/user-attachments/assets/0ae8fcbf-3a25-48eb-8091-d064aabff4cd" />

Berisi data lengkap transaksi:
  - ID: Nomor identifikasi transaksi
  - Nama Pelanggan: Identitas customer
  - Tanggal: Waktu transaksi dilakukan
  - Total: Jumlah pembayaran
  - Kasir: Admin yang melayani
    

### 🗄️ Database
Penyimpanan Permanen: Menggunakan SQLite untuk menyimpan data produk dan transaksi secara permanen
Auto-Setup Database: Otomatis membuat tabel-tabel berikut saat aplikasi pertama kali dijalankan jika belum ada:

  - admin - Data pengguna/administrator
  - menu - Data menu makanan dan minuman
  - order - Data transaksi/pesanan
  - orderitem - Detail item dalam setiap pesanan

    
---

### Struktur Folder
```plaintext
📁 temurasa/                         // Main package - Paket utama aplikasi POS
├── 📁 abstracts/                    
│   └── 📄 ShowScene.java           // Kelas abstrak untuk manajemen tampilan/scene UI
├── 📁 database/                    // Data Access Layer - Layer akses data
│   ├── 📄 AdminDao.java            // Data Access Object untuk manajemen admin/user
│   ├── 📄 DatabaseHelper.java      // Helper untuk koneksi dan operasi database SQLite
│   ├── 📄 MenuDAO.java             // Data Access Object untuk operasi CRUD menu makanan
│   ├── 📄 OrderDAO.java            // Data Access Object untuk operasi CRUD pesanan
│         
├── 📁 GUI/                         // Graphical User Interface - Antarmuka pengguna
│   ├── 📄 LoginWindow.java         // Jendela login untuk autentikasi pengguna
│   ├── 📄 MainWindow.java          // Jendela utama aplikasi dengan menu navigasi
│   ├── 📄 MenuManagement.java      // Panel untuk mengelola menu (tambah/edit/hapus item)
│   ├── 📄 PosPanel.java            // Panel kasir untuk input pesanan dan transaksi
│   └── 📄 SalesReportPanel.java    // Panel laporan penjualan dan statistik
├── 📁 models/                      // Data Models - Model data/entitas
│   ├── 📄 BaseModel.java           // Kelas dasar untuk semua model (ID, timestamps)
│   ├── 📄 Menu.java                // Model untuk item menu (nama, harga, kategori)
│   ├── 📄 Order.java               // Model untuk pesanan (tanggal, total, status)
│   ├── 📄 OrderItem.java           // Model untuk item dalam pesanan
│   └── 📄 User.java                // Model untuk pengguna/admin sistem
├── 📁 util/                        // Utility Classes - Kelas utilitas
│   └── 📄 PasswordUtils.java       // Utility untuk hashing dan verifikasi password
├── 📄 Main.java                    // Application entry point - Titik masuk aplikasi
└── 🗄️ temurasa.db                  // SQLite database file - File database SQLite
```

---

### 🧱 Struktur Paket & Kelas

| Paket              | Kelas                            | Deskripsi                                                                 |
|--------------------|----------------------------------|---------------------------------------------------------------------------|
| `abstracts`        | `ShowScene.java`                | Kelas abstrak untuk manajemen tampilan/scene                             |
| `database`         | `AdminDao.java`                 | DAO untuk data admin/pengguna                                            |
|                    | `DatabaseHelper.java`           | Koneksi & utilitas database SQLite                                       |
|                    | `MenuDAO.java`                  | DAO untuk operasi CRUD menu makanan                                      |
|                    | `OrderDAO.java`                 | DAO untuk operasi CRUD pesanan                                           |                        
| `GUI`              | `LoginWindow.java`              | Jendela login untuk autentikasi pengguna                                 |
|                    | `MainWindow.java`               | Jendela utama aplikasi dengan navigasi                                   |
|                    | `MenuManagement.java`           | Panel untuk mengelola menu (tambah/edit/hapus item)                      |
|                    | `PosPanel.java`                 | Panel kasir untuk input pesanan dan transaksi                            |
|                    | `SalesReportPanel.java`         | Panel laporan penjualan dan statistik                                    |
| `models`           | `BaseModel.java`                | Kelas dasar untuk semua model (ID, timestamps)                           |
|                    | `Menu.java`                     | Model untuk item menu (nama, harga, kategori)                            |
|                    | `Order.java`                    | Model untuk pesanan (tanggal, total, status)                             |
|                    | `OrderItem.java`                | Model untuk item dalam pesanan                                           |
|                    | `User.java`                     | Model untuk pengguna/admin sistem                                        |
| `util`             | `PasswordUtils.java`            | Utility untuk hashing dan verifikasi password                            |
| *(root)*           | `Main.java`                     | Titik masuk aplikasi (entry point)                                       |
| *(root)*           | `temurasa.db`                   | File database SQLite                                                     |

---

### 🧠 Implementasi OOP
- Penerapan Pilar OOP
- encapsulation: modifier, dan fields yang bersifat private dan modifier protected, akses melalui setter dan getter
- inheritance: menu dan order mewarisi atribut id dari basemodel
- abstraction: show scene sebagai kelas interface
- polymorphism: method createUI() yang dioverride oleh LoginWindow dan MainWindow

---

### 📌 Pembagian Tugas

| Nama      | Bagian Tugas                                                                 |
|-----------|-------------------------------------------------------------------------------|
| **Siti**  | `MenuController`, `MenuManagementPanel`, `SalesReportPanel`, `Menu`, `MenuDAO`, `Main` |
| **Shabrina** | `OrderController`, `LoginWindow`, `MainWindow`, `Order`, `OrderItem`, `OrderDAO`,  |
| **Gatri** | `UserController`, `PosPanel`, `AdminDAO`, `DatabaseHelper`, `User`, `PasswordUtils` |

---


