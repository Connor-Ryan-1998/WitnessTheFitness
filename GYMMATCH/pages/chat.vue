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
                    label="Public APIs"
                    placeholder="Start typing to Search"
                    prepend-icon="mdi-database-search"
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
            <v-img v-for="(url) in images" :key="url"
            :src="url"
            ></v-img>
            </v-list-item-avatar>
          </v-badge>
          <v-list-item-content>
            <v-list-item-title class="text-h5 mb-1" to="/">
              {{ name }}
            </v-list-item-title>
            <v-list-item-subtitle v-if="i == 0" style="font-family: Arial;font-size: 12pt;color:#000000;opacity: .5;">Your current rank</v-list-item-subtitle>
          </v-list-item-content>
           <v-col justify="right" align="right" style="font-family: Arial;font-size: 15pt;color:#E94057;">
             {{69 - Math.floor(Math.random() + i)}}
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
          'https://picsum.photos/600/200',
          'https://picsum.photos/300/200',
          'https://picsum.photos/500/200'
        ],
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