<template>
  <v-container>
    <v-layout row wrap>
        <v-flex xs12 md4 v-for="project in projects" :key="project.title" pr-4 pt-3>
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
                    <v-chip v-for="(tool,index) in project.tools" :key="index" color="primary" text-color="white">{{tool}}</v-chip>
                </v-card-title>
                <div v-if="project.url">
                <v-card-actions>
                    <v-btn  :href="project.url" target="_blank" dark color="blue accent-2">visit</v-btn>
                </v-card-actions>
                </div>
                <div v-else>
                    <v-alert
                        :value="true"
                        color="primary"
                        icon="info"
                        outline
                    >
                     Offline
                    </v-alert>
                </div>
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
                  short_description:'Sistem Informasi Akademik semester antara Fakultas Teknik Universitas Tanjungpura',
                  image: require('../assets/semester-antara.png'),
                  tools : ['Laravel'],
                  url:'http://sa.teknik.untan.ac.id/'
              },
              {
                  title:'International Conference',
                  year: '2016',
                  short_description:'Sistem Informasi konferensi internasional Universitas Tanjungpura',
                  image: require('../assets/international-conference.png'),
                  tools : [],
                  url:'http://icb.untan.ac.id/'
              },
              {
                  title:'Penjadwalan',
                  year: '2015-2016',
                  short_description:'Sistem Penjadwalan mata kuliah dengan algoritma genetika',
                  image: require('../assets/penjadwalan.png'),
                  tools : ['PHP'],
                  url: false
              },
              {
                  title:'SDA PUPR',
                  year: '2017',
                  short_description:'Sistem Informasi Sumber Daya Air, Pekerjaan Umum dan Perumahan Rakyat Kabupaten Landak ',
                  image: require('../assets/pupr.png'),
                  tools : ['Laravel'],
                  url: false
              },
              {
                  title:'Siakad Mahasiswa',
                  year: '2017-2018',
                  short_description:'Sistem Informasi Akademik Universitas Tanjungpura ',
                  image: require('../assets/siakad-mahasiswa.png'),
                  tools : ['Laravel'],
                  url: 'http://mahasiswa.siakad.untan.ac.id/'
              },
              {
                  title:'Siakad Dosen',
                  year: '2017-2018',
                  short_description:'Sistem Informasi Akademik Universitas Tanjungpura ',
                  image: require('../assets/siakad-dosen.png'),
                  tools : ['Laravel'],
                  url: 'http://dosen.siakad.untan.ac.id/'
              },
              {
                  title:'Evaluasi Dosen Oleh Mahasiswa',
                  year: '2017-2018',
                  short_description:'Sistem Penilaian kinerja dosen oleh mahasiswa ',
                  image: require('../assets/edom.png'),
                  tools : ['Laravel'],
                  url: 'http://edom.untan.ac.id/'
              },
              {
                  title:'Evaluasi Layanan Oleh Mahasiswa',
                  year: '2017-2018',
                  short_description:'Sistem penilaian oleh mahasiswa terhadap layanan yang diberikan Universitast Tanjungpura ',
                  image: require('../assets/elom.png'),
                  tools : ['Laravel','ACL','VueJS'],
                  url: 'https://evaluasi.untan.ac.id/'
              },
          ]
      }
    }
}
</script>
