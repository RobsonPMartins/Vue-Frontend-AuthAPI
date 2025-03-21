<template>
  <div class="flex items-center justify-center min-h-screen bg-gray-200 p-2">
    <!-- Formulário de Login -->
    <div class="w-full md:w-1/2 bg-white md:p-20 rounded-lg shadow-lg flex items-center justify-center">
      <div class="w-full p-9">
        <h1 class="text-2xl text-orange-500 font-semibold text-center mb-6">Login</h1>

        <input 
          v-model="email" 
          placeholder="Email" 
          type="email" 
          class="w-full p-3 mb-4 border border-gray-300 rounded-lg" 
        />
        <input 
          v-model="senha" 
          placeholder="Senha" 
          type="password" 
          class="w-full p-3 mb-4 border border-gray-300 rounded-lg" 
        />

        <button 
          @click="loginUsuario" 
          class="w-full bg-blue-500 text-white py-3 rounded-lg hover:bg-blue-600 transition duration-300"
        >
          Login
        </button>

        <p class="text-center text-red-500 mt-4">{{ mensagem }}</p>

        <p class="text-center mt-4">
          Não tem uma conta? 
          <router-link to="/register" class="text-blue-500 hover:underline">Registrar</router-link>
        </p>
      </div>
    </div>

    <!-- Lado Direito (Imagem) -->
    <div class="hidden md:block md:w-1/2">
      <img
        src="../components/icons/login-lindo.jpeg"
        alt="Imagem de registro"
        class="w-full h-full object-cover rounded-lg shadow-lg"
      />
    </div>
  </div>
</template>

<script>
import api from '@/services/api';

export default {
  data() {
    return {
      email: '',
      senha: '',
      mensagem: '',
    };
  },
  methods: {
    async loginUsuario() {
      try {
        const response = await api.post('/auth/login', { 
          email: this.email, 
          senha: this.senha 
        });

        // Armazenando o token no localStorage
        localStorage.setItem('token', response.data.token);

        // Redirecionando para o dashboard após o login bem-sucedido
        this.$router.push('/dashboard');
        
      } catch (error) {
        // Exibindo mensagem de erro
        this.mensagem = error.response.data.message || 'Erro ao fazer login.';
        console.error(error);
      }
    },
  },
};
</script>
