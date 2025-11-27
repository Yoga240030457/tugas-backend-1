# Tugas1 — README

## Deskripsi Studi Kasus

### Studi Kasus 1
Simulasi pengelolaan data akademik yang sederhana. Ada tiga tokoh utama: `Student`, `Professor`, dan `Address`. Mahasiswa menyimpan data dasar serta riwayat seminar; dosen membimbing beberapa mahasiswa dengan batas tertentu; alamat menyediakan validasi dan format yang rapi. Fokusnya pada hubungan antar objek dan logika ringan tanpa ketergantungan eksternal.

### Studi Kasus 2
Simulasi alur peminjaman di perpustakaan. Kelas dasar `LibraryItem` menjadi fondasi untuk item, `Book` mewarisi perilaku itu dan menambahkan `author` serta `isbn`, sedangkan `LibraryMember` menangani proses meminjam dan mengembalikan. Sistem mencatat siapa peminjam dan tenggat pengembalian, lalu menghitung denda keterlambatan lewat `calculate_late_fee` dengan kebijakan denda harian.

## Penjelasan Class Diagram (Singkat)
- Studi Kasus 1:
  - `Student` memiliki `Address` (komposisi).
  - `Professor` mengawasi banyak `Student` (asosiasi dengan batasan jumlah).
  - `Person` hanya berupa stub dan tidak dipakai dalam pewarisan aktif.
- Studi Kasus 2:
  - `Book` mewarisi `LibraryItem` (pewarisan).
  - `Book` memiliki `Author` (komposisi).
  - `LibraryMember` meminjam/mengembalikan `LibraryItem` (asosiasi).
  - `Book.calculate_late_fee()` meng-override versi dasar untuk menerapkan kebijakan denda khusus.

## Struktur Folder (Tree)
```
Tugas1/
├─ StudiKasus1/
│  ├─ main.py
│  ├─ address.py
│  ├─ student.py
│  ├─ professor.py
│  └─ person.py
└─ StudiKasus2/
   ├─ main.py
   ├─ library_item.py
   ├─ book.py
   ├─ author.py
   └─ library_member.py
```

## Cara Menjalankan

### Studi Kasus 1
- Masuk ke folder `Tugas1/StudiKasus1`, lalu jalankan:
```
python main.py
```

### Studi Kasus 2
- Masuk ke folder `Tugas1/StudiKasus2`, lalu jalankan:
```
python main.py
```

## Catatan Penggunaan OOP
- Inheritance:
  - `Book` mewarisi `LibraryItem` untuk berbagi perilaku peminjaman dan struktur dasar item.
- Relasi:
  - `Student` memiliki `Address`.
  - `Professor` mengawasi banyak `Student`.
  - `LibraryMember` berasosiasi dengan `LibraryItem` lewat proses pinjam dan kembali.
  - `Book` memiliki `Author`.
- Override:
  - `Book.calculate_late_fee(days_late)` meng-override implementasi dasar agar memakai kebijakan denda harian khusus buku.

## Dokumentasi Penggunaan AI (Prompt Diringkas)
- Tidak ada AI di dalam source code proyek; seluruh logika ditulis manual.
- Penulisan README ini dirapikan dengan bantuan alat otomatis agar bahasanya konsisten.
- Prompt (diringkas) yang dipakai untuk merapikan narasi:
  - "Jelaskan singkat relasi kelas dan pewarisan untuk Tugas1."
  - "Buat struktur folder dalam bentuk tree dan cara menjalankan kedua studi kasus."
