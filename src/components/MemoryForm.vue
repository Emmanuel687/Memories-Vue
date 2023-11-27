<template>
    <form class="space-y-4" @submit.prevent="onSubmit">
      <!-- Title Input -->
      <div>
        <label for="title" class="block text-sm font-medium text-gray-700">Title</label>
        <input type="text" id="title" name="title" class="w-full p-3 border border-gray-300 rounded-md focus:outline-none focus:border-blue-500" v-model="title" />
      </div>
  
      <!-- Description Textarea -->
      <div>
        <label for="description" class="block text-sm font-medium text-gray-700">Description</label>
        <textarea id="description" name="description" rows="4" class="w-full p-3 border border-gray-300 rounded-md focus:outline-none focus:border-blue-500" v-model="description"></textarea>
      </div>
  
      <!-- Related Tags Input -->
      <div>
        <label for="tags" class="block text-sm font-medium text-gray-700">Related Tags</label>
        <input type="text" id="tags" name="tags" class="w-full p-3 border border-gray-300 rounded-md focus:outline-none focus:border-blue-500" v-model="tags" />
      </div>
  
      <!-- Images Input -->
      <div>
        <label for="images" class="block text-sm font-medium text-gray-700">Images (URLs, comma-separated)</label>
        <input type="text" id="images" name="images" class="w-full p-3 border border-gray-300 rounded-md focus:outline-none focus:border-blue-500" v-model="image" />
      </div>
  
      <!-- Submit Button -->
      <button type="submit" class="bg-blue-500 text-white py-3 px-4 rounded-md hover:bg-blue-600 w-full">Create Memory</button>
    </form>
  </template>
  
  <script setup>
  import { ref, defineEmits } from "vue";
  
  const title = ref("");
  const description = ref("");
  const tags = ref("");
  const image = ref("");
  
  const emit = defineEmits(["memorySubmitted"]);
  
  const onSubmit = () => {
    // if (!title.value || !description.value || !tags.value || !image.value) return;
  
    const memoryData = {
      title: title.value,
      description: description.value,
      tags: tags.value,
      image: image.value
    };

  
    emit("memorySubmitted", memoryData);
  
    title.value = "";
    description.value = "";
    tags.value = "";
    image.value = "";
  };
  </script>
  