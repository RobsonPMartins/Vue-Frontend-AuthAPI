<template>
  <div class="grid grid-cols-3 gap-4 mb-6 mt-6">
    <div class="bg-[#98DFEA] text-white p-4 rounded-xl shadow-lg">
      <h2 class="text-lg font-bold">Pedidos</h2>
      <p class="text-2xl">{{ pedidos.total }}</p>
      <p>Total R$: {{ pedidos.valorTotal }}</p>
    </div>
    <div class="bg-green-500 text-white p-4 rounded-xl shadow-lg">
      <h2 class="text-lg font-bold">Vendas</h2>
      <p class="text-2xl">{{ vendas.total }}</p>
      <p>Total R$: {{ vendas.valorTotal }}</p>
    </div>
    <div class="bg-[#EA2B1F] text-white p-4 rounded-xl shadow-lg">
      <h2 class="text-lg font-bold">Ticket Médio</h2>
      <p class="text-2xl">R$ {{ ticketMedio }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps(['pedidos', 'vendas', 'ticketMedio'])
</script>
