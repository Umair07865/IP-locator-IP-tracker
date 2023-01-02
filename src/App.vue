<template>
  <v-app>
    <v-app-bar
      app
      color="black"
      dark
    >
      <div class="d-flex align-center">
       
       <v-icon size="4rem">
         mdi-wifi-marker
       </v-icon>

       <h1>IP TRACKER</h1>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
    <DashboardHome/>
      
    </v-main>
  
    
    
  
  </v-app>
</template>

<script>

import DashboardHome from './components/DashboardHome.vue'

export default {
  name: 'App',

  components: {
   DashboardHome,
 
   
  },

  data: () => ({
    //
  }),
};
</script>
