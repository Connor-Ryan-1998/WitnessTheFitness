<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto"  id="leaderboardHeaderCard">
        <v-card-title class="justify-left">
          <h3 class="text-lg-center" id="leaderboardTitle">Leaderboard: This week</h3>
        </v-card-title>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-row id="leaderboardTop3">
          <v-col justify="center" align="center">
            <v-row justify="center" align="center"  style="padding-bottom: 5%;">
              <v-badge
              bordered
              overlap
              bottom
              content="2"
              color="grey"
              offset-x="50">
                <v-avatar style = "border: 3px solid silver;"
                  size="80"
                  rounded = "true">
                 <img
                  src="https://images.freeimages.com/images/large-previews/e71/frog-1371919.jpg"
                  alt="JF"
                 >
                </v-avatar>
              </v-badge>
            </v-row>
            <v-row justify="center" align="center" style="font-family: Arial;font-size: 12pt;color:#9F9F9F;">
              Julia Frydenburg
            </v-row>
            <v-row justify="center" align="center" style="font-family: Arial;font-size: 15pt;color:#17181A;font-weight: bold;">
              90
            </v-row>
          </v-col >
          <v-col justify="center" align="center">
            <v-row justify="center" align="center"  style="padding-bottom: 5%;">
              <v-badge
              bordered
              overlap
              bottom
              content="1"
              color="yellow"
              offset-x="60">
                <v-avatar style = "border: 3px solid gold;"
                  size="100"
                  rounded = "true">
                  <img
                  src="https://images.freeimages.com/images/large-previews/70f/clouds-1371112.jpg"
                  alt="JF"
                 >
                </v-avatar>
              </v-badge>
            </v-row>
            <v-row justify="center" align="center" style="font-family: Arial;font-size: 12pt;color:#9F9F9F;">
              Scott Morrison
            </v-row>
            <v-row justify="center" align="center" style="font-family: Arial;font-size: 15pt;color:#17181A;font-weight: bold;">
              100
            </v-row>
          </v-col>
          <v-col justify="center" align="center">
            <v-row justify="center" align="center"  style="padding-bottom: 5%;">
              <v-badge
              bordered
              overlap
              bottom
              content="3"
              color="brown"
              offset-x="50">
                <v-avatar style = "border: 3px solid brown;"
                  size="80"
                  rounded = "true">
                 <img
                  src="https://cdn.vuetifyjs.com/images/john.jpg"
                  alt="JF"
                 >
                </v-avatar>
              </v-badge>
            </v-row>
            <v-row justify="center" align="center" style="font-family: Arial;font-size: 12pt;color:#9F9F9F;">
              Kevin Rudd
            </v-row>
            <v-row justify="center" align="center" style="font-family: Arial;font-size: 15pt;color:#17181A;font-weight: bold;">
              70
            </v-row>
          </v-col>
        </v-row>
        <v-list-item v-for="(name, i) in top10users" :key="name">
          <v-badge 
              bordered
              overlap
              left
              :content = "i + 4"
              color="#E94057"
              offset-y="60">
            <v-list-item-avatar 
              size="80"
              color="grey"
              rounded = "true"
            >
            <v-img
            :src="images[i]"
            ></v-img>
            </v-list-item-avatar>
          </v-badge>
          <v-list-item-content>
            <v-list-item-title class="text-h5 mb-1" to="/">
              {{ name }}
            </v-list-item-title>
            <v-list-item-subtitle v-if="i == 0" style="font-family: Arial;font-size: 12pt;color:#000000;opacity: .5;">Your current rank</v-list-item-subtitle>
          </v-list-item-content>
           <v-col v-if="i != 0" justify="right" align="right" style="font-family: Arial;font-size: 15pt;color:#E94057;">
              <v-btn
                class="ma-2"
                text
                icon
                color="red lighten-2"
                href="/exampleChat"
              >
                <v-icon
                  medium
                  color="teal darken-2"
                >
                  mdi-message-processing
                </v-icon>
              </v-btn>
           </v-col>
        </v-list-item>
      </v-card>
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
        model: 0,
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