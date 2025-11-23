# Assignment: Vue.js – Simple To-Do List

## Identitas
- Nama : Izzat Nazhiefa  
- NIM  : F1D02310114  

---

## Deskripsi Tugas
Pada tugas ini saya membuat aplikasi To-Do List sederhana menggunakan Vue.js.  
Aplikasi ini memiliki fitur dasar yang umum dipakai pada aplikasi daftar tugas, seperti:

- Menambah tugas ke daftar  
- Menghapus tugas tertentu  
- Menampilkan daftar tugas secara dinamis  
- Menampilkan pesan **“Tidak ada tugas”** jika daftar kosong  
- Menggunakan konsep reaktivitas Vue dengan `ref()`  
- Memanfaatkan event handling seperti `@submit.prevent` dan `@click`  

---

## Hasil
### 1. Screenshot Hasil Program
- Tampilan awal program sebelum tugas di tambahkan
  <img width="1520" height="780" alt="image" src="https://github.com/user-attachments/assets/ff81b1df-d1c4-4350-b8f2-ca9ca70244cf" />

- Tampilan setelah tugas ditambahkan dan list daftar tugas
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/93ce233b-de55-4229-9d86-079290ec8dde" />

- Tampilan saat menghapus tugas
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d08bf6ce-3c23-46e4-951f-4abb8ffdb5f0" />



### 2. Penjelasan Singkat
- **State Management:**  
  Menggunakan `ref()` untuk menyimpan `tasks` (array) dan `newTask` (string input).
  
- **Menambah Tugas (`addTask()`):**  
  Fungsi ini mengecek apakah input kosong, lalu memasukkan data ke array `tasks`.

- **Menampilkan Daftar:**  
  Menggunakan `v-for="(task, index) in tasks"` dengan `:key="index"`.

- **Menghapus Tugas:**  
  Tombol hapus memanggil `deleteTask(index)` untuk menghapus item tertentu.

- **Handling Jika Kosong:**  
  Menggunakan `v-if="tasks.length === 0"` untuk menampilkan teks “Tidak ada tugas”.

---
