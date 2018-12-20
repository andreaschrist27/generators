<template>
  <div id="app">
    <v-app>
      <Profile/>
      <Portofolio/>
    </v-app>
  </div>
</template>

<script>
import Profile from './components/Profile.vue'
import Portofolio from './components/Portofolio.vue'

export default {
  name: 'app',
  components: {
    Profile,
    Portofolio
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
