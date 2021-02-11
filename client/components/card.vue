<template>
  <v-card class="box-shadow">
    <div class="card-img_wraper">
      <v-img
        class="img_card"
        :src="img"
      />
      <div class="best" :class="{'best_bottom': news}" v-if="best">Бестселлер</div>
      <div class="news" v-if="news">Новинка</div>
      <div class="sale" v-if="sale">
        - {{ 100-(Math.floor(sale/(price/100))) }}%
      </div>
    </div>
    <v-card-title class="heading">{{ heading }}</v-card-title>
    <v-card-text class="categories">
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
.box-shadow{
  box-shadow: none !important;
}
  .card-img_wraper{
    position: relative;
    .best{
      position: absolute;
      left: 0px;
      padding: 2px 8px;
      background: #D64C4C;
      color: white;
      border-radius: 0px 5px 5px 0px;
      bottom: 10px;
      &_bottom{
        bottom: 40px;
      }
    }
    .news{
      position: absolute;
      left: 0px;
      padding: 2px 8px;
      background: #219653;
      color: white;
      border-radius: 0px 5px 5px 0px;
      bottom: 10px;
    }
    .sale{
      position: absolute;
      right: 0px;
      padding: 2px 8px;
      background: #01BEDE;
      color: white;
      border-radius: 5px 0px 0px 5px;
      bottom: 10px;
    }
  }
  img{
    max-width: 100%;
    height: auto;
    object-fit: cover;
  }
  .heading{
    font-size: 16px !important;
    line-height: 24px !important;
    padding: 0px;
    letter-spacing:auto !important;
    padding-top: 10px;
    padding-bottom: 10px;
  }
  .categories{
    padding-left:0px ;
    padding-right: 0px;
    padding-bottom: 0px;
    span{
      font-weight: 500;
      font-size: 14px;
      line-height: 17px;
      color:#C0C0C0;
      margin-bottom: 5px;
    }
  }
  .overline{
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #616D75;
  }
</style>
