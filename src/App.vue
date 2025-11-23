<script setup>

  import { reactive } from "vue"
  import { ref } from "vue"

  // Membuat reactive object
  // const task = reactive({ 
  //   task: "", 
  //   created_at: new Date().toISOString()
  // })

  const tasks = ref([])
  const newTask = ref("")

  const handleKeyEnter = () => {
    console.log("Enter ditekan:", searchQuery.value)
  }

  // tambah tugas
  function addTask() {
    if (newTask.value.trim() === "") return
    tasks.value.push(newTask.value)
    newTask.value = ""
  }

  // hapus tugas
  function deleteTask(index) {
    tasks.value.splice(index, 1)
  }


</script>

<template>
  <div style="max-width: 400px; margin: auto; padding: 20px">
    <h2>To-Do List</h2>

    <!-- tambah tugas -->
    <form @submit.prevent="addTask">
      <input 
        v-model="newTask" 
        placeholder="Tambah tugas baru..." 
        style="padding: 8px; width: 100%"
      />
    </form>

    <br />

    <!-- kondisi jika kosong -->
    <p v-if="tasks.length === 0">Tidak ada tugas</p>

    <!-- list tugas -->
    <ul v-else>
      <li 
        v-for="(task, index) in tasks" 
        :key="index"
        style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; text-align: left"
      >
        {{ index + 1 }}. {{ task }}
        <button 
          @click="deleteTask(index)"
          style="background: red; color: white; border: none; padding: 4px 8px; border-radius: 5px"
        >
          Hapus
        </button>
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
