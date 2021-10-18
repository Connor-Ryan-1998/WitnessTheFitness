<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="6" md="6">
      <v-card class="pa-md-6 mx-lg-auto"  id="leaderboardHeaderCard">
        <v-card-title class="justify-left">
            <h3 id="messagesTitle">Direct Message</h3>
        </v-card-title>
        <v-card-subtitle class="justify-left">
            <h3 id="messagesSubtitle">You have 2 new messages</h3>
        </v-card-subtitle>
      </v-card>
    <v-card class="pa-md-6 mx-lg-auto">
      <v-container class="fill-height">
        <v-row class="fill-height pb-14" align="end">
          <v-col>
            <div v-for="(item, index) in chat" :key="index" 
                :class="['d-flex flex-row align-center my-2', item.from == 'user' ? 'justify-end': null]">
              <span v-if="item.from == 'user'" class="blue--text mr-3">{{ item.msg }}</span>
              <v-avatar :color="item.from == 'user' ? 'indigo': 'red'" size="36">
                <span class="white--text">{{ item.from[0] }}</span>
              </v-avatar>
              <span v-if="item.from != 'user'" class="blue--text ml-3">{{ item.msg }}</span>
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
      }
    },
      methods: {
      send: function(){
        this.chat.push(
        {
          from: "user",
          msg: this.msg
        })
        this.msg = null
        this.addReply()
      },
      addReply(){
        this.chat.push({
          from: "sushant",
          msg: "Hmm"
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
    #messagesSubtitle{
    color: black;
    font-family: Arial, Helvetica, sans-serif ;
    font-size: 14pt;
    opacity: 0.3;
  }
  #leaderboardTop3{
    padding: 10%;
  }
  
</style>