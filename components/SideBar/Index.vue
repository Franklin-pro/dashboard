<template>
    <div>
      <h1>Menu Items</h1>
      <ul>
        <li v-for="(menu, index) in data" :key="menu.id">
          <div @click="toggleSubmenu(index)">
            {{ menu.name }}
          </div>
          <ul v-show="menu.showSubmenu">
            <li v-for="submenu in menu.submenus" :key="submenu.id">
              <nuxt-link :to="submenu.route">{{ submenu.name }}</nuxt-link>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
  
  const props = defineProps({
    data: {
      type: Array,
      required: true,
    },
  });
  
  const toggleSubmenu = (index) => {
    props.data.forEach((menu, i) => {
      if (i === index) {
        menu.showSubmenu = !menu.showSubmenu;
      } else {
        menu.showSubmenu = false;
      }
    });
  };
  </script>
  
  <style scoped>
  /* Add your scoped styles here */
  </style>
  