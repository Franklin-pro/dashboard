<template>
    <div class="flex">
  <div class="left-dashboard">
    <Menu/>
  </div>
  <div class="right-dashboard">
  <header>
    <nav class="flex justify-between pb-5 pt-5 pr-8 pl-8 items-center">
        <div class="leading-loose text-xl">
  <h1 class="text-4xl text-gray-400 font-extralight">Good Morning,<span class="text-4xl text-black font-medium ">John Doe</span></h1>
  
  <p class="text-gray-400 font-light">Your performance summary this week</p>
        </div>
        <div class="flex gap-6">
      
          <div v-for="(item , index) in items" :key="index" class="relative">
            <div 
              v-if="item.title === 'Select-Category'"
              class="text-blue-800 items-center gap-2 px-2 pr-7 pl-7 pb-2 pt-2 py-1 transition rounded cursor-pointer bg-white hover:bg-neutral-100 text-black"
              @click="toggleDropdown(index)"
            >
              <div class="flex items-center gap-2">
                <UIcon :name="item.icon"/>
                {{ item.title }}
              </div>
            </div>
           
            <div v-if="item.showDropdown" class="absolute mt-1 w-48 bg-gray-700 z-50 shadow-lg rounded">
              <div v-if="item.dropdownItems && item.showDropdown" class="flex flex-col gap-3">
              <Dropdown :show="item.showDropdown" :dropdownItems="item.dropdownItems" />
            </div>
              
            </div>
          </div>
          
  
  <input type="date" class="bg-white rounded-md pr-7 pl-7 pb-2 pt-2 text-black">
        </div>
        <div class="flex gap-4 text-2xl items-center text-black">
     <UIcon name="i-heroicons-magnifying-glass"/>
     <UIcon name="i-heroicons-envelope-20-solid"/>
     <UIcon name="i-heroicons-bell-solid"/>
     <div class="image">
        <img src="../Assets/gent.jpeg" alt="">
     </div>
    
        </div>
    </nav>
  </header>
 <header>
    <nav class="flex justify-between items-center border-b p-2 border-gray-900">
        <div class="flex gap-4 pr-7 pl-7">
            <NuxtLink to="/" class="border-r pr-3 text-black">Contact</NuxtLink>
            <NuxtLink to="/" class="border-r pr-3 text-black">Lead</NuxtLink>
            <NuxtLink to="/" class="border-r pr-3 text-black">Accounts</NuxtLink>
            <NuxtLink to="/" class=" pr-3 text-black">More</NuxtLink>
        </div>
        <div class="flex gap-4 pr-7 pl-7">
            <button class="border rounded-md pr-3 pl-3 pb-1 pt-1 flex justify-between items-center gap-3 border-blue-400 text-black"><UIcon name="i-heroicons-share"/>share</button>
            <button class="border rounded-md pr-3 pl-3 pb-1 pt-1 flex justify-between items-center gap-3 border-blue-400 text-black"><UIcon name="i-heroicons-printer"/>Print</button>
            <button class="border rounded-md pr-3 pl-3 pb-1 pt-1 bg-blue-600 flex justify-between items-center gap-3 border-blue-400 "> <UIcon name="i-heroicons-plus-circle"/> New</button>
        </div>
    </nav>
 </header>
 <div class="flex gap-5 justify-between p-4">
    <div v-for="(experiences, index) in experience" :key="index" class="">
    <div class="p-3">
        <Cards :title="experiences.title" :subhead="experiences.subhead"  :text = "experiences.text"/>
       
    </div>

 </div>

 </div>
<div v-for="item in items" :key="item.id" class="flex w-full">
  <div class="w-full">
    <ChartsCard :title="cardTitle" :items="cardItems" @toggle-dropdown="toggleDropdown"/>

    
  </div>
  <div class="w-full">
  <ChartsCard :title="cardTitle" :items="cardItem"/>

</div>

  </div>
 
 
  </div>
    </div>
  
    
    <div>
        
    </div>
  </template>
  
  <script setup>
import Menu from '~/components/SideBar/Menu.vue';

const items = ref([
  {
    title: "Select-Category",
    dropdownItems: ["Default", "CRM", "Purple", "Purple Dark", "Sale", "HR"],
    path: '/dashboard',
    showDropdown: false
  },
  
]);

const toggleDropdown = (index) => {
  items.value[index].showDropdown = !items.value[index].showDropdown;
 
};
  const experience = [
    
  {

    title:"Number of sales",
    subhead:"2431",
   

  },
  {

title:"sale revenue",
subhead:"$24.403",


},
{

title:"Total Products",
subhead:"84234",


},
{

title:"Total Customer",
subhead:"64732",


},
{

title:"Average Price",
subhead:"S2431",


},
{

title:"Total Turnover",
subhead:"$5567",


}

]
const cardTitle = 'Revenue statics';
import { ref } from 'vue';


const cardItems = ref([
  { 
    title: 'DATE', 
    showDropdown: false, 
    dropdownItems: ['today', 'this week', 'this month', 'this year'] 
  }
]);
const cardItem = ref([
  { 
    title: 'DATE', 
    showDropdown: false, 
    dropdownItems: ['today', 'this week', 'this month', 'this year'] 
  }
]);
const toggleDropdowns = (index) => {
  cardItems.value[index].showDropdown = !cardItems.value[index].showDropdown;
};



  
  </script>
  
  <style scoped>
  .left-dashboard{
    background-color: rgb(231, 231, 231);
    height: 100vh;
    width: 20%;
  }
  .right-dashboard{
    background-color: rgb(231, 231, 231);
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
  