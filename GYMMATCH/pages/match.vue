<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-toolbar color="#E94057" flat dark>
        <v-toolbar-title color="white">
          Matching
        </v-toolbar-title>
        <template v-slot:extension>
          <v-tabs
            v-model="tab"
            align-with-title
            fixed-tabs
          >
            <v-tabs-slider color="white"></v-tabs-slider>
            <v-tab 
            v-for="item in items"
            :key="item">
              {{ item }}
            </v-tab>
          </v-tabs>
        </template>
      </v-toolbar>
      <v-tabs-items v-model="tab">
        <v-tab-item
          v-for="item in items"
          :key="item"
        >
          <v-card flat>
            <v-card-text v-text="text"></v-card-text>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-col>
  </v-row>
</template>


<script>
  export default {
    data () {
      return {
        top10users: [
          'Monica Geller',
          'Julian Dasilvia',
          'Mike Lyne',
          'Claire Kumas',
          'Blair Dota',
          'Connor Ryan',
          'Dendi Navidad',
        ],
        items: [
          'Same Session', 'Other'
        ],
        images: [
          'https://picsum.photos/id/190/200/300',
          'https://picsum.photos/id/400/200/300',
          'https://picsum.photos/id/160/200/300',
          'https://picsum.photos/id/150/200/300',
          'https://picsum.photos/id/237/200/300',
          'https://picsum.photos/id/200/200/300',
          'https://picsum.photos/id/300/200/300',
        ],
      }
    },
  }
</script>

<style scoped>
  #leaderboardHeaderCard {
    background-color: #E94057;
  }
  #leaderboardTitle{
    color: white;
  }
  #leaderboardTop3{
    padding: 10%;
  }
</style>