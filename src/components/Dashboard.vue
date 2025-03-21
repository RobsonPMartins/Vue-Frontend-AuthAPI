<template>
  <div class="flex">
    <Sidebar />
    <div class="flex-1 p-6">
      <Navbar />
      
      <Cards :pedidos="metricas.pedidos" :vendas="metricas.vendas" :ticketMedio="metricas.ticketMedio" />

      <h2 class="text-xl font-bold mt-6 mb-2">Lista de Pedidos</h2>
      <Tabela :pedidos="pedidos" />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Sidebar from '@/components/Sidebar.vue'
import Navbar from '@/components/Navbar.vue'
import Cards from '@/components/Cards.vue'
import Tabela from '@/components/Tabela.vue'

const pedidos = ref([
  { id: '001', lojaId: 'LJ123', nomeCliente: 'João Silva', statusPedido: 'Concluído', total: 250.00 },
  { id: '002', lojaId: 'LJ456', nomeCliente: 'Maria Souza', statusPedido: 'Pendente', total: 120.50 },
  { id: '003', lojaId: 'LJ789', nomeCliente: 'Carlos Lima', statusPedido: 'Cancelado', total: 300.00 },
  { id: '004', lojaId: 'LJ101', nomeCliente: 'Ana Costa', statusPedido: 'Concluído', total: 500.75 }
])

const metricas = ref({
  pedidos: { total: pedidos.value.length, valorTotal: pedidos.value.reduce((acc, p) => acc + p.total, 0) },
  vendas: { total: pedidos.value.filter(p => p.statusPedido === 'Concluído').length, valorTotal: pedidos.value.filter(p => p.statusPedido === 'Concluído').reduce((acc, p) => acc + p.total, 0) },
  ticketMedio: (pedidos.value.reduce((acc, p) => acc + p.total, 0) / pedidos.value.length).toFixed(2)
})

</script>
