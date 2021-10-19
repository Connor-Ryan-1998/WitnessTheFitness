<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="pa-md-6 mx-lg-auto" id="profileHeaderCard">
        <v-card-title class="justify-left">
          <h3 class="text-lg-center" id="profileTitle">User Profile</h3>
        </v-card-title>
      </v-card>
      <v-card class="pa-md-6 mx-lg-auto">
        <v-row id="profilePicture" justify="center" align="center">
          <v-avatar size="300" tile>
            <img
              src="https://cdn.vuetifyjs.com/images/john.jpg"
              alt="JF"
              id="profileAvatar"
            />
          </v-avatar>
        </v-row>
        <v-row id="infoHeading" style="font-family: Arial;font-size: 12pt;">
          <h3>Personal Information</h3>
        </v-row>
        <v-list one-line style="font-family: Arial;font-size: 14pt;">
          <v-list-item style="padding-top: 10px;">
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Username</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >Tom Nook</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Email</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >tom_nook@gmail.com</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Phone</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >(+61) 414 454 020</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Gender</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse">Male</v-list-item-title>
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
                >15/06/1996</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-row id="infoHeading">
          <h3>Interests</h3>
        </v-row>
        <v-row id="interestButtons">
          <v-btn
            style="margin-left: 30px"
            id="interest"
            rounded
            color="gray"
            outlined
          >
            Yoga
          </v-btn>
          <v-btn id="interest" rounded color="gray" outlined> Weights </v-btn>
          <v-btn id="interest" rounded color="gray" outlined> Boxing </v-btn>
        </v-row>
        <v-row id="infoHeading">
          <h3>Available Sessions</h3>
        </v-row>
        <v-list one-line style="font-family: Arial;font-size: 14pt;">
          <v-list-item style="padding-top: 10px;">
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Monday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >7AM - 8:30AM</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Tuesday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >3PM - 4PM</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Wednesday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse"
                >3PM - 4PM</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content align="left" id="leftListItem">
              <v-list-item-title id="infoField">Thursday</v-list-item-title>
            </v-list-item-content>

            <v-list-item-content align="right" id="rightListItem">
              <v-list-item-title id="infoResponse">7:30 - 9PM</v-list-item-title>
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
                >6AM - 8AM</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <div id="bottom">
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>


<script>
export default {
  data() {
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
  padding-left: 30px;
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
</style>