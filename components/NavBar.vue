<template>
  <div class="w-full  bg-white ">
    <div class="container mx-auto flex justify-between">

    
    <div class="h-14 pl-4  flex justify-center items-center">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-8 w-8 text-blue-700"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M14 10l-2 1m0 0l-2-1m2 1v2.5M20 7l-2 1m2-1l-2-1m2 1v2.5M14 4l-2-1-2 1M4 7l2-1M4 7l2 1M4 7v2.5M12 21l-2-1m2 1l2-1m-2 1v-2.5M6 18l-2-1v-2.5M18 18l2-1v-2.5"
        />
      </svg>
      <h3 class="text-blue-800 px-3 font-bold text-xl">{{company?company:''}}</h3>
    </div>
    <div class="flex items-center">
      <nuxt-link
        v-for="(menu, i) in menus"
        :key="i"
        :to="menu.route"
        
        :class="`text-sm hover:text-blue-700 text-gray-500 font-medium tracking-wide hover:bg-blue-50 px-3 py-1 rounded-md mx-1 ${
          id === menu.id ? 'text-blue-700' : ''
        }`"
        ><span @click="id=menu.id">
          {{ menu.menu }}
          </span></nuxt-link
      >
    </div>
    <div class="flex items-start space-x-2 pt-2 pr-4">
      <div class="w-10 h-10 rounded-full bg-blue-300"></div>
      <div class="">
        <button @click.prevent="onLogout()" class="bg-blue-900 py-2 px-8 text-blue-50 rounded">
          logout
        </button>
      </div>
    </div>
    </div>
  </div>
</template>
<script>

export default {
  props:{
    company:String
  },
  data() {
    return {
      menus: [
        {
          menu: "Dashbord",
          route: "/dashbord",
          id: "dashbord",
        },
        {
          menu: "Maisons",
          route: "/maison",
          id: "maison",
        },
        {
          menu: "Comptabilite",
          route: "/comptabilite/general",
          id: "compte",
        },
        {
          menu: "Clients",
          route: "/clients",
          id: "client",
        },
        {
          menu: "Parametre",
          route: "/settings/general",
          id: "settings",
        },
      ],
      id: "dashbord",
    };
  },
  methods:{
    async onLogout () {
      await this.$apolloHelpers.onLogout();
      this.$router.push('/login');
    },
  }
};
</script>