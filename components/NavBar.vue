<template>
    <div class="flex">
  <div class="left-dashboard">
  <h1>Star-Admin</h1>
  </div>
  <div class="right-dashboard">
  <header>
    <nav class="flex justify-between pb-5 pt-5 pr-8 pl-8 items-center">
        <div class="leading-loose text-xl">
  <h1 class="text-4xl text-gray-400 font-extralight">Good Morning,<span class="text-4xl text-black font-medium ">John Doe</span></h1>
  
  <p class="text-gray-400 font-light">Your performance summary this week</p>
        </div>
        <div class="flex gap-6">
        <Down/>
    <select name="" id="" class="bg-gray-200 rounded-md pr-7 pl-7 pb-2 pt-2 text-gray-600 text-center border-slate-600">
    <option value="">Category</option>
    <option value="">ABC</option>
    <option value="">DEF</option>
  </select>
          
  
  <input type="date" class="bg-gray-200 rounded-md pr-7 pl-7 pb-2 pt-2 text-gray-600">
        </div>
        <div class="flex gap-4 text-2xl items-center">
     <UIcon name="i-heroicons-magnifying-glass"/>
     <UIcon name="i-heroicons-envelope-20-solid"/>
     <UIcon name="i-heroicons-bell-solid"/>
     <div class="image">
        <img src="../Assets/gent.jpeg" alt="">
     </div>
    
        </div>
    </nav>
  </header>
  </div>
    </div>
  </template>
  
  <script setup>
  
  
  
  </script>
  
  <style scoped>
  .left-dashboard{
    background-color: red;
    height: 100vh;
    width: 20%;
  }
  .right-dashboard{
    background-color: rgba(62, 62, 62, 0.854);
    height: 100vh;
    width: 80%;
  }
  .image{
    width: 30px;
    height: 30px;
  }
  img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 100%;
  }
  </style>
  