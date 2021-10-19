<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6" class="tab-wrapper">
      <v-toolbar color="#E94057" flat dark>
        <v-toolbar-title color="white">
          Matching
        </v-toolbar-title>
        <template v-slot:extension>
          <v-tabs
            fixed-tabs
          >
            <v-tabs-slider color="white"></v-tabs-slider>
            <v-tab>Same Session</v-tab>
            <v-tab>Others</v-tab>
            <v-tab-item>
              <v-container fluid class="scrolling-div">
                <v-row dense>
                  <v-col
                    v-for="card1 in cards1"
                    :key="card1.title"
                    :cols="card1.flex"
                  >
                    <v-card outlined color="transparent" style="padding: 10px; margin: 5px;">
                      <nuxt-link :to="`/users/${card1.id}`">
                        <v-img
                          :src="card1.src"
                          class="white--text align-end"
                          gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                          height="200px"
                        >
                        </v-img>
                      </nuxt-link>
                      <nuxt-link class="routerLink" :to="`/users/${card1.id}`"><h1 v-text="card1.title"></h1></nuxt-link>
                      <h3 v-text="card1.job"></h3>
                      <p v-text="card1.detail"> </p>
                    </v-card>
                  </v-col>
                </v-row>
              </v-container>
            </v-tab-item>
            <v-tab-item>
              <v-container fluid class="scrolling-div">
                <v-row dense>
                  <v-col
                    v-for="card in cards"
                    :key="card.title"
                    :cols="card.flex"
                  >
                    <v-card outlined color="transparent" style="padding: 10px; margin: 5px;">
                      <nuxt-link :to="`/users/${card.id}`">
                        <v-img
                          :src="card.src"
                          class="white--text align-end"
                          gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                          height="200px"
                        >
                        </v-img>
                      </nuxt-link>
                      <nuxt-link class="routerLink" :to="`/users/${card.id}`"><h1 v-text="card.title"></h1></nuxt-link>
                      <h3 v-text="card.job"></h3>
                      <p v-text="card.detail"> </p>
                    </v-card>
                  </v-col>
                </v-row>
              </v-container>
            </v-tab-item>
          </v-tabs>
        </template>
      </v-toolbar>
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
        images: [
          'https://picsum.photos/id/190/200/300',
          'https://picsum.photos/id/400/200/300',
          'https://picsum.photos/id/160/200/300',
          'https://picsum.photos/id/150/200/300',
          'https://picsum.photos/id/237/200/300',
          'https://picsum.photos/id/200/200/300',
          'https://picsum.photos/id/300/200/300',
        ],
        cards1: [
        { id: 2, title: 'Julian Dasilva', src: 'https://picsum.photos/id/400/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', link: '/leaderboard', flex: 6 },
        { id: 1, title: 'Monica Geller', src: 'https://picsum.photos/id/190/200/300', job: 'Car Dealer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 6, title: 'Connor Ryan', src: 'https://picsum.photos/id/200/200/300', job: 'Software Engineer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        ],
        cards: [
        { id: 1, title: 'Monica Geller', src: 'https://picsum.photos/id/190/200/300', job: 'Car Dealer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', link: '/leaderboard', flex: 6 },
        { id: 2, title: 'Julian Dasilvia', src: 'https://picsum.photos/id/400/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 3, title: 'Mike Lyne', src: 'https://picsum.photos/id/160/200/300', job: 'Officemen', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 4, title: 'Claire Kumas', src: 'https://picsum.photos/id/150/200/300', job: 'Teacher', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', link: '/leaderboard', flex: 6 },
        { id: 5, title: 'Blair Dota', src: 'https://picsum.photos/id/237/200/300', job: 'Shop Owner', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 6, title: 'Connor Ryan', src: 'https://picsum.photos/id/200/200/300', job: 'Software Engineer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 7, title: 'Dendi Navidad', src: 'https://picsum.photos/id/300/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
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
  .routerLink{
     text-decoration: none;
     color:black;
 }
 .tab-wrapper {
  height:100%; /* Set to desired height of entire tabbed section, or use flex, or ... */
  display:flex; 
  flex-direction: column;
}
 .scrolling-div {
  width: 100%;
  height: 1000px;
  overflow: auto;
  white-space: nowrap;
}
</style>