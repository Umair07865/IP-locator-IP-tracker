<template>
  <span>
    <div class="main justify-content-center pa-6">
      <div >
  
        <v-text-field
          label="IPV-4 Address"
          :rules="rules"
          hide-details="auto"
          v-model="ipInput"
          class="white mt-5"
          outlined
          style="width: 60%"
        ></v-text-field>
       
     
            
             
          
      
      </div>
        <v-btn color="primary" class="ma-2" @click="fetchApiFunction">
        Search
      </v-btn>
      <!--loader-->

    <div class="text-center " >
   

    <v-overlay :value="loading"  >
       <v-progress-circular
      :size="70"
      :width="7"
      
      color="black"
      indeterminate
     
    >
  
    </v-progress-circular>
     <span style="color:white"> loading</span>
    </v-overlay>
  </div>

      <!--loader ending-->
     

      <!--this is the i frame-->
      <div style="width: 100%" class="d-flex">
        <iframe
          width="50%"
          height="600"
          frameborder="0"
          scrolling="no"
          marginheight="0"
          marginwidth="0"
          v-bind:src="this.src"
          ><a href="https://www.maps.ie/distance-area-calculator.html"
            >measure distance on map</a
          ></iframe
        >

        <div style="width: 50%">
          <!-- ip address details-->

          <v-card
            class="mx-auto"
            max-width="500"
            height="600px"
            rounded-xl
            tile
            style="overflow-y: scroll"
          >
            <v-list disabled>
              <v-subheader class="black white--text center"
                >REPORTS</v-subheader
              >
              <v-list-item-group v-model="selectedItem" color="primary">
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> City: </b>
                      {{ city }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>

                <v-list-item two-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Country: </b> {{ country }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>

                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Country Code: </b>{{ countryCode }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Isp: </b>{{ isp }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Latitude: </b>{{ lat }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Longitude: </b>{{ long }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Organization:</b>{{ organization }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Query: </b>{{ query }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Region:</b>{{ region }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Region Name: </b>{{ regionName }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Status:</b>{{ status }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> Time Zone:</b>{{ timeZone }}</v-list-item-title
                    >
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title>
                      <b> zip:</b>{{ zip }}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title> <b> AS:</b>{{ as }}</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </div>
      </div>
         <iframe
          src="https://gifer.com/embed/HcPC"
          width="50%"
          height="400px"
          frameBorder="0"
          allowFullScreen
        ></iframe>
          <h1>Track IP</h1>
      <!-- iframe ends here-->

      <DashboardCards />
    </div>
    <v-container-Fluid>
      <FooterDashboard />
    </v-container-Fluid>
  </span>
</template>
<script>
import FooterDashboard from "./FooterDashboard.vue";
import DashboardCards from "./DashboardCards.vue";
export default {
  name: "DashboardHome",
  data() {
    return {
      ipInput: "",
      long: "",
      lat: "",
      src: "https://maps.google.com/maps?q=31.582045,74.329376&z=15&output=embed",
      city: "",
      country: "",
      countryCode: "",
      isp: "",
      organization: "",
      query: "",
      region: "",
      regionName: "",
      status: "",
      timeZone: "",
      zip: "",
      as: "",
      loading:false
    };
  },
  methods: {
    async fetchApiFunction() {
      await fetch(`http://ip-api.com/json/${this.ipInput}`)
        .then((response) => {
          return response.json();
        })
        .then((data) => {
          console.log(data);
          this.long = data.lon;
          this.lat = data.lat;
          this.src = `https://maps.google.com/maps?q=${this.lat}, ${this.long}&z=15&output=embed`;
          this.city = data.city;
          this.country = data.country;
          this.countryCode = data.countryCode;
          this.isp = data.isp;
          this.organization = data.org;
          this.query = data.query;
          this.region = data.region;
          this.regionName = data.regionName;
          this.status = data.status;
          this.timeZone = data.timezone;
          this.zip = data.zip;
          this.as = data.as;
          setTimeout(() => {
              this.loading=true;
          }, 1000);

          setTimeout(() => {
            this.loading=false;
          }, 3000);
        });
      //    address generator api
    },
  },
  components: {
    FooterDashboard,
    DashboardCards,
  },
};
</script>
