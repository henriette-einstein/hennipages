<template>
  <nav class="flex justify-between items-center py-4 px-6 bg-white shadow">
    <div class="flex items-center">
      <div class="flex-shrink-0">
            <nuxt-link to="/">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H19" />
                <path d="M4 4v13.5A2.5 2.5 0 0 0 6.5 20h12.1a1.5 1.5 0 0 1 0 3H6.5A4.5 4.5 0 0 1 2 18.5V4h2z" />
              </svg>
            </nuxt-link>
          </div>
    </div>
    <div class="hidden md:flex items-center space-x-4">
      <template v-for="item in menuItems">
        <nuxt-link :to="item.href" class="text-black hover:text-gray-600">{{ item.name }}</nuxt-link>    
      </template>
    </div>
    <div class="md:hidden flex items-center">
      <button @click="isOpen = !isOpen" class="text-black hover:text-gray-500 focus:outline-none">
        <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path v-if="!isOpen" fill-rule="evenodd" clip-rule="evenodd" d="M4 6h16v2H4V6zm0 5h16v2H4v-2zm0 5h16v2H4v-2z"/>
          <path v-else fill-rule="evenodd" clip-rule="evenodd" d="M13.414 12l3.293-3.293a1 1 0 1 0-1.414-1.414L12 10.586l-3.293-3.293a1 1 0 0 0-1.414 1.414L10.586 12l-3.293 3.293a1 1 0 0 0 1.414 1.414L12 13.414l3.293 3.293a1 1 0 0 0 1.414-1.414L13.414 12z"/>
        </svg>
      </button>
    </div>
    <div v-if="isOpen" class="md:hidden absolute top-16 inset-x-0 p-2 bg-white">
      <template v-for="item in menuItems">
        <nuxt-link :to="item.href" @click="isOpen = false" class="block text-black py-2 border-b border-gray-300 hover:text-gray-500">{{ item.name }}</nuxt-link>
      </template>
    </div>
  </nav>
</template>

<script setup>
const isOpen = ref(false)
const props = defineProps({
  menuItems: {
    type: Array,
    required: true,
  },
})
</script>
