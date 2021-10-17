<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto"  id="leaderboardHeaderCard">
        <v-card-title class="justify-center">
            <v-card-text>
                <v-autocomplete
                    v-model="model"
                    :items="items"
                    :loading="isLoading"
                    :search-input.sync="search"
                    color="white"
                    hide-no-data
                    hide-selected
                    item-text="Description"
                    item-value="API"
                    label="Search..."
                    placeholder="Start typing to Search"
                    return-object
                ></v-autocomplete>
            </v-card-text>
        </v-card-title>
      </v-card>
    <v-card class="pa-md-6 mx-lg-auto">
        <v-card-title class="justify-left">
            <h3 id="messagesTitle">Messages</h3>
        </v-card-title>
        <v-card-subtitle class="justify-left">
            <h3 id="messagesSubtitle">You have 2 new messages</h3>
        </v-card-subtitle>
    </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-list-item v-for="(name, i) in top10users" :key="name" href="/exampleChat" target="_blank">
          <v-badge 
              bordered
              overlap
              right
              color="#84C857"
              offset-y="30"
              offset-x="30">
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
            <v-badge v-if="i == 0 || i == 1"
              bordered
              overlap
              right
              color="#E24E59"
              offset-y="30"
              offset-x="30">
                <v-list-item-title class="text-h5 mb-1" to="/" style="font-family: Arial;font-size: 15pt;font-weight: bold;">
                {{ name }}
                </v-list-item-title>
            </v-badge>
            <v-list-item-title v-else class="text-h5 mb-1" to="/" style="font-family: Arial;font-size: 15pt;font-weight: bold;">
                {{ name }}
            </v-list-item-title>
            <v-list-item-subtitle style="font-family: Arial;font-size: 12pt;color:#000000;opacity: .5;">{{ textEntries[i] }} </v-list-item-subtitle>
          </v-list-item-content>
           <v-col justify="right" align="right" style="font-family: Arial;font-size: 12pt;color:#000000;opacity: .3;">
             {{Math.floor(Math.random() * i) + 2}} minutes ago
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
          'Blair Dota',
          'Connor Ryan',
          'Monica Geller',
          'Julian Dasilvia',
          'Mike Lyne',
          'Claire Kumas',
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
        textEntries: [
            'Hey!',
            'Good gym session',
            'Almost there',
            'And there we go',
            'See you next time!',
            'Nice to meet you',
            'Legs day was solid'
          ]
      }
    },
  }
</script>

<style scoped>
  #leaderboardHeaderCard {
    background-color: #E94057;
  }
  #messagesTitle{
    color: black;
    font-family: Arial, Helvetica, sans-serif ;
    font-weight: bold;
    font-size: 28pt;
    padding-bottom: 5%;
  }
    #messagesSubtitle{
    color: black;
    font-family: Arial, Helvetica, sans-serif ;
    font-size: 14pt;
    opacity: 0.3;
    padding-bottom: 5%;
  }
  #leaderboardTop3{
    padding: 10%;
  }
</style>