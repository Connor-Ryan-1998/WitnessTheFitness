<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">GYMATCH</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">Never fear working out alone!</p>
        </v-card-text>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">VIEW TODAY'S TOP RECORDS</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">VIEW THE RANKING</p>
        </v-card-text>
        <v-carousel v-model="model" class="py-md-6 my-3">
          <v-carousel-item
            v-for="(color, i) in colors"
            :key="color"
          >
            <v-sheet
              :color="color"
              height="100%"
              tile
            >
              <v-row
                class="fill-height"
                align="center"
                justify="center"
              >
                <div class="text-h2">
                  Ranking {{ i + 1 }}
                </div>
              </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
        <v-card-actions class="justify-center">
              <v-btn
                elevation="2"
                x-large
                color="warning"
                nuxt
                class="text-center"
                to="/ranking"
              >
                VIEW MORE RANKING
              </v-btn>
            </v-card-actions>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-center">
          <h3 class="text-lg-center">VIEW TODAY'S CLASSES</h3>
        </v-card-title>
        <v-card-text class="justify-center">
          <p class="text-md-center">SELECT CLASSES</p>
        </v-card-text>
          <v-card
            class="pa-md-3 mx-auto my-4"
            max-width="550"
            outlined
            :style="'border: 1px solid blue;'"
          >
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title class="text-h5 mb-1">
                  <NuxtLink to="/"> YOGA</NuxtLink>
                </v-list-item-title>
                <v-list-item-subtitle>YOGAYOGA</v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
            </v-list-item>

            <v-card-actions>
              <v-btn
                outlined
                rounded
                text
                color="primary"
                nuxt
                to="/findNearby"
              >
                VIEW MORE
              </v-btn>
            </v-card-actions>
          </v-card>
          <v-card
            class="pa-md-3 mx-auto my-4"
            max-width="550"
            outlined
            :style="'border: 1px solid red;'"
          >
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title class="text-h5 mb-1" to="/">
                  BOXING
                </v-list-item-title>
                <v-list-item-subtitle>PUNCH HARDER</v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
            </v-list-item>

            <v-card-actions>
              <v-btn
                outlined
                rounded
                text
                color="red"
                nuxt
                to="/"
              >
                VIEW MORE
              </v-btn>
            </v-card-actions>
          </v-card>
      </v-card>
    </v-col>
  </v-row>
</template>


<script>
  export default {
    data () {
      return {
        colors: [
          'orange',
          'orange',
          'orange',
          'orange',
          'orange'
        ],
        model: 0,
      }
    },
  }
</script>