<template>
  <div class="flex justify-around gap-5 p-4">
    <div class="flex justify-between w-full bg-white p-4 rounded-xl text-black">
      <h1 class="text-black">{{ title }}</h1>
      <div v-for="(item , index) in items" :key="index" class="relative">
        <div
          v-if="item.title === 'DATE'"
          class="bg-gray-200 text-blue-800 items-center gap-2 px-2 py-1 transition rounded cursor-pointer hover:bg-neutral-100 text-black"
          @click="toggleDropdown(index)"
        >
          <div class="flex items-center gap-2">
            <UIcon :name="item.icon"/>
            {{ item.title }}
          </div>
        </div>
        <div v-if="item.showDropdown" class="absolute mt-1 w-48 bg-green-500 z-50 shadow-lg rounded">
          <div v-if="item.dropdownItems && item.showDropdown" class="flex flex-col gap-3 text-gray-200 hover:text-primary">
            <Dropdown :show="item.showDropdown" :dropdownItems="item.dropdownItems" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const props = defineProps({
  title: String,
  items: Array
});

const toggleDropdown = (index) => {
  props.items[index].showDropdown = !props.items[index].showDropdown;
};
</script>

<style scoped>

</style>
