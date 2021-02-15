<template>
  <v-container fluid class="px_7_5">
    <swiper class="swiper" :options="swiperOption">
      <swiper-slide v-for="(n, i) in json" :key="i">
        <Card v-bind="n" />
      </swiper-slide>
      <swiper-slide v-for="(n, i) in json" :key="i">
        <Card v-bind="n" />
      </swiper-slide>
      <swiper-slide v-for="(n, i) in json" :key="i">
        <Card v-bind="n" />
      </swiper-slide>
      <swiper-slide v-for="(n, i) in json" :key="i">
        <Card v-bind="n" />
      </swiper-slide>
      <swiper-slide v-for="(n, i) in json" :key="i">
        <Card v-bind="n" />
      </swiper-slide>
      <swiper-slide v-for="(n, i) in json" :key="i">
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
    <!-- <img src="~/assets/photo.jpg" alt=""> -->
  </v-container>
</template>
<script>
import card from "../components/card";
import SwiperCore, { Navigation } from "swiper";
SwiperCore.use([Navigation]);
import json from "../static/index";
export default {
  components: { card },
  data: () => ({
    json: json,
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
  })
};
</script>
<style lang="scss" scoped>
.px_7_5 {
  padding-left: 0px !important;
  padding-right: 0px !important;
}
.swiper{
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
</style>
