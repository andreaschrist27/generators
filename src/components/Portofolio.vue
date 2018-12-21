<template>
  <v-container>
    <v-layout row wrap>
        <v-flex xs12 md4 v-for="project in projects" :key="project.title" px-3 pb-4>
            <v-card>
                <v-img :gradient="!project.status ? gradient:''"
                :src="project.image"
                aspect-ratio="2"
                >
                <div v-if="!project.status">
                    <v-container fill-height >
                        <v-layout align-center>
                        <v-flex text-xs-center >
                            <p class="display-2 font-weight-thin font-italic white--text">On Progress..</p>
                        </v-flex>
                        </v-layout>
                    </v-container>
                </div>
                 </v-img>
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
    <v-layout>
        <v-flex xs12 pt-4 px-3>
            <v-alert 
            :value="true"
            color="info"
            icon="info"
            outline
            >
            Need More Information ?  <v-btn round color="primary" href="https://goo.gl/fKVEwh" target="_blank" dark>Download CV</v-btn>
            </v-alert>
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
                  year: '2016-2018',
                  short_description:'Sistem Informasi Akademik semester antara Fakultas Teknik Universitas Tanjungpura',
                  image: require('../assets/semester_antara.jpg'),
                  tools : ['Laravel'],
                  url:'http://sa.teknik.untan.ac.id/',
                  status: true
              },
              {
                  title:'International Conference',
                  year: '2016',
                  short_description:'Sistem Informasi konferensi internasional Universitas Tanjungpura',
                  image: require('../assets/international_conference.jpg'),
                  tools : [],
                  url:'http://icb.untan.ac.id/',
                  status: true
              },
              {
                  title:'Penjadwalan',
                  year: '2016',
                  short_description:'Sistem Penjadwalan mata kuliah dengan algoritma genetika',
                  image: require('../assets/penjadwalan.jpg'),
                  tools : ['PHP'],
                  url: false,
                  status: true
              },
              {
                  title:'SDA PUPR',
                  year: '2017',
                  short_description:'Sistem Informasi Sumber Daya Air, Pekerjaan Umum dan Perumahan Rakyat Kabupaten Landak ',
                  image: require('../assets/pupr.jpg'),
                  tools : ['Laravel'],
                  url: false,
                  status: true
              },
              {
                  title:'Siakad Mahasiswa',
                  year: '2017-2018',
                  short_description:'Sistem Informasi Akademik Universitas Tanjungpura ',
                  image: require('../assets/siakad_mahasiswa.jpg'),
                  tools : ['Laravel'],
                  url: 'http://mahasiswa.siakad.untan.ac.id/',
                  status: true
              },
              {
                  title:'Siakad Dosen',
                  year: '2017-2018',
                  short_description:'Sistem Informasi Akademik Universitas Tanjungpura ',
                  image: require('../assets/siakad_dosen.jpg'),
                  tools : ['Laravel'],
                  url: 'http://dosen.siakad.untan.ac.id/',
                  status: true
              },
              {
                  title:'Evaluasi Dosen Oleh Mahasiswa',
                  year: '2017-2018',
                  short_description:'Sistem Penilaian kinerja dosen oleh mahasiswa ',
                  image: require('../assets/edom.jpg'),
                  tools : ['Laravel'],
                  url: 'http://edom.untan.ac.id/',
                  status: true
              },
              {
                  title:'Evaluasi Layanan Oleh Mahasiswa',
                  year: '2017-2018',
                  short_description:'Sistem penilaian oleh mahasiswa terhadap layanan yang diberikan Universitast Tanjungpura ',
                  image: require('../assets/elom.jpg'),
                  tools : ['Laravel','ACL','VueJS'],
                  url: 'https://evaluasi.untan.ac.id/',
                  status: true
              },
               {
                  title:'Frontend Presensi Online Mahasiswa',
                  year: '2018',
                  short_description:'Frontend Sistem Presensi Online Mahasiswa Universitas Tanjungpura',
                  image: require('../assets/frontend_presensi_mahasiswa.jpg'),
                  tools : ['VueCLI'],
                  url: 'https://mahasiswa.presensi.untan.ac.id/',
                  status: true
              },
               {
                  title:'Frontend Presensi Online Dosen',
                  year: '2018',
                  short_description:'Frontend Sistem Presensi Online Dosen Universitas Tanjungpura',
                  image: require('../assets/frontend_presensi_dosen.jpg'),
                  tools : ['VueCLI'],
                  url: 'http://dosen.presensi.untan.ac.id/',
                  status: true
              },
               {
                  title:'Backend Presensi Online',
                  year: '2018',
                  short_description:'Backend Sistem Presensi Online Universitas Tanjungpura',
                  image: require('../assets/backend_presensi.jpg'),
                  tools : ['Laravel'],
                  url: 'https://presensi.untan.ac.id/',
                  status: true
              },
             {
                  title:'Backend UNTAN',
                  year: '2018',
                  short_description:'Backend Universitas Tanjungpura',
                  image: require('../assets/backend_untan.jpg'),
                  tools : ['Laravel','Redis','Horizon'],
                  url: false,
                  status: false
              },
               {
                  title:'Konveksi Online dan Custom T-shirt',
                  year: '2018',
                  short_description:'C2B, Konveksi dan custom T-shirt',
                  image: require('../assets/custom_clothes.jpg'),
                  tools : ['Laravel','VueJS','Canvas','AWS'],
                  url: false,
                  status: false
              },
          ],
          gradient: 'to top right, rgba(63,81,181, .7), rgba(25,32,72, .7)'
      }
    }
}
</script>
