<template>
    <v-footer
    dark
    padless
  >
    <v-card
      flat
      tile
      class="black  white--text text-center"
    >
      <v-card-text>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 white--text"
          icon
        >
         

        </v-btn>
        
   <div class="iconDiv d-flex justify-space-between">
        <v-icon>
            mdi-facebook
        </v-icon>
         <v-icon>
            mdi-whatsapp
        </v-icon>
         <v-icon>
            mdi-instagram
        </v-icon>
         <v-icon>
            mdi-linkedin
        </v-icon>
        </div>

      </v-card-text>

      <v-card-text class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>
<script>
export default {
    name:'FooterDashboard'
}
</script>
<style scoped>
.iconDiv{
   
    width: 30%;
    margin-left: 35%;
    
}
</style>