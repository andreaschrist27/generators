<template>
  <v-container>
    <v-layout row wrap>
        <v-flex xs12 md4 v-for="project in projects" :key="project.title">
            <v-card>
                <v-img
                :src="project.image"
                aspect-ratio="2"
                ></v-img>

                <v-card-title primary-title>
                    <div>
                        <h3 class="headline mb-0">{{project.title}} ({{project.year}})</h3>
                        <div>{{project.short_description}}</div>
                    </div>
                    <v-chip v-for="(tool,index) in project.tools" :key="index" color="blue" text-color="white">{{tool}}</v-chip>
                </v-card-title>
                <v-card-actions>
                <v-btn  :href="project.url" target="_blank" dark color="blue accent-2">visit</v-btn>
                </v-card-actions>
            </v-card>
        </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
export default {
  name: 'portofolio',
   data () {
      return {
          projects : [
              {
                  title:'Semester Antara',
                  year: '2015-2018',
                  short_description:'Sistem Informasi Akademik semester antara fakultas teknik universitas tanjungpura',
                  image: require('../assets/semester-antara.png'),
                  tools : ['Laravel','Guzzle'],
                  url:'http://sa.teknik.untan.ac.id/'
              }
          ]
      }
    }
}
</script>
