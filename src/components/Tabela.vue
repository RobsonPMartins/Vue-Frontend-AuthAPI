<template>
  <table class="w-full border-collapse border border-gray-700">
    <thead class="bg-gray-800">
      <tr>
        <th class="border-r border-white p-2 text-[#ff3f00]">ID</th>
        <th class="border-r border-white p-2 text-[#ff3f00]">Loja</th>
        <th class="border-r border-white p-2 text-[#ff3f00]">Cliente</th>
        <th class="border-r border-white p-2 text-[#ff3f00]">Status</th>
        <th class="border-r border-white p-2 text-[#ff3f00]">Total R$</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="pedido in pedidos" :key="pedido.id" class="text-center">
        <td class="border p-2">{{ pedido.id }}</td>
        <td class="border p-2">{{ pedido.lojaId }}</td>
        <td class="border p-2">{{ pedido.nomeCliente }}</td>
        <td class="border p-2">{{ pedido.statusPedido }}</td>
        <td class="border p-2">{{ pedido.total }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
defineProps(['pedidos'])
</script>
