<template>
  <v-container grid-list-xl text-xs-center>
    <v-layout row wrap>
      <v-flex xs10 offset-xs1>
        <v-card dark color="indigo darken-1">
          <v-card-text>
            <v-layout row wrap>
              <v-flex xs12 md3>
                      <v-avatar
                      :tile="false"
                      :size="140"
                      color="grey lighten-4"
                      >
                      <img src="../assets/profile.jpg" alt="avatar">
                      </v-avatar>
              </v-flex>   
             <v-flex xs12 md8>
                 <v-card-text >
                   <p class="text-sm-left headline font-weight-light font-italic pt-4">" Interest in clean code and test driven development "</p>
                 </v-card-text>
            </v-flex>   
            </v-layout>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
     <v-layout row justify-center>
      <v-flex xs12>
               <v-btn
                v-for="(social, i) in socials"
                :key="i"
                :color="social.color"
                class="white--text"
                fab
                icon
                small
                :href="social.link"
                target="_blank"
              >
                <v-icon>{{ social.icon }}</v-icon>
              </v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
        socials: [
        {
          icon: 'fab fa-facebook',
          color: 'indigo',
          link:'https://www.facebook.com/AndreasChristianOfficialAccount'
        },
        {
          icon: 'fab fa-github',
          color: 'grey darken-3',
          link:'https://github.com/andreaschrist27'
        }
      ]
    }
  }
}
</script>
