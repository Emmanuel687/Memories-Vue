<template>
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
    <!-- Example item -->
    <div v-for="memory in memories" :key="memory.id" class="bg-white p-4 rounded-md shadow-md">
      <img :src="memory.images" alt="Item Image" class="w-full h-32 object-cover mb-4 rounded-md" />
      <h2 class="text-xl font-semibold mb-2">{{ memory.title}}</h2>
      <p class="text-gray-600 mb-4">{{ memory.description }}</p>
      <div class="flex space-x-2">
        <span class="bg-gray-200 text-gray-700 px-2 py-1 text-sm rounded-md">{{ memory.tags }}</span>
    <!-- Add more tags as needed -->
      </div>
      <CommentForm />
    </div>

  </div>

</template>
<script setup>
 import CommentForm from './CommentForm.vue';

 const props = defineProps(["memories"]);




</script>