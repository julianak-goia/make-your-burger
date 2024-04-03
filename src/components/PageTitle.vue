<template>
  <div>
    <h1 class="text-6xl text-white">{{ title }}</h1>
    <h3 class="text-2xl text-white mt-2">{{ description }}</h3>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
});
</script>
