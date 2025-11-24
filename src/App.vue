<script setup>
import { ref } from "vue"

const tasks = ref([])
const newTask = ref("")

function addTask() {
  if (newTask.value.trim() === "") return
  tasks.value.push(newTask.value.trim())
  newTask.value = ""
}

function deleteTask(index) {
  const deleted = tasks.value[index]
  tasks.value.splice(index, 1)
  alert(`Tugas "${deleted}" berhasil dihapus!`)
}
</script>

<template>
  <div
    style="max-width: 520px; margin: 60px auto; padding: 20px; 
           background:#f8f8f8; border-radius: 12px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);"
  >
    <h2 style="margin-bottom: 16px; text-align: center;">To-Do List</h2>

    <!-- input dan button -->
    <div style="display: flex; gap: 8px;">
      <input 
        v-model="newTask" 
        @keyup.enter="addTask"
        placeholder="Tambah tugas baru..." 
        style="padding: 10px; flex: 1; border-radius: 8px; border: 1px solid #ccc;"
      />

      <button
        @click="addTask"
        style="padding: 10px 14px; background: #4caf50; color: white; border: none; 
               border-radius: 8px; cursor: pointer; font-weight: bold;"
      >
        Tambah
      </button>
    </div>

    <br />

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
  </div>
</template>
