<template>
  <nuxt-link :to="href">
    <img :src="img" alt="">
  </nuxt-link>
</template>
<script>
export default {
  props:{
    img:{
      type:String,
      required:true
    },
    href:{
      type:String,
      required:true
    }
  }
}
</script>
<style lang="scss" scoped>

</style>