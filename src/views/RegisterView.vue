
  <template>
  <div class="min-h-screen flex items-center justify-center bg-gray-200">
    <div class="grid grid-cols-1 min-h-screen md:grid-cols-2 w-full max-w-6xl p-2">
      <!-- Lado Esquerdo (Formulário) -->
      <div class="flex flex-col justify-center space-y-4 bg-white p-8 rounded-lg shadow-lg">
        <h1 class="text-3xl font-semibold text-center text-orange-500">Registrar-se</h1>
        <input
          v-model="nome"
          placeholder="Nome..."
          class="p-3 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500"
        />
        <input
          v-model="email"
          placeholder="Email..."
          type="email"
          class="p-3 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500"
        />
        <input
          v-model="senha"
          placeholder="Senha..."
          type="password"
          class="p-3 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500"
        />
        <button
          @click="registrarUsuario"
          class="w-full py-3 bg-blue-600 text-white rounded-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500 cursor-pointer"
        >
          Registrar
        </button>
        <p class="text-center text-gray-600">{{ mensagem }}</p>
      </div>

      <!-- Lado Direito (Imagem) -->
      <div class="hidden md:block">
        <img
          src="../components/icons/login-lindo.jpeg"
          alt="Imagem de registro"
          class="w-full h-full object-cover rounded-lg shadow-lg"
        />
      </div>
    </div>
  </div>
</template>


<script>
import api from '@/services/api'

export default {
  data() {
    return {
      nome: '',
      email: '',
      senha: '',
      messagem: '',
    }
  },
  methods: {
    async registrarUsuario() {
      try {
        const response = await api.post('/auth/register', {
          nome: this.nome,
          email: this.email,
          senha: this.senha,
        })

        localStorage.setItem('token', response.data.token)

        alert(response.data.token)

        this.mensagem = 'Usuário registrado e autenticado com sucesso!'

        this.nome = ''
        this.email = ''
        this.senha = ''

        this.$router.push('/')

        console.log('Dados sendo passado =>', this.nome, this.email, this.senha)
      } catch (error) {
        this.messagem = 'Erro ao registrar usuário.'
        console.error(error)
      }
    },
  },
}
</script>
