<template>
  <div
    class="bg-slate-800 shadow rounded-xl hover:scale-105 transition-all"
  >
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <img
        :src="meal.strMealThumb"
        :alt="meal.strMeal"
        class="rounded-t-xl w-full h-40 object-cover "
      />
    </router-link>
    <div class="p-3 bg-slate-800">
      <h3 class="font-bold text-sm sm:text-base text-indigo-400">{{ meal.strMeal }}</h3>
      <p class="mb-4 text-xs sm:text-base text-white">
        {{ $filters.truncateWords(meal.strInstructions, 20) }}
      </p>
      <div class="flex items-center justify-between">
        <YouTubeButton :href="meal.strYoutube" />
      </div>
    </div>
  </div>
</template>

<script setup>
import YouTubeButton from './YouTubeButton.vue';

const { meal } = defineProps({
  meal: {
    required: true,
    type: Object
  }
})

</script>
