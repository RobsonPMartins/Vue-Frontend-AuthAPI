<template>
  <div class="flex justify-end gap-2 mb-4 border-2">
    <input type="date" v-model="dataInicio" class="border p-2 rounded">
    <input type="date" v-model="dataFim" class="border p-2 rounded">
    <button @click="$emit('filtrar', { dataInicio, dataFim })" class="bg-blue-500 text-white p-2 rounded">
      Filtrar
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const dataInicio = ref('')
const dataFim = ref('')
</script>
