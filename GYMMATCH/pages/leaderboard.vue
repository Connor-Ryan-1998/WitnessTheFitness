<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto"  id="leaderboardHeaderCard" style="background-color: #E94057;">
        <v-card-title class="justify-left">
          <h3 class="text-lg-center" id="leaderboardTitle" style="color: white;">Leaderboard</h3>
        </v-card-title>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
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
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
          <v-card
            class="pa-md-3 mx-auto my-4"
            max-width="550"
            outlined
            :style="'border: 1px solid red;'"
          >
            <v-list-item v-for="name in top10users" :key="name">
              <v-list-item-content>
                <v-list-item-title class="text-h5 mb-1" to="/">
                  {{ name }}
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
      css: [
        // CSS file in the project
        '@/assets/leaderboard.scss',
      ],
    data () {
      return {
        colors: [
          'orange',
          'orange',
          'orange',
          'orange',
          'orange'
        ],
        top10users: [
          'Monica Geller',
          'Julian Dasilvia',
          'Mike Lyne',
          'Claire Kumas',
          'Blair Dota'
        ],
        model: 0,
      }
    },
  }
</script>