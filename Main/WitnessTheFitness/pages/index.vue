<template>
  <b-container fluid="sm">
    <b-row justify="center" align="center">
      <b-col cols="12" sm="8" md="6">
        <b-card class="pa-md-6 mx-lg-auto">
          <b-card-title class="justify-center">
            <h3 class="text-lg-center"> Welcome to GYMMATCH</h3>
          </b-card-title>
          <b-card-text class="justify-center">
            <p class="text-md-center">Find places to walk and play with your dogs!</p>
          </b-card-text>
        </b-card>
        <b-card class="pa-md-6 mx-lg-auto">
          <b-card-title class="justify-center">
            <h3 class="text-lg-center">VIEW TOP DOG PARKS</h3>
          </b-card-title>
          <b-card-text class="justify-center">
            <p class="text-md-center">VIEW THE RANKING OF DOG PARKS</p>
          </b-card-text>
          <b-card-actions class="justify-center">
                <b-btn
                  elevation="2"
                  x-large
                  color="warning"
                  nuxt
                  class="text-center"
                  to="/ranking"
                >
                  VIEW RANKING
                </b-btn>
              </b-card-actions>
        </b-card>
        <b-card class="pa-md-6 mx-lg-auto">
          <b-card-title class="justify-center">
            <h3 class="text-lg-center">SELECT BETWEEN TWO OPTIONS</h3>
          </b-card-title>
          <b-card-text class="justify-center">
            <p class="text-md-center">Find places to walk and play with your dogs!</p>
          </b-card-text>
            <b-card
              class="pa-md-3 mx-auto my-4"
              max-width="550"
              outlined
              :style="'border: 1px solid blue;'"
            >
              <b-list-item three-line>
                <b-list-item-content>
                  <b-list-item-title class="text-h5 mb-1">
                    <NuxtLink to="/findNearby"> DOG PARK NEARBY</NuxtLink>
                  </b-list-item-title>
                  <b-list-item-subtitle>Find great places near you</b-list-item-subtitle>
                </b-list-item-content>

                <b-list-item-avatar
                  tile
                  size="80"
                  color="grey"
                ></b-list-item-avatar>
              </b-list-item>

              <b-card-actions>
                <b-btn
                  outlined
                  rounded
                  text
                  color="primary"
                  nuxt
                  to="/findNearby"
                >
                  FIND
                </b-btn>
              </b-card-actions>
            </b-card>
            <b-card
              class="pa-md-3 mx-auto my-4"
              max-width="550"
              outlined
              :style="'border: 1px solid red;'"
            >
              <b-list-item three-line>
                <b-list-item-content>
                  <b-list-item-title class="text-h5 mb-1" to="/avoid">
                    AVOID DOG ATTACKS
                  </b-list-item-title>
                  <b-list-item-subtitle>Find safe places from dogs</b-list-item-subtitle>
                </b-list-item-content>

                <b-list-item-avatar
                  tile
                  size="80"
                  color="grey"
                ></b-list-item-avatar>
              </b-list-item>

              <b-card-actions>
                <b-btn
                  outlined
                  rounded
                  text
                  color="red"
                  nuxt
                  to="/avoid"
                >
                  FIND
                </b-btn>
              </b-card-actions>
            </b-card>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>
