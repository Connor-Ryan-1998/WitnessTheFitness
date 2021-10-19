<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="6" md="6">
      <v-card class="pa-md-6 mx-lg-auto"  id="leaderboardHeaderCard">
        <v-card-title class="justify-left">
            <h3 id="messagesTitle">Direct Message</h3>
        </v-card-title>
      </v-card>
    <v-card class="pa-md-6 mx-lg-auto" style="height: 35em; overflow-y: auto;">
      <v-container>
        <v-row class="pb-14" align="end">
          <v-col>
            <div v-for="(item, index) in chat" :key="index" 
                :class="['d-flex flex-row align-center my-2', item.from == 'me' ? 'justify-end': null]">
              <span v-if="item.from == 'me'" class="blue--text mr-3">{{ item.msg }}</span>
              <v-avatar :color="item.from == 'me' ? 'indigo': 'red'" size="36">
                <span class="white--text">{{ item.from[0] }}</span>
              </v-avatar>
              <span v-if="item.from != 'me'" class="blue--text ml-3">{{ item.msg }}</span>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-container class="ma-0 pa-0">
          <v-row no-gutters>
            <v-col>
              <div class="d-flex flex-row align-center">
                <v-text-field v-model="msg" placeholder="Type Something" @keypress.enter="send"></v-text-field>
                <v-btn icon class="ml-4" @click="send"><v-icon>mdi-send</v-icon></v-btn>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </v-col>
  </v-row>
</template>


<script>
  export default {
    data () {
      return {
        model: 0,
        textEntries: [
            'Hey!',
            'Good gym session',
            'Almost there',
            'And there we go',
            'See you next time!',
            'Nice to meet you',
            'Legs day was solid'
          ],
        chat: [
          ],
        msg: null,
        responseIndex: 0,
        botResponse: ["Yes", "thank you","please", "Amazing", "Thats's cool", "Amazing", "Nice", "Okay!"],
      }
    },
      methods: {
      send: function(){
        this.chat.push(
        {
          from: "me",
          msg: this.msg
        })
        this.responseIndex = Math.floor(Math.random() * 5)
        this.msg = null
        this.addReply()
      },
      addReply(){
        this.chat.push({
          from: "user",
          msg: this.botResponse[this.responseIndex]
        })
      }
    }
  }
</script>

<style scoped>
  #leaderboardHeaderCard {
    background-color: #E94057;
  }
  #messagesTitle{
    color: white;
    font-family: Arial, Helvetica, sans-serif ;
  }
  #messageBox{
  }
  #leaderboardTop3{
    padding: 10%;
  }
  
</style>