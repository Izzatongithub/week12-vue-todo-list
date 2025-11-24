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
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/263c9747-bf33-4de9-875a-58f57fed1551" />

- Tampilan setelah tugas ditambahkan dan list daftar tugas
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4c4abf92-c78d-46f6-926a-de4c91b77353" />

- Tampilan saat menghapus tugas
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/15530f6c-1a25-4201-abf9-6ec3cb2b3e17" />


### 2. Penjelasan Singkat
- **State:**

      const tasks = ref([])
      const newTask = ref("")
    
  Menggunakan `ref()` untuk menyimpan `tasks` (array) dan `newTask` (string input).
  
- **Menambah Tugas (`addTask()`):**

      function addTask() {
        if (newTask.value.trim() === "") return
        tasks.value.push(newTask.value.trim())
        newTask.value = ""
      }

  Fungsi ini mengecek apakah input kosong, lalu memasukkan data ke array `tasks`.

- **Menampilkan Daftar:**

      <p v-if="tasks.length === 0" style="opacity: .6;">Belum ada tugas</p>
    
        <ul v-else style="padding-left: 0; list-style: none; margin-top: 10px;">
          <li 
            v-for="(task, index) in tasks"
            :key="index"
            style="display: flex; justify-content: space-between; align-items: center;
                   background: white; padding: 10px 12px; border-radius: 8px; 
                   margin-bottom: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.05);"
          >
            <span>{{ index + 1 }}. {{ task }}</span>
    
            <button 
              @click="deleteTask(index)"
              style="background: red; color: white; border: none; padding: 6px 10px; 
                     border-radius: 6px; cursor: pointer;"
            >
              Hapus
            </button>
          </li>
        </ul>

  Menggunakan `v-for="(task, index) in tasks"` dengan `:key="index"`.

- **Menghapus Tugas:**

      function deleteTask(index) {
        const deleted = tasks.value[index]
        tasks.value.splice(index, 1)
        alert(`Tugas "${deleted}" berhasil dihapus!`)
      }

  Tombol hapus memanggil `deleteTask(index)` untuk menghapus item tertentu.

- **Handling Jika Kosong:**

      <p v-if="tasks.length === 0" style="opacity: .6;">Belum ada tugas</p>

  Menggunakan `v-if="tasks.length === 0"` untuk menampilkan teks “Tidak ada tugas”.

---
