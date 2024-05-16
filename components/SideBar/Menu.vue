<template>
  <div class="fixed overflow-y-auto h-full overscroll-auto w-[240px] shadow-xl text-black">
    <header class="flex items-center gap-2 p-4 hover:scale-[100%] transitio cursor-pointer">
      <p class="font-bold text-black">Star<span class="text-blue-800">Admin</span></p>
    </header>
    <div class="p-4 grow">
      <div class="grid">
        <ul class="relative cursor-pointer">
          <li v-for="(menu, index) in menus" :key="menu.id" class="text-gray-700 font-bold p-2">
            <div @click="toggleSubmenu(index)" class=" gap-4 items-center">
              <UIcon :name="menu.icon"/>
              {{ menu.name }}
            </div>
            <div class="shadow-xl text-black p-5 rounded-md" v-show="activeMenu === index">
              <ul>
                <li v-for="submenu in menu.submenus" :key="submenu.id" class="hover:bg-gray-500 rounded-md text-black font-light p-2">
                  
                  <nuxt-link :to="submenu.route" class="">{{ submenu.name }}</nuxt-link>
                </li>
              </ul>
            </div>
          </li>

          <li v-for="(menu, index) in menux" :key="menu.id" class="p-3">
            <div @click="toggleSubmenux(index)" class="text-gray-700 font-bold">
              <UIcon :name="menu.icon"/>
              {{ menu.name }}
            </div>
            <div  v-show="activeMenux === inde">
              <ul>
                <li v-for="submenu in menu.submenus" :key="submenu.id" class="flex items-center font-light gap-2 hover:bg-gray-400 rounded-md">
                  <UIcon :name="submenu.icon"/>
                  <nuxt-link :to="submenu.route" class="text-gray-500">{{ submenu.name }}</nuxt-link>
                  
                </li>
              </ul>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menux:[
      {
          id: 2,
          name: 'Orders',
        submenus:[
        { id: 6, name: 'Revenue Order',icon:'i-heroicons-archive-box-16-solid', route: '/menu2/submenu2' }, 
            { id: 7,icon:'i-heroicons-credit-card-20-solid', name: 'Payments', route: '/menu2/submenu2' }  
        ]
        },
        {
          id: 2,
          name: 'CMR',
        submenus:[
        { id: 6, name: 'Users', route: '/menu2/submenu2' }, 
          { id: 7,icon:'i-heroicons-clipboard-document-list', name: 'Customer Profile', route: '/menu2/submenu2' },
          { id: 7,icon:'i-heroicons-rectangle-stack-solid', name: 'Resource', route: '/menu2/submenu2' },
          { id: 7, name: 'Management', route: '/menu2/submenu2' } 
        ]
        },
        {
          id: 2,
          name: 'Developments',
        submenus:[
        { id: 6, name: 'Revenue Order', route: '/menu2/submenu2' }, 
          { id: 7, name: 'Payments', route: '/menu2/submenu2' }  
        ]
        },
      ],
      menus: [
        {
          id: 1,
          name: 'Dashboard',
          icon: "i-heroicons-qr-code",
          submenus: [
            { id: 1, name: 'Default', route: '/menu1/submenu1' },
            { id: 1, name: 'CRM', route: '/menu1/submenu1' },
            { id: 1, name: 'Purple', route: '/menu1/submenu1' },
            { id: 2, name: 'Purple Dark', route: '/menu1/submenu2' },
            { id: 1, name: 'Sale', route: '/menu1/submenu1' },
            { id: 1, name: 'HR', route: '/menu1/submenu1' },
          ]
        },
        
        {
          id: 3,
          name: 'Settings',
          icon: 'i-heroicons-cog-6-tooth-20-solid',
          submenus: [
            { id: 4, name: 'Submenu 2.1', route: '/menu2/submenu1' },
            { id: 5, name: 'Submenu 2.2', route: '/menu2/submenu2' },
          
          ]
        }
      ],
      activeMenu: null
    };
  },
  methods: {
    toggleSubmenu(index) {
      if (this.activeMenu === index) {
        this.activeMenu = null;
      }
      
      else {
        this.activeMenu = index;
      }
    }
  }
};
</script>

<style scoped>

</style>
