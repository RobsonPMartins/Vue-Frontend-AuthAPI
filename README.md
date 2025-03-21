# Frontend - Vue 3^ + TailwindCSS

Este repositório contém o frontend de um sistema utilizando **Vue 3**, **TailwindCSS** e autenticação.

## 📌 Tecnologias Utilizadas
- Vue 3 (Composition API)
- Vue Router
- Pinia (gerenciamento de estado)
- TailwindCSS
- Axios (para comunicação com API)

## 🚀 Como Rodar o Projeto

### 1️⃣ Clonar o repositório
```sh
git clone https://github.com/RobsonPMartins/Vue-Frontend-AuthAPI.git
cd seu-repositorio
```

### 2️⃣ Instalar dependências
```sh
npm install
```

### 3️⃣ Configurar variáveis de ambiente
Crie um arquivo **.env** na raiz do projeto e adicione:
```env
VITE_API_URL=http://localhost:3000/api
```

### 4️⃣ Iniciar o projeto
```sh
npm run dev
```

## 📡 Funcionalidades
- 📌 **Autenticação**: Tela de login e cadastro
- 📊 **Dashboard**: Exibição de métricas e pedidos
- 🌐 **Consumo de API**: Integração com backend via Axios

## 📜 Estrutura de Pastas
```
📂 src
 ├── 📂 components        # Componentes reutilizáveis
 ├── 📂 views             # Telas principais
 ├── 📂 router            # Configuração de rotas
 ├── 📂 services          # Requisições HTTP (Axios)
```

## 🛠 Scripts Disponíveis
- `npm run dev` → Inicia o frontend em modo de desenvolvimento
- `npm run build` → Gera a versão de produção

## 📜 Licença
Este projeto está sob a licença MIT.

