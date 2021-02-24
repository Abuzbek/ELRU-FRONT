<template>
  <swiper class="swiper slider" :options="swiperOption">
    <swiper-slide class="slider_item" v-for="n in homecarousel" :key="n._id">
      <div class="slider_item_child">
        <img :src="n.img" alt="" class="slider-img" />
        <v-btn class="slider-btn" color="#F7213E">
          Посмотреть
          <v-icon left class="ml-3">
            mdi-arrow-right
          </v-icon>
        </v-btn>
      </div>
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
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</template>
<script>
import SwiperCore, { Navigation, Pagination, Autoplay } from "swiper";
SwiperCore.use([Navigation, Pagination, Autoplay]);
export default {
  data: () => ({
    swiperOption: {
      slidesPerView: 1,
      spaceBetween: 30,
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev"
      },
      pagination: {
        el: ".swiper-pagination",
        clickable: true
      }
    }
  }),
  props: {
    homecarousel: {
      type: Array,
      required: true
    }
  }
};
</script>
<style lang="scss">
.slider {
  padding-bottom: 45px;
  .slider_item_child {
    position: relative;
    width: 100%;
    height: 100%;
    .slider-img {
      width: 100%;
      height: auto;
    }
    .slider-btn {
      position: absolute;
      color: white;
      left: 155px;
      bottom: 88px;
    }
  }
  .swiper-button-prev {
    width: 48px;
    height: 48px;
    background: white;
    border-radius: 50%;
    box-shadow: -4px -4px 4px -1px rgba(0, 0, 0, 0.04);
    left: 10px;
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
    right: 10px;
    &::after {
      display: none;
    }
  }
  .swiper-pagination-bullet {
    width: 15px !important;
    height: 15px !important;
    background: #dedede !important;
    opacity: 0.5 !important;
    margin: 0 calc(15px / 2) !important;
    &-active {
      background: transparent !important;
      border: 2px solid #01bede;
      box-sizing: border-box;
    }
  }
}
</style>
