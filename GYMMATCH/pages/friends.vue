<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto"  id="leaderboardHeaderCard">
        <v-card-title class="justify-left">
          <h3 class="text-lg-center" id="leaderboardTitle">My Friends</h3>
          <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
        </v-card-title>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-list-item v-for="(name, i) in top10users" :key="name" style="padding-top: 15px;">
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
          </v-list-item-content>
           <v-col justify="right" align="right" style="font-family: Arial;font-size: 15pt;color:#E94057;">
               <nuxt-link to="/chat" class="routerLink">
                <v-icon color="#e94057">
                    mdi-message-processing
                </v-icon>
                </nuxt-link>
                <nuxt-link to="/users/1" class="routerLink">
                <v-icon color="#e94057">
                    mdi-account-multiple-plus
                </v-icon>
                </nuxt-link>
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
          'Matthew Wiebe',
          'Michelle Smith',
          'Bob Menery',
          'Popeye Clark',
          'Seymour Skinner',
          'Connor Ryan',
          'Dendi Navidad',
          'Michael Scott',
          'Mary Michelle',
          'Tony Abbot',
        ],
        model: 0,
        images: [
          'https://picsum.photos/id/1005/5760/3840',
          'https://picsum.photos/id/1027/2848/4272',
          'https://picsum.photos/id/1074/5472/3648',
          'https://picsum.photos/id/338/2000/1333',
          'https://picsum.photos/id/237/200/300',
          'https://picsum.photos/id/200/200/300',
          'https://picsum.photos/id/334/2304/1536',
          'https://picsum.photos/id/342/2896/1944',
          'https://picsum.photos/id/375/5184/3456',
          'https://picsum.photos/id/433/4752/316',
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