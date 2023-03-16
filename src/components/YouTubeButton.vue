<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 rounded-lg text-xs sm:text-base text-white border-indigo-600 bg-indigo-500 hover:bg-indigo-600 transition-colors"
  >
    <slot>YouTube</slot>
  </a>
</template>

<script setup>
const props = defineProps({
  href: String
})
</script>
