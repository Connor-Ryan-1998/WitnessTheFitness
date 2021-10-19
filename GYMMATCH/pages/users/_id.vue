<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto" id="profileHeaderCard">
        <v-card-title class="justify-left">
          <v-icon color="white" @click="goBack" class="pr-5">mdi-arrow-left</v-icon>
          <h3 class="text-lg-center" id="profileTitle" style="font-size: 28px;">{{ users[userKey-1].title }}</h3>
        </v-card-title>
      </v-card>
      <v-img
      class="pa-3 mx-auto my-10"
      max-height="60%"
      max-width="90%"
      :src=users[userKey-1].src>
        <nuxt-link to="/chat" class="routerLink">
          <v-avatar color="white" max-width="80px" class="pa-2 mx-auto" max-height="80px" min-width="70px" min-height="70px" style="postion:absolute; left: 20%; top: 85% ">
            <v-icon color="#e94057">
              mdi-message-processing
            </v-icon>
          </v-avatar>
        </nuxt-link>
        <v-avatar color="white" max-width="80px" class="pa-2 mx-auto" max-height="80px" min-width="70px" min-height="70px" style="postion:absolute; left: 60%; top: 85% ">
          <v-icon color="#e94057">
            mdi-account-multiple-plus
          </v-icon>
        </v-avatar>
      </v-img>
      <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
        <v-col style="flex-grow: 0; padding-left: 30px">
            <v-icon
                small
                color="black"
            >
            info
            </v-icon>
        </v-col>
        <v-col style="flex-grow: 1;"> 
            <h3 style="font-family: Arial;font-size: 12pt;">Personal Information</h3>
        </v-col>
        </v-row>
        <v-list one-line style="font-family: Arial;font-size: 14pt;">
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Username</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].title }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Email</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].email }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Phone</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].pn }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Gender</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse">{{ users[userKey-1].gender }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField"
                >Date of Birth</v-list-item-title
              >
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].dob }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
        <v-col style="flex-grow: 0; padding-left: 30px">
            <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
            <v-icon
                small
                color="black"
            >
            widgets
            </v-icon>
        </v-col>
        <v-col style="flex-grow: 1;"> 
            <h3 style="font-family: Arial;font-size: 12pt;">Interests</h3>
        </v-col>
        </v-row>
        <v-row id="interestButtons">
          <v-btn
            style="margin-left: 30px"
            id="interest"
            rounded
            color="gray"
            outlined
          >
            {{ users[userKey-1].int1 }}
          </v-btn>
          <v-btn id="interest" rounded color="gray" outlined> {{ users[userKey-1].int2 }} </v-btn>
          <v-btn id="interest" rounded color="gray" outlined> {{ users[userKey-1].int3 }} </v-btn>
          <v-btn id="interest" rounded color="gray" outlined> {{ users[userKey-1].int4 }} </v-btn>
        </v-row>
        <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
        <v-col style="flex-grow: 0; padding-left: 30px">
            <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
            <v-icon
                small
                color="black"
            >
            event
            </v-icon>
        </v-col>
        <v-col style="flex-grow: 1;"> 
            <h3 style="font-family: Arial;font-size: 12pt;">Available Sessions</h3>
        </v-col>
        </v-row>
        <v-list one-line style="font-family: Arial;font-size: 14pt;">
          <v-list-item style="padding-top: 10px;">
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Monday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].mon }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Tuesday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].tues }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Wednesday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].wed }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Thursday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse">{{ users[userKey-1].thurs }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField"
                >Friday</v-list-item-title
              >
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >{{ users[userKey-1].fri }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
    </v-col>
  </v-row>
</template> 
<script> 
  export default { 
    methods: {
      goBack(){
        return this.$router.go(-1);
      }
    },
    asyncData({params}) { console.log( params ); 
    return { userKey: params.id }; }, 
    validate({params}) 
    { return /^\d+$/.test(params.id); },
    data () {
      return {
        users: [
        { id: 1, title: 'Monica Geller', email: 'm.geller@gmail.com', pn: '0405235135', gender: 'F', dob: '15/12/1989', int1: 'cycling', int2: 'jogging', int3: 'hiking', int4: 'jogging', mon: '7AM-8AM', tues: '6PM-8PM', wed:'7AM-8AM', thurs:'Break', fri: '6PM-8PM', src: 'https://picsum.photos/id/190/200/300', job: 'Car Dealer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', link: '/leaderboard', flex: 6 },
        { id: 2, title: 'Julian Dasilvia', email: 'jsilva@gmail.com', pn: '0468231953', gender: 'F', dob: '11/10/1986', int1: 'running', int2: 'jogging', int3: 'mountain climbing', int4: 'squash', mon: '8AM-10AM', tues: '6PM-8PM', wed:'Break', thurs:'Break', fri: '4PM-6PM',  src: 'https://picsum.photos/id/400/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 3, title: 'Mike Lyne', email: 'mikelyn@gmail.com', pn: '0462931532', gender: 'M', dob: '29/04/1999', int1: 'cycling', int2: 'swimming', int3: 'football', mon: 'Break', tues: '6AM-8PM', wed:'7AM-8AM', thurs:'Break', fri: '6AM-8AM',  src: 'https://picsum.photos/id/160/200/300', job: 'Officemen', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 4, title: 'Claire Kumas', email: 'kum.cla@gmail.com', pn: '041396134', gender: 'F', dob: '25/02/1994', int1: 'football', int2: 'baseball', int3: 'basketball', int4: 'running', mon: '7AM-8AM', tues: '7AM-8AM', wed:'7AM-8AM', thurs:'7AM-8AM', fri: '7AM-8AM',  src: 'https://picsum.photos/id/150/200/300', job: 'Teacher', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', link: '/leaderboard', flex: 6 },
        { id: 5, title: 'Blair Dota', email: 'bdloat@gmail.com', pn: '0443561333', gender: 'M', dob: '17/05/1995', int1: 'jogging', int2: 'hiking', int3: 'running', mon: 'Break', tues: '6PM-8PM', wed:'Break', thurs:'6PM-8PM', fri: 'Break',  src: 'https://picsum.photos/id/237/200/300', job: 'Shop Owner', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 6, title: 'Connor Ryan', email: 'con.r12@gmail.com', pn: '0405613432', gender: 'M', dob: '16/06/1996', int1: 'tennis', int2: 'jogging', int3: 'golf', mon: '6PM-8PM', tues: '6PM-8PM', wed:'6PM-8PM', thurs:'6PM-8PM', fri: '6PM-8PM',  src: 'https://picsum.photos/id/200/200/300', job: 'Software Engineer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        { id: 7, title: 'Dendi Navidad', email: 'navidendi@gmail.com', pn: '0403231555', gender: 'M', dob: '01/04/1997', int1: 'basketball', int2: 'tennis', int3: 'cycling', int4: 'dancing', mon: '6PM-8PM', tues: 'Break', wed:'6PM-8PM', thurs:'Break', fri: '6PM-8PM',  src: 'https://picsum.photos/id/300/200/300', job: 'Graphic Designer', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit', flex: 6 },
        ],
      }
    },
  }



</script>

<style scoped>
#profileHeaderCard {
  background-color: #e94057;
}
#profileTitle {
  color: white;
}
#profilePicture {
  padding: 5%;
}
#profileAvatar {
  border-radius: 10%;
}
#leftListItem {
  padding-left: 30px;
}
#rightListItem {
  padding-right: 30px;
}
#infoHeading {
  padding-top: 20px;
  font-size: 75%;
}
#infoField {
  color: #8d8d8d;
}
#infoResponse {
  color: #8d8d8d;
  font-weight: bold;
}
#interestButtons {
  padding-top: 10px;
}
#interest {
  margin: 10px 10px;
}
#bottom {
    padding-bottom: 50px;
}
.routerLink{
     text-decoration: none;
     color:black;
 }
</style>