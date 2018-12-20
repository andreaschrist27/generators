<template>
  <v-container grid-list-xl text-xs-center>
    <v-layout row wrap>
      <v-flex xs10 offset-xs1>
        <v-card dark color="indigo darken-1">
          <v-card-text>
            <v-layout row>
              <v-flex xs5 md4>
                      <v-avatar
                      :tile="false"
                      :size="140"
                      color="grey lighten-4"
                      >
                      <img src="../assets/profile.jpg" alt="avatar">
                      </v-avatar>
              </v-flex>   
             <v-flex xs7 md8>
                 <v-card-text >
                   <p class="text-sm-left headline font-weight-light font-italic mt-4 mr-3">" Interest in clean code and test driven development "</p>
                 </v-card-text>
            </v-flex>   
            </v-layout>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
