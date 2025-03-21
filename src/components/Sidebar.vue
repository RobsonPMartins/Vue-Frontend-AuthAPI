<template>
  <div class="h-screen w-64 bg-gray-800 text-white p-4">
    <h2 class="text-xl font-bold mb-6">Dashboard</h2>
    <ul>
      <li class="mb-2">
        <router-link to="/" class="flex gap-2 p-2 hover:bg-gray-700 rounded">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            stroke="#ff3f00"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="lucide lucide-door-open"
          >
            <path d="M13 4h3a2 2 0 0 1 2 2v14" />
            <path d="M2 20h3" />
            <path d="M13 20h9" />
            <path d="M10 12v.01" />
            <path
              d="M13 4.562v16.157a1 1 0 0 1-1.242.97L5 20V5.562a2 2 0 0 1 1.515-1.94l4-1A2 2 0 0 1 13 4.561Z"
            />
          </svg>
          Início
        </router-link>
      </li>
      <li>
        <router-link to="/pedidos" class="flex gap-2  p-2 hover:bg-gray-700 rounded">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            stroke="#ff3f00"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="lucide lucide-package-open"
          >
            <path d="M12 22v-9" />
            <path
              d="M15.17 2.21a1.67 1.67 0 0 1 1.63 0L21 4.57a1.93 1.93 0 0 1 0 3.36L8.82 14.79a1.655 1.655 0 0 1-1.64 0L3 12.43a1.93 1.93 0 0 1 0-3.36z"
            />
            <path
              d="M20 13v3.87a2.06 2.06 0 0 1-1.11 1.83l-6 3.08a1.93 1.93 0 0 1-1.78 0l-6-3.08A2.06 2.06 0 0 1 4 16.87V13"
            />
            <path
              d="M21 12.43a1.93 1.93 0 0 0 0-3.36L8.83 2.2a1.64 1.64 0 0 0-1.63 0L3 4.57a1.93 1.93 0 0 0 0 3.36l12.18 6.86a1.636 1.636 0 0 0 1.63 0z"
            />
          </svg>
          Pedidos
        </router-link>
      </li>
    </ul>
  </div>
</template>
