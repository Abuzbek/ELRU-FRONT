<template>
  <section>
    <h2 v-if="title" class="heading_title">{{ title }}</h2>
    <swiper class="swiper swiper_card" :options="swiperOption">
      <swiper-slide v-for="n in cards" :key="n._id">
        <Card v-bind="n" />
      </swiper-slide>
      <div class="swiper-button-prev" slot="button-prev">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="8"
          height="12"
          viewBox="0 0 8 12"
          fill="none"
        >
          <path
            d="M7 1L2 6L7 11"
            stroke="#616D75"
            stroke-width="2"
            stroke-linecap="round"
          />
        </svg>
      </div>
      <div class="swiper-button-next" slot="button-next">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="8"
          height="12"
          viewBox="0 0 8 12"
          fill="none"
        >
          <path
            d="M1 1L6 6L1 11"
            stroke="#616D75"
            stroke-width="2"
            stroke-linecap="round"
          />
        </svg>
      </div>
    </swiper>
  </section>
</template>
<script>
import Card from "../card.vue";
export default {
  components: { Card },
  data: () => ({
    swiperOption: {
      slidesPerView: 6,
      spaceBetween: 30,
      grabCursor: true,
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev"
      },
      breakpoints: {
        1024: {
          slidesPerView: 6,
          spaceBetween: 30
        },
        991: {
          slidesPerView: 4,
          spaceBetween: 30
        },
        640: {
          slidesPerView: 2,
          spaceBetween: 30
        },
        320: {
          slidesPerView: 2,
          spaceBetween: 30
        }
      }
    }
  }),
  props: {
    title: {
      type: String
    },
    cards: {
      type: Array,
      required: true
    }
  }
};
</script>
<style lang="scss" scoped>
.swiper_card {
  padding-left: 24px !important;
  padding-right: 24px !important;
}
.swiper-button-prev {
  width: 48px;
  height: 48px;
  background: white;
  border-radius: 50%;
  box-shadow: -4px -4px 4px -1px rgba(0, 0, 0, 0.04);
  left: 0px;
  &::after {
    display: none;
  }
}
.swiper-button-next {
  width: 48px;
  height: 48px;
  background: white;
  border-radius: 50%;
  box-shadow: 4px 4px 4px -1px rgba(0, 0, 0, 0.04);
  right: 0px;
  &::after {
    display: none;
  }
}
.heading_title{
  margin-bottom: 30px;
  margin-left: 30px;
  font-weight: bold;
  font-size: 24px;
  line-height: 150%;
  color: #3E4549;
}
</style>
