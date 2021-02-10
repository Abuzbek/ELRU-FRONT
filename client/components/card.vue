<template>
  <v-card>
    <div class="card-img_wraper">
      <v-img
        class="img_card"
        height="280"
        :src="img"
      />
      <div class="best" v-if="best">Бестселлер</div>
      <div class="news" v-if="news">Новинка</div>
      <div class="sale" v-if="sale">
        - {{ 100-(Math.floor(sale/(price/100))) }}%
      </div>
    </div>
    <v-card-title>{{ heading }}</v-card-title>
    <v-card-text>
      <span v-if="paper">
        Бумажная,
      </span>
      <span class="ml-2" v-if="audio">
        аудио,
      </span>
      <span class="ml-2" v-if="ebook">
        pdf
      </span>
    </v-card-text>
    <div class="overline">
      {{ author }}
    </div>
  </v-card>
</template>
<script>
export default {
  props: {
    _id: {
      type: String,
      required: true,
    },
    paper: {
      type: Boolean,
    },
    ebook: {
      type: Boolean,
    },
    audio: {
      type: Boolean,
    },
    img: {
      type: String,
      default: "../assets/default.jpg",
    },
    heading: {
      type: String,
      required: true,
    },
    author: {
      type: String,
      required: true,
    },
    categories: {
      type: String,
    },
    news: {
      type: Boolean,
    },
    best: {
      type: Boolean,
    },
    price: {
      type: Number,
      required: true,
    },
    sale: {
      type: Number,
    },
  },
};
</script>
<style lang="scss" scoped>
  .card-img_wraper{
    position: relative;

  }
</style>
