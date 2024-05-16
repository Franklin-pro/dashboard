<template>
    <div v-if="show" class="absolute mt-1 w-48 bg-gray-700 z-50 shadow-lg rounded">
      <div class="py-1">
        <div v-for="item in dropdownItems" :key="item" class="px-4 py-2 cursor-pointer hover:bg-gray-200">{{ item }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      show: Boolean,
      dropdownItems: Array,
    },
  };
  </script>
  
  <style scoped>

  </style>