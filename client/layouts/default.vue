<template>
  <v-app>
    <Navtop/>
    <v-main>
        <nuxt />
    </v-main>
  </v-app>
</template>

<script>
import Navtop from '../components/navbarTop'
export default {
  data () {
    return {
    }
  },
  components:{
    Navtop
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700;800&display=swap');
body{
  font-family: 'Open Sans', sans-serif;
}
</style>