<script setup lang="ts">
import { ref } from 'vue'
import TheWelcome from '../components/TheWelcome.vue'

// Create a reactive array to store grid items
const gridItems = ref(['Item 1', 'Item 2', 'Item 3', 'Item 4', 'Item 5', 'Item 6'])

// Function to add a new item to the grid
const addItem = () => {
  const newItem = `Item ${gridItems.value.length + 1}` // Create a new item based on the current length
  gridItems.value.push(newItem) // Add new item to the gridItems array
}

// Function to remove an item from the grid
const removeItem = (index: number) => {
  gridItems.value.splice(index, 1) // Remove the item at the specified index
}
</script>

<template>
  <div class="flex flex-col h-screen">
    <header class="py-4" style="background-color: rgba(255, 83, 73, 0.05);">
      <div class="flex justify-between items-center px-6">
        <div class="flex items-center">
          <img alt="Vue logo" class="logo pr-2" src="@/assets/logo.png" width="60" height="60" />
          <div>
            <h2 class="text-orange-400 custom-bold">Kim Pengkhieng</h2>
            <h2
              class="custom-bold text-white bg-[#FF5349] border border-[#FFA500] rounded-full text-left inline-block px-2"
              style="font-size: 12px;">
              Premium
            </h2>
          </div>
        </div>
        <div class="text-[#FF5349]">
          <button @click="addItem" class="text-white bg-[#FF5349] py-2 px-4 rounded">Add</button>
        </div>
      </div>
    </header>
    <main class="flex-1 px-4 py-2 text-white">
      <!-- Main content -->
      <div class="grid grid-cols-2 gap-2">
        <div v-for="(item, index) in gridItems" :key="index"
          class="bg-[#FF5349] px-4 py-2 rounded relative justify-center">
          {{ item }}
          <button @click="removeItem(index)"
            class="absolute top-1/2 right-2 transform -translate-y-1/2 bg-red-500 text-white py-1 px-2 rounded-full text-xs">
            Delete
          </button>
        </div>
      </div>
    </main>
    <footer class="py-4 bg-black text-center text-white">
      tailwind sticky footer
    </footer>
  </div>
</template>

<style>
.custom-bold {
  font-weight: 500 !important;
}
</style>
