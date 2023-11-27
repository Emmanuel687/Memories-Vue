<template>
  <MemoryForm   @memorySubmitted="handleSubmittedMemories"/>
  <MemoryList :memories="memories"/>
  <CommentForm/>
  <CommentList />
  <p class="text-red-500">Hello world</p>
</template>

<script setup>
import CommentForm from './components/CommentForm.vue';
import CommentList from './components/CommentList.vue';
import MemoryForm from './components/MemoryForm.vue';
import MemoryList from './components/MemoryList.vue';
import {ref} from "vue";


const memories = ref([
  {
    id: 1,
    title: "Beautiful Sunset",
    description: "Enjoyed a breathtaking sunset at the beach.",
    tags: "nature, sunset, beach",
    images:"https://github.com/selemondev.png"
  },
  {
    id: 2,
    title: "Family Picnic",
    description: "Had a fun picnic day with the family in the park.",
    tags: "family, picnic, outdoors",
    images:"https://github.com/selemondev.png"
  },
  {
    id: 3,
    title: "Hiking Adventure",
    description: "Explored a scenic trail and reached the mountain's summit.",
    tags: "hiking, adventure, nature",
    images:"https://github.com/selemondev.png"
  },
  {
    id: 4,
    title: "Delicious Homemade Meal",
    description: "Cooked a tasty homemade meal with friends.",
    tags: "food, cooking, friends",
    images:"https://github.com/selemondev.png"

  },
  {
    id: 5,
    title: "City Lights",
    description: "Captured the mesmerizing city lights at night.",
    tags: "city, lights, night",
    images:"https://github.com/selemondev.png"
  },
]);



const handleSubmittedMemories = (memoryData)=>{
  console.log(memoryData)
  memories.value.push({
    id: crypto.randomUUID(),
    title:memoryData.title,
    description:memoryData.description,
    tags:memoryData.tags,
    images:memoryData.images

  })



}



</script>