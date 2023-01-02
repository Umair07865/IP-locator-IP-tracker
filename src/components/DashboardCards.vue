<template>
  <v-container-Fluid class="grey lighten-5 " >
    <v-row no-gutters>
      <v-col
        v-for="n in 3"
        :key="n"
        cols="12" 
        sm="12"

      >
        <v-card
          class="pa-2 mt-4"
          outlined
          
          tile
          
        >
        <v-card
    class="mx-auto"
  
  >
   <v-icon>
       mdi-map-marker-path
   </v-icon>

    <v-card-title>
     IP Tracker
    </v-card-title>

    <v-card-subtitle>
    Track via public ip address Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quaerat aliquam quas nulla omnis non exercitationem laudantium numquam veniam eaque dicta!
    </v-card-subtitle>

    <v-card-actions>
      <v-btn
        color="orange lighten-2"
        text
      >
        Explore
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
        </v-card>
      </v-col>
    </v-row>
  </v-container-Fluid>
</template>
<script>
export default {
    name:'DashboardCards'
}
</script>




  