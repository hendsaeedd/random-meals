<template>
  <header class="bg-indigo-800 text-xs sm:text-base h-16 flex text-white justify-between items-stretch font-bold">
    <router-link
      :to="{ name: 'home' }"
      class="inline-flex items-center h-full px-5 text-white font-bold"
    >
      Home
    </router-link>

    <div class="hidden sm:flex items-center gap-1">
      <router-link
        v-for="(link, index) in links"
        :key="index"
        :to="{ name: link.route }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-indigo-500 hover:text-white hover-border"
      >
        {{ link.name }}
      </router-link>
    </div>

    <div class="flex sm:hidden items-center">
      <button @click="showMenu = !showMenu" class="inline-flex items-center px-3 h-full text-white transition-colors hover:bg-indigo-500 hover:text-white">
        <svg v-if="!showMenu" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

      <div v-show="showMenu" class="absolute top-16 right-0 w-full bg-indigo-800">
        <router-link
          v-for="(link, index) in links"
          :key="index"
          :to="{ name: link.route }"
          class="block py-2 px-3 mb-4 transition-colors hover:bg-indigo-500 hover:text-white"
        >
          {{ link.name }}
        </router-link>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      links: [
        { name: 'Search Meals', route: 'byName' },
        { name: 'Meals By Letter', route: 'byLetter' },
        { name: 'Meals By Ingredients', route: 'ingredients' },
      ],
      showMenu: false,
    }
  },
}
</script>
